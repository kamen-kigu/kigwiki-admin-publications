---
title: Animegao Usage in 2026 - An Analytical Look
tags:
  - ramblings
  - lore
  - animegao kigurumi
description: "An Analytical look at the current usage  of the term Animegao."
authors: admin
date: 2026-08-09T10:00
slug: /animegao-usage
canonical_url: https://kig.wiki/publications/animegao-usage
---

# The State of Animegao in 2026

In our previous publication on [the history and lore of Animegao](/publications/animegao-history) we explored the past of the term Animegao, and how it came to be. In this publication lets explore the present.

{/* truncate */}

On an anecdotal and social basis, the term has largely faded away from usage in most larger Kigurumi communities. Most social media posts are absent of the term, and those that do are often in a deluge of other hashtags attempting to maximize views and reach.

Anecdotes involving Kigurumi performers are one thing however, lets try to put some numbers to things by those who are most financially invested in the hobby, makers.

## Makers and their usage

I threw together a quick script to scrape all the makers I'm aware of. In specific their last 20 X posts that were not retweets, the homepage of their site, and any of their site's pages that were linked on the homepage. 107 makers in total.

Totals:
Only 6 makers out of 107 use the term Animegao in their website or their X posts, with the only X post usage being in a series of countless hashtags (GKO).
69 makers out of 107 specifically used Kigurumi in English, with a spread of usage in both the body of X posts as well as in hashtags.
The rest of the makers did not use either, using only terms in their own language for Kigurumi, this is also due to many makers simply not targeting western markets.

For those new to Kigurumi who may be asking "why X posts?", the answer is simple, despite the state of that platform it is where almost all Makers regardless of region are present and posting. X is the de facto platform for Kigurumi makers and performers. Although many makers will still post on other platforms, such as many Chinese makers posting on Xiaohongshu.

<details>
<summary>Script Details and Output</summary>

The following script can be run in the root directory of the Kig Wiki repository to scan our maker folders and their json files for mentions of Animegao and Kigurumi.
If Internet Archive environment variables are set, the site will also archive the pages in the state they are found.
The last 20 X posts are scanned for mentions of Animegao and Kigurumi, as well as the homepage and any linked internal pages are scanned for mentions of the terms.

<details>
<summary>Script</summary>
```python
#!/usr/bin/env -S uv run --script
# /// script
# requires-python = ">=3.11"
# dependencies = [
#   "httpx>=0.27",
#   "beautifulsoup4>=4.12",
#   "lxml>=5.0",
# ]
# ///

from **future** import annotations

import argparse
import json
import os
import re
import sys
import time
import warnings
from dataclasses import dataclass, field
from pathlib import Path
from typing import Any, Literal
from urllib.parse import quote, urldefrag, urljoin, urlparse

import httpx
from bs4 import BeautifulSoup, XMLParsedAsHTMLWarning

warnings.filterwarnings("ignore", category=XMLParsedAsHTMLWarning)

REPO_ROOT = Path(**file**).resolve().parent.parent
FX_API_BASE = "https://api.fxtwitter.com"
WAYBACK_SAVE = "https://web.archive.org/save"
WAYBACK_STATUS = "https://web.archive.org/save/status"
TweetMentionKind = Literal["general", "hashtag_only"]
TermName = Literal["animegao", "kigurumi"]
TERMS: tuple[TermName, ...] = ("animegao", "kigurumi")
TERM_PHRASE_RE: dict[TermName, re.Pattern[str]] = {
"animegao": re.compile(r"animegao", re.IGNORECASE),
"kigurumi": re.compile(r"kigurumi", re.IGNORECASE),
}
HASHTAG_TOKEN_RE = re.compile(r"[#＃][^\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\s#＃]+")
PRIMARY_TERM: TermName = "animegao"
TARGET_POSTS = 20
FX_PAGE_SIZE = 20
FX_MAX_PAGES = 6
FX_MIN_INTERVAL_S = 1.25
FX_RETRY_LIMIT = 5
SITE_TIMEOUT_S = 20.0
SITE_MIN_INTERVAL_S = 0.4
SITE_MAX_BYTES = 2_000_000
SITE_MAX_CHILD_PAGES = 40
ARCHIVE_MIN_INTERVAL_S = 6.0
ARCHIVE_POLL_INTERVAL_S = 4.0
ARCHIVE_POLL_ATTEMPTS = 20
ARCHIVE_IF_NOT_WITHIN = "30d"
USER_AGENT = (
"KigWikiAnimegaoScan/1.0 (+https://kig.wiki; research; polite crawler)"
)
UNSAFE_LINE_TRANS = str.maketrans({
"\u2028": "\n",
"\u2029": "\n",
"\u0085": "\n",
})
SKIP_LINK_SUFFIXES = (
".jpg",
".jpeg",
".png",
".gif",
".webp",
".svg",
".ico",
".css",
".js",
".mjs",
".map",
".pdf",
".zip",
".rar",
".7z",
".mp4",
".webm",
".mp3",
".wav",
".woff",
".woff2",
".ttf",
".eot",
)
SKIP_LINK_SCHEMES = {"mailto", "tel", "javascript", "data"}
MARKETPLACE_HOST_MARKERS = (
"taobao.com",
"tmall.com",
"tmall.hk",
"liangxinyao.com",
)

@dataclass
class TweetHit:
url: str
text: str

@dataclass
class SiteHit:
url: str
excerpt: str
archive_url: str | None = None
term: TermName = "animegao"

@dataclass
class ScannedPage:
url: str
hit_terms: list[TermName] = field(default_factory=list)
archive_url: str | None = None
archive_note: str | None = None

    @property
    def hit(self) -> bool:
        return bool(self.hit_terms)

@dataclass
class MakerScan:
name: str
region: str
source: str
handle: str | None = None
website: str | None = None
tweet_hits: dict[TermName, list[TweetHit]] = field(
default_factory=lambda: {term: [] for term in TERMS}
)
tweet_hashtag_hits: dict[TermName, list[TweetHit]] = field(
default_factory=lambda: {term: [] for term in TERMS}
)
site_hits: dict[TermName, list[SiteHit]] = field(
default_factory=lambda: {term: [] for term in TERMS}
)
scanned_tweets: list[TweetHit] = field(default_factory=list)
scanned_pages: list[ScannedPage] = field(default_factory=list)
twitter_error: str | None = None
website_error: str | None = None

    @property
    def has_animegao_hits(self) -> bool:
        return bool(
            self.tweet_hits["animegao"]
            or self.tweet_hashtag_hits["animegao"]
            or self.site_hits["animegao"]
        )

class RateLimiter:
def **init**(self, min_interval_s: float) -> None:
self.min_interval_s = min_interval_s
self.\_last = 0.0

    def wait(self) -> None:
        elapsed = time.monotonic() - self._last
        remaining = self.min_interval_s - elapsed
        if remaining > 0:
            time.sleep(remaining)
        self._last = time.monotonic()

def clean_text(text: str) -> str:
return (text or "").translate(UNSAFE_LINE_TRANS)

def wayback_browse_url(url: str) -> str:
return f"https://web.archive.org/web/*/{url}"

def wayback_capture_url(timestamp: str, url: str) -> str:
return f"https://web.archive.org/web/{timestamp}/{url}"

def archive_credentials() -> tuple[str, str] | None:
access = os.environ.get("IA_S3_ACCESS_KEY") or os.environ.get("ARCHIVE_ACCESS_KEY")
secret = os.environ.get("IA_S3_SECRET_KEY") or os.environ.get("ARCHIVE_SECRET_KEY")
if access and secret:
return access, secret
return None

class WaybackArchiver:
def **init**(self, client: httpx.Client, limiter: RateLimiter, enabled: bool) -> None:
self.client = client
self.limiter = limiter
self.enabled = enabled
self.credentials = archive_credentials()
self.\_cache: dict[str, tuple[str | None, str | None]] = {}

    def resolve(self, url: str, *, save: bool = False) -> tuple[str | None, str | None]:
        cache_key = f"{int(save)}:{url}"
        cached = self._cache.get(cache_key)
        if cached is not None:
            return cached

        browse = wayback_browse_url(url)
        if not self.enabled or not save:
            note = None if self.enabled else "archive save skipped"
            result = (browse, note)
            self._cache[cache_key] = result
            return result

        if self.credentials:
            saved, note = self._save_authenticated(url)
            result = (saved or browse, note)
            self._cache[cache_key] = result
            return result

        result = (browse, "set IA_S3_ACCESS_KEY/IA_S3_SECRET_KEY to Save Page Now")
        self._cache[cache_key] = result
        return result

    def _auth_headers(self) -> dict[str, str]:
        assert self.credentials is not None
        access, secret = self.credentials
        return {
            "Accept": "application/json",
            "Authorization": f"LOW {access}:{secret}",
        }

    def _save_authenticated(self, url: str) -> tuple[str | None, str | None]:
        self.limiter.wait()
        try:
            response = self.client.post(
                WAYBACK_SAVE,
                headers=self._auth_headers(),
                data={
                    "url": url,
                    "skip_first_archive": "1",
                    "js_behavior_timeout": "0",
                    "if_not_archived_within": ARCHIVE_IF_NOT_WITHIN,
                },
                timeout=60.0,
            )
        except httpx.HTTPError as exc:
            return None, f"archive save network error: {exc}"

        if response.status_code == 429:
            return None, "archive save rate-limited"

        try:
            body = response.json()
        except json.JSONDecodeError:
            return None, f"archive save HTTP {response.status_code}"

        if response.status_code >= 400:
            return None, body.get("message") or f"archive save HTTP {response.status_code}"

        recent = body.get("relative_url") or body.get("url")
        timestamp = body.get("timestamp")
        if timestamp and body.get("original_url"):
            return wayback_capture_url(str(timestamp), str(body["original_url"])), "reused recent capture"

        job_id = body.get("job_id")
        if not job_id:
            if isinstance(recent, str) and recent.startswith("http"):
                return recent, "archive save accepted"
            return None, "archive save returned no job id"

        return self._poll_job(str(job_id))

    def _poll_job(self, job_id: str) -> tuple[str | None, str | None]:
        for _ in range(ARCHIVE_POLL_ATTEMPTS):
            time.sleep(ARCHIVE_POLL_INTERVAL_S)
            try:
                response = self.client.get(
                    f"{WAYBACK_STATUS}/{quote(job_id, safe='')}",
                    headers=self._auth_headers(),
                    timeout=30.0,
                )
                body = response.json()
            except (httpx.HTTPError, json.JSONDecodeError):
                continue

            status = body.get("status")
            if status == "success":
                timestamp = body.get("timestamp")
                original = body.get("original_url")
                if timestamp and original:
                    return wayback_capture_url(str(timestamp), str(original)), "archived"
                return None, "archive succeeded without timestamp"
            if status == "error":
                return None, body.get("message") or body.get("status_ext") or "archive error"
        return None, "archive save still pending"

def load_makers(paths: list[Path]) -> list[tuple[Path, dict[str, Any]]]:
makers: list[tuple[Path, dict[str, Any]]] = []
for directory in paths:
if not directory.is_dir():
continue
for path in sorted(directory.glob("\*.json")):
makers.append((path, json.loads(path.read_text(encoding="utf-8"))))
return makers

def extract_handle(socials: dict[str, Any] | None) -> str | None:
if not socials:
return None
raw = socials.get("x") or socials.get("twitter")
if not raw or not isinstance(raw, str):
return None
parsed = urlparse(raw.strip())
path = parsed.path.strip("/")
if not path:
return None
handle = path.split("/")[0].lstrip("@")
return handle or None

def phrase_matches(text: str, term: TermName = PRIMARY_TERM) -> bool:
return bool(TERM_PHRASE_RE[term].search(text or ""))

def classify_tweet_mention(text: str, term: TermName) -> TweetMentionKind | None:
if not phrase_matches(text, term):
return None
without_hashtags = HASHTAG_TOKEN_RE.sub(" ", text)
if phrase_matches(without_hashtags, term):
return "general"
return "hashtag_only"

def classify_all_tweet_mentions(text: str) -> dict[TermName, TweetMentionKind]:
found: dict[TermName, TweetMentionKind] = {}
for term in TERMS:
kind = classify_tweet_mention(text, term)
if kind is not None:
found[term] = kind
return found

def matching_terms(text: str) -> list[TermName]:
return [term for term in TERMS if phrase_matches(text, term)]

def host_of(url: str) -> str:
host = urlparse(url if "://" in url else f"https://{url}").netloc.casefold()
return host.removeprefix("www.")

def is_marketplace_url(url: str) -> bool:
host = host_of(url)
return any(host == marker or host.endswith("." + marker) for marker in MARKETPLACE_HOST_MARKERS)

def excerpt_around(text: str, term: TermName, radius: int = 80) -> str:
match = TERM_PHRASE_RE[term].search(text)
if not match:
return ""
start = max(0, match.start() - radius)
end = min(len(text), match.end() + radius)
chunk = text[start:end].replace("\n", " ").strip()
if start > 0:
chunk = "…" + chunk
if end < len(text):
chunk = chunk + "…"
return chunk

def is_own_post(status: dict[str, Any], handle: str) -> bool:
if status.get("reposted_by") is not None:
return False
author = (status.get("author") or {}).get("screen_name") or ""
return author.casefold() == handle.casefold()

def fetch_fx_statuses(
client: httpx.Client,
limiter: RateLimiter,
handle: str,
) -> tuple[list[dict[str, Any]], str | None]:
collected: list[dict[str, Any]] = []
cursor: str | None = None
seen_ids: set[str] = set()
error: str | None = None

    for _ in range(FX_MAX_PAGES):
        if len(collected) >= TARGET_POSTS:
            break

        params: dict[str, str | int] = {"count": FX_PAGE_SIZE}
        if cursor:
            params["cursor"] = cursor

        body: dict[str, Any] | None = None
        for attempt in range(FX_RETRY_LIMIT):
            limiter.wait()
            try:
                response = client.get(
                    f"{FX_API_BASE}/2/profile/{handle}/statuses",
                    params=params,
                )
            except httpx.HTTPError as exc:
                error = f"network error: {exc}"
                return collected, error

            if response.status_code == 429:
                retry_after = response.headers.get("Retry-After")
                delay = float(retry_after) if retry_after and retry_after.isdigit() else min(
                    30.0, FX_MIN_INTERVAL_S * (2**attempt)
                )
                time.sleep(delay)
                continue

            if response.status_code == 404:
                return collected, "profile not found or empty timeline"

            if response.status_code >= 500:
                time.sleep(min(20.0, FX_MIN_INTERVAL_S * (2**attempt)))
                continue

            try:
                body = response.json()
            except json.JSONDecodeError:
                error = f"invalid JSON (HTTP {response.status_code})"
                return collected, error

            if response.status_code != 200 or body.get("code") != 200:
                error = body.get("message") or f"HTTP {response.status_code}"
                return collected, error
            break
        else:
            return collected, "rate limited by FxTwitter after retries"

        assert body is not None
        results = body.get("results") or []
        if not results:
            break

        for status in results:
            if status.get("type") not in (None, "status"):
                continue
            status_id = str(status.get("id") or "")
            if not status_id or status_id in seen_ids:
                continue
            if not is_own_post(status, handle):
                continue
            seen_ids.add(status_id)
            collected.append(status)
            if len(collected) >= TARGET_POSTS:
                break

        cursor = (body.get("cursor") or {}).get("bottom")
        if not cursor:
            break

    return collected[:TARGET_POSTS], error

def html_to_text(html: str) -> str:
soup = BeautifulSoup(html, "lxml")
for tag in soup(["script", "style", "noscript", "svg", "template"]):
tag.decompose()
text = soup.get_text("\n", strip=True)
return re.sub(r"\n{3,}", "\n\n", text)

def same_site(base: str, candidate: str) -> bool:
base_host = urlparse(base).netloc.casefold().removeprefix("www.")
cand_host = urlparse(candidate).netloc.casefold().removeprefix("www.")
return bool(base_host) and base_host == cand_host

def normalize*page_url(url: str) -> str:
cleaned, * = urldefrag(url)
parsed = urlparse(cleaned)
path = parsed.path or "/"
if path != "/" and path.endswith("/"):
path = path.rstrip("/")
return parsed.\_replace(fragment="", path=path, query=parsed.query).geturl()

def should_skip_url(url: str) -> bool:
parsed = urlparse(url)
if parsed.scheme.casefold() in SKIP_LINK_SCHEMES:
return True
if parsed.scheme not in ("http", "https"):
return True
if is_marketplace_url(url):
return True
path = parsed.path.casefold()
return any(path.endswith(suffix) for suffix in SKIP_LINK_SUFFIXES)

def extract_same_site_links(page_url: str, html: str) -> list[str]:
soup = BeautifulSoup(html, "lxml")
found: list[str] = []
seen: set[str] = set()
for anchor in soup.find_all("a", href=True):
href = anchor.get("href")
if not href or not isinstance(href, str):
continue
absolute = urljoin(page_url, href.strip())
if should_skip_url(absolute) or not same_site(page_url, absolute):
continue
normalized = normalize_page_url(absolute)
if normalized in seen or normalized == normalize_page_url(page_url):
continue
seen.add(normalized)
found.append(normalized)
return found

def fetch_page(
client: httpx.Client,
limiter: RateLimiter,
url: str,
) -> tuple[str | None, str | None, str | None]:
limiter.wait()
try:
with client.stream("GET", url, follow_redirects=True) as response:
content_type = (response.headers.get("content-type") or "").casefold()
if response.status_code >= 400:
return None, None, f"HTTP {response.status_code}"
if "text/html" not in content_type and "application/xhtml" not in content_type:
if content_type and not content_type.startswith("text/"):
return None, None, f"skipped non-HTML ({content_type.split(';')[0]})"
chunks: list[bytes] = []
total = 0
for chunk in response.iter_bytes():
total += len(chunk)
if total > SITE_MAX_BYTES:
return None, None, "response too large"
chunks.append(chunk)
raw = b"".join(chunks)
encoding = response.charset_encoding or "utf-8"
html = raw.decode(encoding, errors="replace")
return str(response.url), html, None
except httpx.HTTPError as exc:
return None, None, f"network error: {exc}"

def scan_website(
client: httpx.Client,
limiter: RateLimiter,
website: str,
archiver: WaybackArchiver,
archive_all: bool,
) -> tuple[dict[TermName, list[SiteHit]], list[ScannedPage], str | None]:
root = website if "://" in website else f"https://{website}"
final_url, html, error = fetch_page(client, limiter, root)
if error or not html or not final_url:
return {term: [] for term in TERMS}, [], error or "empty response"

    fetched: list[tuple[str, str]] = [(final_url, html_to_text(html))]
    child_urls = extract_same_site_links(final_url, html)[:SITE_MAX_CHILD_PAGES]

    for child in child_urls:
        child_final, child_html, child_error = fetch_page(client, limiter, child)
        if child_error or not child_html or not child_final:
            continue
        fetched.append((child_final, html_to_text(child_html)))

    hits: dict[TermName, list[SiteHit]] = {term: [] for term in TERMS}
    pages: list[ScannedPage] = []
    for url, text in fetched:
        terms = matching_terms(text)
        should_save = PRIMARY_TERM in terms or archive_all
        archive_url, archive_note = archiver.resolve(url, save=should_save)
        pages.append(
            ScannedPage(
                url=url,
                hit_terms=terms,
                archive_url=archive_url,
                archive_note=archive_note,
            )
        )
        for term in terms:
            hits[term].append(
                SiteHit(
                    url=url,
                    excerpt=clean_text(excerpt_around(text, term)),
                    archive_url=archive_url,
                    term=term,
                )
            )
    return hits, pages, None

def scan_maker(
path: Path,
data: dict[str, Any],
fx_client: httpx.Client,
web_client: httpx.Client,
fx_limiter: RateLimiter,
web_limiter: RateLimiter,
archiver: WaybackArchiver,
archive_all: bool,
) -> MakerScan:
source = "makers" if path.parent.name == "makers" else path.parent.name
website = data.get("website") if isinstance(data.get("website"), str) else None
if website and is_marketplace_url(website):
website = None

    result = MakerScan(
        name=str(data.get("name") or path.stem),
        region=str(data.get("Region") or data.get("region") or "unknown"),
        source=source,
        handle=extract_handle(data.get("socials")),
        website=website,
    )

    if result.handle:
        statuses, error = fetch_fx_statuses(fx_client, fx_limiter, result.handle)
        result.twitter_error = error
        for status in statuses:
            text = clean_text(str(status.get("text") or ""))
            url = str(status.get("url") or f"https://x.com/{result.handle}/status/{status.get('id')}")
            entry = TweetHit(url=url, text=text)
            result.scanned_tweets.append(entry)
            for term, kind in classify_all_tweet_mentions(text).items():
                if kind == "general":
                    result.tweet_hits[term].append(entry)
                else:
                    result.tweet_hashtag_hits[term].append(entry)

    if result.website:
        hits, pages, error = scan_website(
            web_client, web_limiter, result.website, archiver, archive_all
        )
        result.website_error = error
        result.site_hits = hits
        result.scanned_pages = pages

    return result

def format_site_hit_line(term: TermName, index: int, hit: SiteHit) -> str:
line = f"site {term} references {index} : {hit.url}"
if hit.archive_url:
line += f" | archive: {hit.archive_url}"
return line

def format_url_list(label: str, hits: list[TweetHit]) -> str:
if not hits:
return f"{label}: none (0)"
urls = ", ".join(hit.url for hit in hits)
return f"{label} ({len(hits)}): {urls}"

def format_compact(results: list[MakerScan]) -> str:
lines: list[str] = []
zero_animegao: list[str] = []

    for scan in results:
        has_any = any(
            scan.site_hits[term]
            or scan.tweet_hits[term]
            or scan.tweet_hashtag_hits[term]
            for term in TERMS
        )
        if not scan.has_animegao_hits:
            zero_animegao.append(scan.name)
        if not has_any:
            continue

        lines.append(f"maker: {scan.name}")
        lines.append(f"region: {scan.region}")
        for term in TERMS:
            site_hits = scan.site_hits[term]
            if site_hits:
                for index, hit in enumerate(site_hits, start=1):
                    lines.append(format_site_hit_line(term, index, hit))
            else:
                lines.append(f"site {term} references: none (0)")
            lines.append(
                format_url_list(
                    f"x.com {term} references",
                    scan.tweet_hits[term],
                )
            )
            lines.append(
                format_url_list(
                    f"x.com {term} hashtag-only references",
                    scan.tweet_hashtag_hits[term],
                )
            )
        lines.append("")

    lines.append("makers with zero animegao reference:")
    lines.append(" ".join(zero_animegao) if zero_animegao else "(none)")
    lines.append("")
    lines.append(_format_totals(results))
    return "\n".join(lines).rstrip() + "\n"

def \_format_totals(results: list[MakerScan]) -> str:
lines = ["totals:"]
for term in TERMS:
site = sum(len(scan.site_hits[term]) for scan in results)
general = sum(len(scan.tweet_hits[term]) for scan in results)
hashtag = sum(len(scan.tweet_hashtag_hits[term]) for scan in results)
makers_with = sum(
1
for scan in results
if scan.site_hits[term] or scan.tweet_hits[term] or scan.tweet_hashtag_hits[term]
)
lines.append(
f" {term}: {makers_with} makers | "
f"site pages {site} | x.com general {general} | x.com hashtag-only {hashtag}"
)
return "\n".join(lines)

def tweet_marker(text: str) -> str:
kinds = classify_all_tweet_mentions(text)
if not kinds:
return "ok"
parts: list[str] = []
for term in TERMS:
kind = kinds.get(term)
if kind == "general":
parts.append(term)
elif kind == "hashtag_only":
parts.append(f"{term}#")
return "HIT " + ",".join(parts)

def format_verbose(results: list[MakerScan]) -> str:
lines: list[str] = []

    for scan in results:
        lines.append("=" * 72)
        lines.append(f"maker: {scan.name}")
        lines.append(f"region: {scan.region}")
        lines.append(f"source: {scan.source}")
        lines.append(f"handle: {scan.handle or '(none)'}")
        lines.append(f"website: {scan.website or '(none)'}")
        if scan.twitter_error:
            lines.append(f"twitter note: {scan.twitter_error}")
        if scan.website_error:
            lines.append(f"website note: {scan.website_error}")
        lines.append("")

        lines.append(f"--- scanned tweets ({len(scan.scanned_tweets)}) ---")
        if not scan.scanned_tweets:
            lines.append("(none)")
        for tweet in scan.scanned_tweets:
            lines.append(f"[{tweet_marker(tweet.text)}] {tweet.url}")
            lines.append(clean_text(tweet.text) or "(empty)")
            lines.append("")

        lines.append(f"--- scanned website pages ({len(scan.scanned_pages)}) ---")
        if not scan.scanned_pages:
            lines.append("(none)")
        for page in scan.scanned_pages:
            if page.hit_terms:
                marker = "HIT " + ",".join(page.hit_terms)
            else:
                marker = "ok"
            lines.append(f"[{marker}] {page.url}")
            if page.archive_url:
                lines.append(f"archive: {page.archive_url}")
            if page.archive_note:
                lines.append(f"archive note: {page.archive_note}")
            lines.append("")

    lines.append("=" * 72)
    lines.append("RESULTS")
    lines.append("=" * 72)
    lines.append(format_compact(results).rstrip())
    return "\n".join(lines).rstrip() + "\n"

def parse_args(argv: list[str] | None = None) -> argparse.Namespace:
parser = argparse.ArgumentParser(
description=(
"Scan makers and unused_makers for 'animegao' and 'kigurumi' "
"mentions on FxTwitter timelines and maker websites. Website "
"bodies are not dumped; pages are linked to the Wayback Machine instead."
)
)
parser.add_argument(
"-v",
"--verbose",
action="store_true",
help="Print scanned tweet texts and website URLs/archive links, then the summary",
)
parser.add_argument(
"--makers-dir",
type=Path,
default=REPO_ROOT / "makers",
help="Directory of published maker JSON files",
)
parser.add_argument(
"--unused-dir",
type=Path,
default=REPO_ROOT / "unused_makers",
help="Directory of unused maker JSON files",
)
parser.add_argument(
"--limit",
type=int,
default=0,
help="Only scan the first N makers (0 = all); useful for smoke tests",
)
parser.add_argument(
"--no-archive",
action="store_true",
help="Skip Wayback Save Page Now attempts; still emit web/\*/ browse links",
)
parser.add_argument(
"--archive-all",
action="store_true",
help="Save Page Now every scanned website page (default: only animegao hits)",
)
return parser.parse_args(argv)

def main(argv: list[str] | None = None) -> int:
args = parse_args(argv)
makers = load_makers([args.makers_dir, args.unused_dir])
if args.limit > 0:
makers = makers[: args.limit]

    if not makers:
        print("No maker JSON files found.", file=sys.stderr)
        return 1

    fx_limiter = RateLimiter(FX_MIN_INTERVAL_S)
    web_limiter = RateLimiter(SITE_MIN_INTERVAL_S)
    archive_limiter = RateLimiter(ARCHIVE_MIN_INTERVAL_S)
    headers = {"User-Agent": USER_AGENT, "Accept": "application/json, text/html, */*"}

    results: list[MakerScan] = []
    with (
        httpx.Client(headers=headers, timeout=30.0) as fx_client,
        httpx.Client(
            headers={**headers, "Accept": "text/html,application/xhtml+xml;q=0.9,*/*;q=0.8"},
            timeout=SITE_TIMEOUT_S,
            follow_redirects=True,
        ) as web_client,
        httpx.Client(headers=headers, timeout=60.0, follow_redirects=True) as archive_client,
    ):
        archiver = WaybackArchiver(
            archive_client,
            archive_limiter,
            enabled=not args.no_archive,
        )
        if archiver.enabled and not archiver.credentials:
            print(
                "No IA_S3_ACCESS_KEY/IA_S3_SECRET_KEY set; "
                "logging Wayback browse links only (no Save Page Now).",
                file=sys.stderr,
            )

        total = len(makers)
        for index, (path, data) in enumerate(makers, start=1):
            name = data.get("name") or path.stem
            print(f"[{index}/{total}] scanning {name}…", file=sys.stderr)
            results.append(
                scan_maker(
                    path,
                    data,
                    fx_client,
                    web_client,
                    fx_limiter,
                    web_limiter,
                    archiver,
                    archive_all=args.archive_all,
                )
            )

    output = format_verbose(results) if args.verbose else format_compact(results)
    sys.stdout.write(output)
    return 0

if **name** == "**main**":
raise SystemExit(main())

````
</details>

<details>
<summary>Script Output</summary>

```text
maker: 2D Fantasy
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (20): https://x.com/2DFantasy111/status/1948314224578716125, https://x.com/2DFantasy111/status/1940040152656879935, https://x.com/2DFantasy111/status/1931692456300667100, https://x.com/2DFantasy111/status/1928788766161788964, https://x.com/2DFantasy111/status/1925110084411265516, https://x.com/2DFantasy111/status/1924444357442363546, https://x.com/2DFantasy111/status/1923665215113384269, https://x.com/2DFantasy111/status/1922989295666614353, https://x.com/2DFantasy111/status/1916755398578823387, https://x.com/2DFantasy111/status/1892823919167754601, https://x.com/2DFantasy111/status/1888065811224609088, https://x.com/2DFantasy111/status/1887341691780350293, https://x.com/2DFantasy111/status/1874335344084344878, https://x.com/2DFantasy111/status/1868617944743498204, https://x.com/2DFantasy111/status/1865266487893856758, https://x.com/2DFantasy111/status/1864175579530186997, https://x.com/2DFantasy111/status/1861673673444540497, https://x.com/2DFantasy111/status/1856193396940943844, https://x.com/2DFantasy111/status/1854754018565956011, https://x.com/2DFantasy111/status/1849995967875215659

maker: Aria
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (19): https://x.com/mitsukiriya/status/1993960415655809466, https://x.com/mitsukiriya/status/1984917681305522301, https://x.com/mitsukiriya/status/1984204121508110695, https://x.com/mitsukiriya/status/1983450676387844203, https://x.com/mitsukiriya/status/1982402809615237548, https://x.com/mitsukiriya/status/1982335224681033971, https://x.com/mitsukiriya/status/1981636320415158344, https://x.com/mitsukiriya/status/1981256489169014857, https://x.com/mitsukiriya/status/1980611020940001531, https://x.com/mitsukiriya/status/1980361057266020583, https://x.com/mitsukiriya/status/1936734156232482988, https://x.com/mitsukiriya/status/1929949730773364876, https://x.com/mitsukiriya/status/1927057671435206711, https://x.com/mitsukiriya/status/1916439966433100249, https://x.com/mitsukiriya/status/1912485504345673732, https://x.com/mitsukiriya/status/1911706257230021094, https://x.com/mitsukiriya/status/1884245127310544983, https://x.com/mitsukiriya/status/1881347890800706026, https://x.com/mitsukiriya/status/1880562297472688228

maker: BHY Renxing
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://bhyrenxing.com | archive: https://web.archive.org/web/*/https://bhyrenxing.com
site kigurumi references 2 : https://bhyrenxing.com/collections/fixed | archive: https://web.archive.org/web/*/https://bhyrenxing.com/collections/fixed
site kigurumi references 3 : https://bhyrenxing.com/products/kigurumi-mask-black-fox | archive: https://web.archive.org/web/*/https://bhyrenxing.com/products/kigurumi-mask-black-fox
site kigurumi references 4 : https://bhyrenxing.com/products/kigurumi-mask-black-wang | archive: https://web.archive.org/web/*/https://bhyrenxing.com/products/kigurumi-mask-black-wang
site kigurumi references 5 : https://bhyrenxing.com/products/kigurumi-mask-miaomiao | archive: https://web.archive.org/web/*/https://bhyrenxing.com/products/kigurumi-mask-miaomiao
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (11): https://x.com/BHYrenxing/status/2065314747533410671, https://x.com/BHYrenxing/status/2044330423854256487, https://x.com/BHYrenxing/status/2038867555549622443, https://x.com/BHYrenxing/status/2037759419422003459, https://x.com/BHYrenxing/status/2006175883673891118, https://x.com/BHYrenxing/status/2000809541534200171, https://x.com/BHYrenxing/status/1998331341423649233, https://x.com/BHYrenxing/status/1996915592851607695, https://x.com/BHYrenxing/status/1996869634511995352, https://x.com/BHYrenxing/status/1996243006073315551, https://x.com/BHYrenxing/status/1994580938425340034

maker: Black Cat Kig
region: Mainland China
site animegao references 1 : https://blackcatkig.com/pages/gallery | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/gallery
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://blackcatkig.com/ | archive: https://web.archive.org/web/*/https://blackcatkig.com/
site kigurumi references 2 : https://blackcatkig.com/collections/customize-your-mask | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/customize-your-mask
site kigurumi references 3 : https://blackcatkig.com/collections/latest-designs-from-the-past-30-days-exhibition-only-discover-the-intricate-details-and-mastercraft-behind-our-newest-kigurumi-and-zentai-additions | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/latest-designs-from-the-past-30-days-exhibition-only-discover-the-intricate-details-and-mastercraft-behind-our-newest-kigurumi-and-zentai-additions
site kigurumi references 4 : https://blackcatkig.com/collections/2026a-kig-head-shell | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/2026a-kig-head-shell
site kigurumi references 5 : https://blackcatkig.com/collections/pre-made-masks | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/pre-made-masks
site kigurumi references 6 : https://blackcatkig.com/collections/in-stock-masks | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/in-stock-masks
site kigurumi references 7 : https://blackcatkig.com/collections/hadataiskinsuit | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/hadataiskinsuit
site kigurumi references 8 : https://blackcatkig.com/collections/breast | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/breast
site kigurumi references 9 : https://blackcatkig.com/collections/accessories | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/accessories
site kigurumi references 10 : https://blackcatkig.com/pages/gallery | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/gallery
site kigurumi references 11 : https://blackcatkig.com/pages/china-joy | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/china-joy
site kigurumi references 12 : https://blackcatkig.com/pages/dw-menu | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/dw-menu
site kigurumi references 13 : https://blackcatkig.com/pages/a-notice-to-us-customers?view=bw2026 | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/a-notice-to-us-customers?view=bw2026
site kigurumi references 14 : https://blackcatkig.com/pages/order-status | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/order-status
site kigurumi references 15 : https://blackcatkig.com/collections/customize-your-mask | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/customize-your-mask
site kigurumi references 16 : https://blackcatkig.com/search?type=kigurumi-mask*&options%5Bprefix%5D=last&q=kigurumi-mask* | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?type=kigurumi-mask*&options%5Bprefix%5D=last&q=kigurumi-mask*
site kigurumi references 17 : https://blackcatkig.com/search?type=zentai*&options%5Bprefix%5D=last&q=zentai* | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?type=zentai*&options%5Bprefix%5D=last&q=zentai*
site kigurumi references 18 : https://blackcatkig.com/search?type=genshin-impact*&options%5Bprefix%5D=last&q=genshin-impact* | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?type=genshin-impact*&options%5Bprefix%5D=last&q=genshin-impact*
site kigurumi references 19 : https://blackcatkig.com/search?type=honkai-star-rail*&options%5Bprefix%5D=last&q=honkai-star-rail* | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?type=honkai-star-rail*&options%5Bprefix%5D=last&q=honkai-star-rail*
site kigurumi references 20 : https://blackcatkig.com/search?type=zenless-zone-zero*&options%5Bprefix%5D=last&q=zenless-zone-zero* | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?type=zenless-zone-zero*&options%5Bprefix%5D=last&q=zenless-zone-zero*
site kigurumi references 21 : https://blackcatkig.com/search?type=customize*&options%5Bprefix%5D=last&q=customize* | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?type=customize*&options%5Bprefix%5D=last&q=customize*
site kigurumi references 22 : https://blackcatkig.com/search?type=silicone-breastplate*&options%5Bprefix%5D=last&q=silicone-breastplate* | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?type=silicone-breastplate*&options%5Bprefix%5D=last&q=silicone-breastplate*
site kigurumi references 23 : https://blackcatkig.com/search?type=arknights*&options%5Bprefix%5D=last&q=arknights* | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?type=arknights*&options%5Bprefix%5D=last&q=arknights*
site kigurumi references 24 : https://blackcatkig.com/products/marin-kitagawa-my-dress-up-darling-kigurumi-mask-by-blackcatkig-1 | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/marin-kitagawa-my-dress-up-darling-kigurumi-mask-by-blackcatkig-1
site kigurumi references 25 : https://blackcatkig.com/collections/vendors?q=BlackCatKig%E7%8E%84%E8%B2%93%E7%89%A9%E8%AA%9E | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/vendors?q=BlackCatKig%E7%8E%84%E8%B2%93%E7%89%A9%E8%AA%9E
site kigurumi references 26 : https://blackcatkig.com/products/kurageu-roa-kurageu-roa-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kurageu-roa-kurageu-roa-kigurumi-mask-by-blackcatkig
site kigurumi references 27 : https://blackcatkig.com/products/marin-kitagawa-my-dress-up-darling-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/marin-kitagawa-my-dress-up-darling-kigurumi-mask-by-blackcatkig
site kigurumi references 28 : https://blackcatkig.com/cart | archive: https://web.archive.org/web/*/https://blackcatkig.com/cart
site kigurumi references 29 : https://blackcatkig.com/products/customize-a-kig-mask | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/customize-a-kig-mask
site kigurumi references 30 : https://blackcatkig.com/products/lacrimosa-nte-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/lacrimosa-nte-kigurumi-mask-by-blackcatkig
site kigurumi references 31 : https://blackcatkig.com/products/akiyama-mizuki-hatsune-miku-colorful-stage-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/akiyama-mizuki-hatsune-miku-colorful-stage-kigurumi-mask-by-blackcatkig
site kigurumi references 32 : https://blackcatkig.com/products/cerydra-honkai-star-rail-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/cerydra-honkai-star-rail-kigurumi-mask-by-blackcatkig
site kigurumi references 33 : https://blackcatkig.com/products/roon-azur-lane-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/roon-azur-lane-kigurumi-mask-by-blackcatkig
site kigurumi references 34 : https://blackcatkig.com/products/roxy-migurdia-mushoku-tensei-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/roxy-migurdia-mushoku-tensei-kigurumi-mask-by-blackcatkig
site kigurumi references 35 : https://blackcatkig.com/products/nana-hoshi-food-for-the-soul-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/nana-hoshi-food-for-the-soul-kigurumi-mask-by-blackcatkig
site kigurumi references 36 : https://blackcatkig.com/products/nicole-laksamana-until-then-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/nicole-laksamana-until-then-kigurumi-mask-by-blackcatkig
site kigurumi references 37 : https://blackcatkig.com/products/mobius-honkai-impact-3rd-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/mobius-honkai-impact-3rd-kigurumi-mask-by-blackcatkig
site kigurumi references 38 : https://blackcatkig.com/products/kigurumi-costume-accessories | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kigurumi-costume-accessories
site kigurumi references 39 : https://blackcatkig.com/products/ganyu-genshin-impact-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/ganyu-genshin-impact-kigurumi-mask-by-blackcatkig
site kigurumi references 40 : https://blackcatkig.com/products/shiro-no-game-no-life-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/shiro-no-game-no-life-kigurumi-mask-by-blackcatkig
site kigurumi references 41 : https://blackcatkig.com/products/selestia-vr-chat-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/selestia-vr-chat-kigurumi-mask-by-blackcatkig
x.com kigurumi references (8): https://x.com/BKC_BlacKCat/status/2084944990497894853, https://x.com/BKC_BlacKCat/status/2082778779081114053, https://x.com/BKC_BlacKCat/status/2079511506073600031, https://x.com/BKC_BlacKCat/status/2078067646327931227, https://x.com/BKC_BlacKCat/status/2075164729463775533, https://x.com/BKC_BlacKCat/status/2068988815361130851, https://x.com/BKC_BlacKCat/status/2067189602499391708, https://x.com/BKC_BlacKCat/status/2065363571605922052
x.com kigurumi hashtag-only references (11): https://x.com/BKC_BlacKCat/status/2085691343607865541, https://x.com/BKC_BlacKCat/status/2084223707103502631, https://x.com/BKC_BlacKCat/status/2082002456641499479, https://x.com/BKC_BlacKCat/status/2080478244927877473, https://x.com/BKC_BlacKCat/status/2077270706057007259, https://x.com/BKC_BlacKCat/status/2076519013937783187, https://x.com/BKC_BlacKCat/status/2073370235743121902, https://x.com/BKC_BlacKCat/status/2072626008151433463, https://x.com/BKC_BlacKCat/status/2071543647787753841, https://x.com/BKC_BlacKCat/status/2070099825459429611, https://x.com/BKC_BlacKCat/status/2066457488967553400

maker: Fantasy Masks
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (15): https://x.com/FantasyMasks_/status/1955973619697459537, https://x.com/FantasyMasks_/status/1936786617022431672, https://x.com/FantasyMasks_/status/1927681118763155950, https://x.com/FantasyMasks_/status/1925503364982612123, https://x.com/FantasyMasks_/status/1920451153214476590, https://x.com/FantasyMasks_/status/1912338112623301092, https://x.com/FantasyMasks_/status/1909881745018957864, https://x.com/FantasyMasks_/status/1904785060416675907, https://x.com/FantasyMasks_/status/1901171196562985123, https://x.com/FantasyMasks_/status/1898202273538568242, https://x.com/FantasyMasks_/status/1895308901069042083, https://x.com/FantasyMasks_/status/1892789800383459528, https://x.com/FantasyMasks_/status/1886610794764492922, https://x.com/FantasyMasks_/status/1884253880361574810, https://x.com/FantasyMasks_/status/1883202136483545366
x.com kigurumi hashtag-only references (5): https://x.com/FantasyMasks_/status/1934297057168396625, https://x.com/FantasyMasks_/status/1929133013616431436, https://x.com/FantasyMasks_/status/1921959168535134264, https://x.com/FantasyMasks_/status/1909882251435032987, https://x.com/FantasyMasks_/status/1890625366668063028

maker: Goukaou
region: Taiwan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references (10): https://x.com/goukaou/status/2085286749962645855, https://x.com/goukaou/status/2083084974660649171, https://x.com/goukaou/status/2080300622029660258, https://x.com/goukaou/status/2079141815576621308, https://x.com/goukaou/status/2078003083955912707, https://x.com/goukaou/status/2070020403490324484, https://x.com/goukaou/status/2067169158807408716, https://x.com/goukaou/status/2063987572779696172, https://x.com/goukaou/status/2060372437947334931, https://x.com/goukaou/status/2056273418157449254
site kigurumi references 1 : https://www.gko-kig.com/ | archive: https://web.archive.org/web/*/https://www.gko-kig.com/
site kigurumi references 2 : https://www.gko-kig.com/goukaou | archive: https://web.archive.org/web/*/https://www.gko-kig.com/goukaou
site kigurumi references 3 : https://www.gko-kig.com/zentai-suit | archive: https://web.archive.org/web/*/https://www.gko-kig.com/zentai-suit
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (10): https://x.com/goukaou/status/2085286749962645855, https://x.com/goukaou/status/2083084974660649171, https://x.com/goukaou/status/2080300622029660258, https://x.com/goukaou/status/2079141815576621308, https://x.com/goukaou/status/2078003083955912707, https://x.com/goukaou/status/2070020403490324484, https://x.com/goukaou/status/2067169158807408716, https://x.com/goukaou/status/2063987572779696172, https://x.com/goukaou/status/2060372437947334931, https://x.com/goukaou/status/2056273418157449254

maker: Haagaau Kigurumi Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (1): https://x.com/haagaau_GF_EN/status/1882438516879319451
x.com kigurumi hashtag-only references (1): https://x.com/haagaau_GF_EN/status/2003347284038418863

maker: Heyaoheyao
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://heyaoheyao.com/ | archive: https://web.archive.org/web/*/https://heyaoheyao.com/
site kigurumi references 2 : https://heyaoheyao.com/collections/all | archive: https://web.archive.org/web/*/https://heyaoheyao.com/collections/all
site kigurumi references 3 : https://heyaoheyao.com/collections/tights | archive: https://web.archive.org/web/*/https://heyaoheyao.com/collections/tights
site kigurumi references 4 : https://heyaoheyao.com/collections/heavy-doll-suits | archive: https://web.archive.org/web/*/https://heyaoheyao.com/collections/heavy-doll-suits
site kigurumi references 5 : https://heyaoheyao.com/collections/customize | archive: https://web.archive.org/web/*/https://heyaoheyao.com/collections/customize
site kigurumi references 6 : https://heyaoheyao.com/products/spot-products-of-heyaoheyao-kigurumi-mask-%E5%9C%A8%E5%BA%AB%E6%9C%89%E3%82%8A | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/spot-products-of-heyaoheyao-kigurumi-mask-%E5%9C%A8%E5%BA%AB%E6%9C%89%E3%82%8A
site kigurumi references 7 : https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-l-05 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-l-05
site kigurumi references 8 : https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-%E6%98%A5%E5%8D%B7-01 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-%E6%98%A5%E5%8D%B7-01
site kigurumi references 9 : https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-h-01 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-h-01
site kigurumi references 10 : https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-e | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-e
site kigurumi references 11 : https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-x-01 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-x-01
site kigurumi references 12 : https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-j-01 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-j-01
site kigurumi references 13 : https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-l-04 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-l-04
site kigurumi references 14 : https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-l-03 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-l-03
site kigurumi references 15 : https://heyaoheyao.com/collections/in-stock | archive: https://web.archive.org/web/*/https://heyaoheyao.com/collections/in-stock
site kigurumi references 16 : https://heyaoheyao.com/products/spot-products-of-heyaoheyao-kigurumi-mask-%E5%9C%A8%E5%BA%AB%E6%9C%89%E3%82%8A?variant=51117996441784 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/spot-products-of-heyaoheyao-kigurumi-mask-%E5%9C%A8%E5%BA%AB%E6%9C%89%E3%82%8A?variant=51117996441784
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)

maker: HiDolls
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (9): https://x.com/HiDolls_mm/status/2085908857671602482, https://x.com/HiDolls_mm/status/2083734529366540547, https://x.com/HiDolls_mm/status/2083372142591410643, https://x.com/HiDolls_mm/status/2082647369930387682, https://x.com/HiDolls_mm/status/2082284980517151150, https://x.com/HiDolls_mm/status/2081922591212916806, https://x.com/HiDolls_mm/status/2080835429364830243, https://x.com/HiDolls_mm/status/2080473042669687241, https://x.com/HiDolls_mm/status/2080112411701305766
x.com kigurumi hashtag-only references (10): https://x.com/HiDolls_mm/status/2086271249634705794, https://x.com/HiDolls_mm/status/2085576667959894361, https://x.com/HiDolls_mm/status/2085199179618414644, https://x.com/HiDolls_mm/status/2084821698294190179, https://x.com/HiDolls_mm/status/2084459307433631949, https://x.com/HiDolls_mm/status/2084112028634062897, https://x.com/HiDolls_mm/status/2083024864626270270, https://x.com/HiDolls_mm/status/2081575308843524481, https://x.com/HiDolls_mm/status/2081228012494983403, https://x.com/HiDolls_mm/status/2079778464115347783

maker: Kaga Kigurumi
region: Hong Kong
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://kagakii.com/ | archive: https://web.archive.org/web/*/https://kagakii.com/
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)

maker: KFY Aniplus
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (10): https://x.com/KFY_Aniplus/status/2061296681589588080, https://x.com/KFY_Aniplus/status/2057474865951805946, https://x.com/KFY_Aniplus/status/2054537859630239805, https://x.com/KFY_Aniplus/status/2051874597528592406, https://x.com/KFY_Aniplus/status/2044435302429937991, https://x.com/KFY_Aniplus/status/2036076062422241440, https://x.com/KFY_Aniplus/status/2031943265952362870, https://x.com/KFY_Aniplus/status/2029768939882868827, https://x.com/KFY_Aniplus/status/2027015870678245401, https://x.com/KFY_Aniplus/status/2018332959238156753
x.com kigurumi hashtag-only references (7): https://x.com/KFY_Aniplus/status/2060674932779200681, https://x.com/KFY_Aniplus/status/2055505652055978360, https://x.com/KFY_Aniplus/status/2051633425589961118, https://x.com/KFY_Aniplus/status/2042215946174235017, https://x.com/KFY_Aniplus/status/2035368357420261411, https://x.com/KFY_Aniplus/status/2029568547941482867, https://x.com/KFY_Aniplus/status/2020475520069115977

maker: KigLand
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://kig.land/en-US | archive: https://web.archive.org/web/*/https://kig.land/en-US
x.com kigurumi references (7): https://x.com/Remi_IO/status/2079506922462654550, https://x.com/Remi_IO/status/2079145540970070374, https://x.com/Remi_IO/status/2072619287500746827, https://x.com/Remi_IO/status/2055960272326852610, https://x.com/Remi_IO/status/2054916797468680253, https://x.com/Remi_IO/status/2052271837372100663, https://x.com/Remi_IO/status/2036040551636852881
x.com kigurumi hashtag-only references (5): https://x.com/Remi_IO/status/2082068847990046876, https://x.com/Remi_IO/status/2079870065260843337, https://x.com/Remi_IO/status/2052718675858526715, https://x.com/Remi_IO/status/2051691974726672537, https://x.com/Remi_IO/status/2043687957421609170

maker: Kirisame Factory
region: Hong Kong/Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://kirisamefactory.com/en/ | archive: https://web.archive.org/web/*/https://kirisamefactory.com/en/
site kigurumi references 2 : https://kirisamefactory.com/en/prod/mask | archive: https://web.archive.org/web/*/https://kirisamefactory.com/en/prod/mask
site kigurumi references 3 : https://kirisamefactory.com/en/legal/guide | archive: https://web.archive.org/web/*/https://kirisamefactory.com/en/legal/guide
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (10): https://x.com/KirisameFactory/status/2028072788272255212, https://x.com/KirisameFactory/status/1946505910752530504, https://x.com/KirisameFactory/status/1939210413130031581, https://x.com/KirisameFactory/status/1930917275554767235, https://x.com/KirisameFactory/status/1920781976866288120, https://x.com/KirisameFactory/status/1905231060721598974, https://x.com/KirisameFactory/status/1905230619636056245, https://x.com/KirisameFactory/status/1903444706111172787, https://x.com/KirisameFactory/status/1899016846839583102, https://x.com/KirisameFactory/status/1895794219983519776

maker: Lightning
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (19): https://x.com/lightning520/status/2004263619568263348, https://x.com/lightning520/status/1989277500539916645, https://x.com/lightning520/status/1989277268661940536, https://x.com/lightning520/status/1989277056996384769, https://x.com/lightning520/status/1989276751332348285, https://x.com/lightning520/status/1988169646684729673, https://x.com/lightning520/status/1981319161839223079, https://x.com/lightning520/status/1980292136525500662, https://x.com/lightning520/status/1978111220407509343, https://x.com/lightning520/status/1977397447975391477, https://x.com/lightning520/status/1976662274078318595, https://x.com/lightning520/status/1975218314139042053, https://x.com/lightning520/status/1974539022497353731, https://x.com/lightning520/status/1973797156709675438, https://x.com/lightning520/status/1971963523510292751, https://x.com/lightning520/status/1970864253176553662, https://x.com/lightning520/status/1970550108711461031, https://x.com/lightning520/status/1969091359412802026, https://x.com/lightning520/status/1968645307039670463

maker: MidDreamKigu
region: Mainland China
site animegao references 1 : https://kiglover.com/ | archive: https://web.archive.org/web/*/https://kiglover.com/
site animegao references 2 : https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide | archive: https://web.archive.org/web/*/https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide
site animegao references 3 : https://kiglover.com/products/kiglover-animegao-kigu-mask-quote-request | archive: https://web.archive.org/web/*/https://kiglover.com/products/kiglover-animegao-kigu-mask-quote-request
site animegao references 4 : https://kiglover.com/products/cute-little-devil-kigurumi-mask-middream-kigukiglover | archive: https://web.archive.org/web/*/https://kiglover.com/products/cute-little-devil-kigurumi-mask-middream-kigukiglover
site animegao references 5 : https://kiglover.com/products/liskarm-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/*/https://kiglover.com/products/liskarm-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site animegao references 6 : https://kiglover.com/products/w-wanted-ver-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/*/https://kiglover.com/products/w-wanted-ver-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site animegao references 7 : https://kiglover.com/products/mon3tr-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809062940/https://kiglover.com/products/mon3tr-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site animegao references 8 : https://kiglover.com/products/original-character-animegao-kigurumi-cosplay-mask-from-sea83200776-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809063027/https://kiglover.com/products/original-character-animegao-kigurumi-cosplay-mask-from-sea83200776-custom-commission-showcase-kiglover
site animegao references 9 : https://kiglover.com/products/zozzo-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809063104/https://kiglover.com/products/zozzo-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site animegao references 10 : https://kiglover.com/products/azur-lane-laffey-ii-animegao-kigurumi-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809063131/https://kiglover.com/products/azur-lane-laffey-ii-animegao-kigurumi-mask-custom-commission-showcase-kiglover
site animegao references 11 : https://kiglover.com/products/final-payment-handmake-kigu-mask-commission | archive: https://web.archive.org/web/20260809063144/https://kiglover.com/products/final-payment-handmake-kigu-mask-commission
site animegao references 12 : https://kiglover.com/products/animegao-kigu-mask-final-payment | archive: https://web.archive.org/web/20260809063205/https://kiglover.com/products/animegao-kigu-mask-final-payment
site animegao references 13 : https://kiglover.com/collections/custom-kigurumi-mask-commission-gallery-kiglover | archive: https://web.archive.org/web/20260809063320/https://kiglover.com/collections/custom-kigurumi-mask-commission-gallery-kiglover
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://kiglover.com/ | archive: https://web.archive.org/web/*/https://kiglover.com/
site kigurumi references 2 : https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide | archive: https://web.archive.org/web/*/https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide
site kigurumi references 3 : https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/choose-your-kigu-mask-wig | archive: https://web.archive.org/web/*/https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/choose-your-kigu-mask-wig
site kigurumi references 4 : https://kiglover.com/policies/shipping-policy | archive: https://web.archive.org/web/*/https://kiglover.com/policies/shipping-policy
site kigurumi references 5 : https://kiglover.com/products/kiglover-animegao-kigu-mask-quote-request | archive: https://web.archive.org/web/*/https://kiglover.com/products/kiglover-animegao-kigu-mask-quote-request
site kigurumi references 6 : https://kiglover.com/products/order-balance-for-customer-someone-xe | archive: https://web.archive.org/web/*/https://kiglover.com/products/order-balance-for-customer-someone-xe
site kigurumi references 7 : https://kiglover.com/products/cute-little-devil-kigurumi-mask-middream-kigukiglover | archive: https://web.archive.org/web/*/https://kiglover.com/products/cute-little-devil-kigurumi-mask-middream-kigukiglover
site kigurumi references 8 : https://kiglover.com/products/faust-limbus-company-kigu-mask-custom-commission-showcase-dreamweave-kigu-formerly-kiglover | archive: https://web.archive.org/web/*/https://kiglover.com/products/faust-limbus-company-kigu-mask-custom-commission-showcase-dreamweave-kigu-formerly-kiglover
site kigurumi references 9 : https://kiglover.com/products/plum-vrchat-kigu-mask-custom-commission-showcase-dreamweave-kigu-formerly-kiglover | archive: https://web.archive.org/web/*/https://kiglover.com/products/plum-vrchat-kigu-mask-custom-commission-showcase-dreamweave-kigu-formerly-kiglover
site kigurumi references 10 : https://kiglover.com/products/liskarm-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/*/https://kiglover.com/products/liskarm-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site kigurumi references 11 : https://kiglover.com/products/w-wanted-ver-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/*/https://kiglover.com/products/w-wanted-ver-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site kigurumi references 12 : https://kiglover.com/products/mon3tr-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809062940/https://kiglover.com/products/mon3tr-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site kigurumi references 13 : https://kiglover.com/products/original-character-animegao-kigurumi-cosplay-mask-from-sea83200776-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809063027/https://kiglover.com/products/original-character-animegao-kigurumi-cosplay-mask-from-sea83200776-custom-commission-showcase-kiglover
site kigurumi references 14 : https://kiglover.com/products/zozzo-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809063104/https://kiglover.com/products/zozzo-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site kigurumi references 15 : https://kiglover.com/products/azur-lane-laffey-ii-animegao-kigurumi-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809063131/https://kiglover.com/products/azur-lane-laffey-ii-animegao-kigurumi-mask-custom-commission-showcase-kiglover
site kigurumi references 16 : https://kiglover.com/products/final-payment-handmake-kigu-mask-commission | archive: https://web.archive.org/web/20260809063144/https://kiglover.com/products/final-payment-handmake-kigu-mask-commission
site kigurumi references 17 : https://kiglover.com/products/animegao-kigu-mask-final-payment | archive: https://web.archive.org/web/20260809063205/https://kiglover.com/products/animegao-kigu-mask-final-payment
site kigurumi references 18 : https://kiglover.com/collections/custom-kigurumi-mask-commission-gallery-kiglover | archive: https://web.archive.org/web/20260809063320/https://kiglover.com/collections/custom-kigurumi-mask-commission-gallery-kiglover
site kigurumi references 19 : https://kiglover.com/policies/refund-policy | archive: https://web.archive.org/web/*/https://kiglover.com/policies/refund-policy
x.com kigurumi references (1): https://x.com/kiglover_site/status/2080313221924163854
x.com kigurumi hashtag-only references (7): https://x.com/kiglover_site/status/2085427233494065240, https://x.com/kiglover_site/status/2084672638765404667, https://x.com/kiglover_site/status/2083262857450229799, https://x.com/kiglover_site/status/2082002117892456563, https://x.com/kiglover_site/status/2078912860533424294, https://x.com/kiglover_site/status/2078163058086568118, https://x.com/kiglover_site/status/2076295979741987111

maker: Natural Factory
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (10): https://x.com/NaturalFactory2/status/2086293189145841669, https://x.com/NaturalFactory2/status/2084504805322473799, https://x.com/NaturalFactory2/status/2068648413139444024, https://x.com/NaturalFactory2/status/2067117115799372175, https://x.com/NaturalFactory2/status/2065369051103478149, https://x.com/NaturalFactory2/status/2064370811830673523, https://x.com/NaturalFactory2/status/2058929448813256762, https://x.com/NaturalFactory2/status/2058126727986200958, https://x.com/NaturalFactory2/status/2056270098227450010, https://x.com/NaturalFactory2/status/2050882641067716663
x.com kigurumi hashtag-only references: none (0)

maker: New Face Doll
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://x.com/NewfacedolL | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL
site kigurumi references 2 : https://x.com/NewfacedolL/status/1731133903719784858 | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL/status/1731133903719784858
site kigurumi references 3 : https://x.com/NewfacedolL/status/1731133903719784858 | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL/status/1731133903719784858
site kigurumi references 4 : https://x.com/NewfacedolL/status/1730771515980009972 | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL/status/1730771515980009972
site kigurumi references 5 : https://x.com/NewfacedolL/status/1730771515980009972 | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL/status/1730771515980009972
site kigurumi references 6 : https://x.com/NewfacedolL/status/1730408876254605610 | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL/status/1730408876254605610
site kigurumi references 7 : https://x.com/NewfacedolL/status/1730408876254605610 | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL/status/1730408876254605610
site kigurumi references 8 : https://x.com/NewfacedolL/status/1730046237045629099 | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL/status/1730046237045629099
site kigurumi references 9 : https://x.com/NewfacedolL/status/1730046237045629099 | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL/status/1730046237045629099
site kigurumi references 10 : https://x.com/NewfacedolL/status/1729321209475822057 | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL/status/1729321209475822057
site kigurumi references 11 : https://x.com/NewfacedolL/status/1729321209475822057 | archive: https://web.archive.org/web/*/https://x.com/NewfacedolL/status/1729321209475822057
x.com kigurumi references (15): https://x.com/NewfacedolL/status/1731133903719784858, https://x.com/NewfacedolL/status/1730771515980009972, https://x.com/NewfacedolL/status/1730408876254605610, https://x.com/NewfacedolL/status/1730046237045629099, https://x.com/NewfacedolL/status/1729321209475822057, https://x.com/NewfacedolL/status/1728958569821638915, https://x.com/NewfacedolL/status/1728595930340012202, https://x.com/NewfacedolL/status/1728233039384183071, https://x.com/NewfacedolL/status/1727869896724500749, https://x.com/NewfacedolL/status/1727507258899382498, https://x.com/NewfacedolL/status/1727144617207111771, https://x.com/NewfacedolL/status/1726780971104587881, https://x.com/NewfacedolL/status/1726417282585575733, https://x.com/NewfacedolL/status/1725082656877294009, https://x.com/NewfacedolL/status/1684854432293613568
x.com kigurumi hashtag-only references (1): https://x.com/NewfacedolL/status/1615601569789267968

maker: Shinkai Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (14): https://x.com/ShinkaiWorkshop/status/2071152314824736837, https://x.com/ShinkaiWorkshop/status/2060720622968123891, https://x.com/ShinkaiWorkshop/status/2050251753002873073, https://x.com/ShinkaiWorkshop/status/2045791554925912084, https://x.com/ShinkaiWorkshop/status/2045096450712014909, https://x.com/ShinkaiWorkshop/status/2044723776039145912, https://x.com/ShinkaiWorkshop/status/2036077298667905079, https://x.com/ShinkaiWorkshop/status/2029532648717386069, https://x.com/ShinkaiWorkshop/status/2016502449037840865, https://x.com/ShinkaiWorkshop/status/2010097193907302468, https://x.com/ShinkaiWorkshop/status/2005615072266354824, https://x.com/ShinkaiWorkshop/status/2004789427059789926, https://x.com/ShinkaiWorkshop/status/2004511833315754161, https://x.com/ShinkaiWorkshop/status/2003450879312343529

maker: Build Up Studio SIGMA
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://www.buildupstudiosigma.com/gallery/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/gallery/
site kigurumi references 2 : https://www.buildupstudiosigma.com/gallery/twinangel/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/gallery/twinangel/
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)

maker: Scarlet0rabbit
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (2): https://x.com/Scarlet0rabbit/status/1928374234864132544, https://x.com/Scarlet0rabbit/status/1903033375021208032
x.com kigurumi hashtag-only references (17): https://x.com/Scarlet0rabbit/status/2082821855417860509, https://x.com/Scarlet0rabbit/status/2082821437422030868, https://x.com/Scarlet0rabbit/status/2082821140096188894, https://x.com/Scarlet0rabbit/status/2036390960570216583, https://x.com/Scarlet0rabbit/status/1987915653584666675, https://x.com/Scarlet0rabbit/status/1979785083956625876, https://x.com/Scarlet0rabbit/status/1978878813259112470, https://x.com/Scarlet0rabbit/status/1960726357010473166, https://x.com/Scarlet0rabbit/status/1944604966200688980, https://x.com/Scarlet0rabbit/status/1935968594372051380, https://x.com/Scarlet0rabbit/status/1932316370211135969, https://x.com/Scarlet0rabbit/status/1932070426701861184, https://x.com/Scarlet0rabbit/status/1929477229232132254, https://x.com/Scarlet0rabbit/status/1921040108934807869, https://x.com/Scarlet0rabbit/status/1916517052711424327, https://x.com/Scarlet0rabbit/status/1911067982966501633, https://x.com/Scarlet0rabbit/status/1910176001101091210

maker: W Rabbit Mi
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (4): https://x.com/WithRabbitMI/status/1840017154286202924, https://x.com/WithRabbitMI/status/1806952419890192519, https://x.com/WithRabbitMI/status/1798649480293871875, https://x.com/WithRabbitMI/status/1798615646357582062
x.com kigurumi hashtag-only references: none (0)

maker: A2 Laboratory
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (2): https://x.com/A2Laboratory/status/1892091641961320502, https://x.com/A2Laboratory/status/1892092101162049696
x.com kigurumi hashtag-only references: none (0)

maker: BEADOLL
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (1): https://x.com/BEADOLL_OS/status/2031627635709665722
x.com kigurumi hashtag-only references (11): https://x.com/BEADOLL_OS/status/2049853638051537111, https://x.com/BEADOLL_OS/status/2049853155891155315, https://x.com/BEADOLL_OS/status/2048763900745970064, https://x.com/BEADOLL_OS/status/2032020752460104046, https://x.com/BEADOLL_OS/status/2031720878975905869, https://x.com/BEADOLL_OS/status/2031432774461374527, https://x.com/BEADOLL_OS/status/2028439700210581871, https://x.com/BEADOLL_OS/status/2020824996093038684, https://x.com/BEADOLL_OS/status/2020819364291702917, https://x.com/BEADOLL_OS/status/2016855261848490371, https://x.com/BEADOLL_OS/status/2016850218588000414

maker: Bear Technique Studio
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (3): https://x.com/BearTechCenter/status/2082460192105746775, https://x.com/BearTechCenter/status/2076311453334929725, https://x.com/BearTechCenter/status/2073694080828334307
x.com kigurumi hashtag-only references (16): https://x.com/BearTechCenter/status/2081049618625032559, https://x.com/BearTechCenter/status/2080657980337627250, https://x.com/BearTechCenter/status/2079151063131902252, https://x.com/BearTechCenter/status/2077784180956762380, https://x.com/BearTechCenter/status/2075568438924415073, https://x.com/BearTechCenter/status/2075201629180273109, https://x.com/BearTechCenter/status/2074864795447386398, https://x.com/BearTechCenter/status/2074126987724300323, https://x.com/BearTechCenter/status/2073313869481836818, https://x.com/BearTechCenter/status/2073056460897185845, https://x.com/BearTechCenter/status/2071969229751156979, https://x.com/BearTechCenter/status/2071511294793126360, https://x.com/BearTechCenter/status/2070878703186587785, https://x.com/BearTechCenter/status/2070521513334415777, https://x.com/BearTechCenter/status/2069805104279265662, https://x.com/BearTechCenter/status/2069035308738658457

maker: Chris and Meph
region: Canada
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://chrisandmeph.com/about/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/about/
site kigurumi references 2 : https://chrisandmeph.com/author/ctriff/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/author/ctriff/
site kigurumi references 3 : https://chrisandmeph.com/2022/04/30/lets-kick-this-old-school-with-trouble/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/2022/04/30/lets-kick-this-old-school-with-trouble/
site kigurumi references 4 : https://chrisandmeph.com/2022/04/27/here-comes-trouble/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/2022/04/27/here-comes-trouble/
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (4): https://x.com/ChrisAndMeph/status/2078287380860289290, https://x.com/ChrisAndMeph/status/1642665156714049537, https://x.com/ChrisAndMeph/status/1574121244819333120, https://x.com/ChrisAndMeph/status/1520602848752377856

maker: Cover
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (4): https://x.com/cover_plan/status/2081731109587698013, https://x.com/cover_plan/status/2081730916943299059, https://x.com/cover_plan/status/2081729936826732592, https://x.com/cover_plan/status/2081729394612261354
x.com kigurumi hashtag-only references (16): https://x.com/cover_plan/status/2086116867325018158, https://x.com/cover_plan/status/2086102206013641096, https://x.com/cover_plan/status/2085706582730723766, https://x.com/cover_plan/status/2085057296091299964, https://x.com/cover_plan/status/2084702389165338887, https://x.com/cover_plan/status/2084602384828043642, https://x.com/cover_plan/status/2084195475708919968, https://x.com/cover_plan/status/2083275420473114980, https://x.com/cover_plan/status/2082463092949287081, https://x.com/cover_plan/status/2081249566188540156, https://x.com/cover_plan/status/2080716890352361674, https://x.com/cover_plan/status/2080200773858992337, https://x.com/cover_plan/status/2079808875780522395, https://x.com/cover_plan/status/2079421339375714652, https://x.com/cover_plan/status/2078932773818298480, https://x.com/cover_plan/status/2078549979669713317

maker: DAME Kigurumi
region: UK
site animegao references 1 : https://damekigurumi.com/ | archive: https://web.archive.org/web/20260809063546/https://damekigurumi.com/
site animegao references 2 : https://damekigurumi.com/Home | archive: https://web.archive.org/web/*/https://damekigurumi.com/Home
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://damekigurumi.com/ | archive: https://web.archive.org/web/20260809063546/https://damekigurumi.com/
site kigurumi references 2 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 3 : https://damekigurumi.com/Register | archive: https://web.archive.org/web/*/https://damekigurumi.com/Register
site kigurumi references 4 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 5 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 6 : https://damekigurumi.com/Cart | archive: https://web.archive.org/web/*/https://damekigurumi.com/Cart
site kigurumi references 7 : https://damekigurumi.com/Cart | archive: https://web.archive.org/web/*/https://damekigurumi.com/Cart
site kigurumi references 8 : https://damekigurumi.com/Home | archive: https://web.archive.org/web/*/https://damekigurumi.com/Home
site kigurumi references 9 : https://damekigurumi.com/Masks | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks
site kigurumi references 10 : https://damekigurumi.com/Masks/Gen-3 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3
site kigurumi references 11 : https://damekigurumi.com/Masks/Gen-2 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-2
site kigurumi references 12 : https://damekigurumi.com/Components | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components
site kigurumi references 13 : https://damekigurumi.com/Components/Shells | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Shells
site kigurumi references 14 : https://damekigurumi.com/Components/Eyes | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Eyes
site kigurumi references 15 : https://damekigurumi.com/Components/Wigs | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Wigs
site kigurumi references 16 : https://damekigurumi.com/Accessories | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories
site kigurumi references 17 : https://damekigurumi.com/Accessories/Hair | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/Hair
site kigurumi references 18 : https://damekigurumi.com/Accessories/Hats | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/Hats
site kigurumi references 19 : https://damekigurumi.com/Skinsuits | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits
site kigurumi references 20 : https://damekigurumi.com/Skinsuits/Suits | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Suits
site kigurumi references 21 : https://damekigurumi.com/Skinsuits/Samples | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Samples
site kigurumi references 22 : https://damekigurumi.com/Skinsuits/Extras | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Extras
site kigurumi references 23 : https://damekigurumi.com/Shapeware | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware
site kigurumi references 24 : https://damekigurumi.com/Shapeware/Breast-Forms | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/Breast-Forms
site kigurumi references 25 : https://damekigurumi.com/Shapeware/Hip-Padding | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/Hip-Padding
site kigurumi references 26 : https://damekigurumi.com/ReadyToShip | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip
site kigurumi references 27 : https://damekigurumi.com/ReadyToShip/Ready-Masks | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/Ready-Masks
site kigurumi references 28 : https://damekigurumi.com/ReadyToShip/Ready-Components | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/Ready-Components
site kigurumi references 29 : https://damekigurumi.com/ReadyToShip/Ready-Accessories | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/Ready-Accessories
site kigurumi references 30 : https://damekigurumi.com/ReadyToShip/Ready-Skinsuits | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/Ready-Skinsuits
site kigurumi references 31 : https://damekigurumi.com/ReadyToShip/Ready-Shapeware | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/Ready-Shapeware
site kigurumi references 32 : https://damekigurumi.com/Blog/Guides | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guides
site kigurumi references 33 : https://damekigurumi.com/Blog/Guides/Backplate-Attachment-Guide | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guides/Backplate-Attachment-Guide
site kigurumi references 34 : https://damekigurumi.com/Blog/Guides/Guide-Mask-Care | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guides/Guide-Mask-Care
site kigurumi references 35 : https://damekigurumi.com/Blog/Guides/Mask-Padding-Guide | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guides/Mask-Padding-Guide
site kigurumi references 36 : https://damekigurumi.com/Blog/Guides/Plaster-and-Plaits | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guides/Plaster-and-Plaits
site kigurumi references 37 : https://damekigurumi.com/Blog/Guides/Guide-Skinsuit-Maintenance | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guides/Guide-Skinsuit-Maintenance
site kigurumi references 38 : https://damekigurumi.com/Blog/Guides/Guide-Wig-Tutorial | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guides/Guide-Wig-Tutorial
site kigurumi references 39 : https://damekigurumi.com/Gallery | archive: https://web.archive.org/web/*/https://damekigurumi.com/Gallery
site kigurumi references 40 : https://damekigurumi.com/Blog | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog
site kigurumi references 41 : https://damekigurumi.com/Contact-Us | archive: https://web.archive.org/web/*/https://damekigurumi.com/Contact-Us
x.com kigurumi references (1): https://x.com/damekigurumi/status/2048811563121803521
x.com kigurumi hashtag-only references: none (0)

maker: Dora Studio
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (6): https://x.com/DoraKigStudio/status/1832364332275134834, https://x.com/DoraKigStudio/status/1830492360335343935, https://x.com/DoraKigStudio/status/1829733577380282593, https://x.com/DoraKigStudio/status/1825035976923865383, https://x.com/DoraKigStudio/status/1825035782358532210, https://x.com/DoraKigStudio/status/1825034722860474819

maker: ELYSIUM
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (5): https://x.com/ELYSIUM1688/status/2051563563614154835, https://x.com/ELYSIUM1688/status/1809809332026110187, https://x.com/ELYSIUM1688/status/1708371210109923442, https://x.com/ELYSIUM1688/status/1704392916347797975, https://x.com/ELYSIUM1688/status/1660097738120511490

maker: Haka Renxing
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (17): https://x.com/hakarenxin99/status/1926910081343381629, https://x.com/hakarenxin99/status/1926661066206896396, https://x.com/hakarenxin99/status/1926221236952068320, https://x.com/hakarenxin99/status/1925887054384124148, https://x.com/hakarenxin99/status/1925506693255073890, https://x.com/hakarenxin99/status/1925200300257968347, https://x.com/hakarenxin99/status/1924103920961585378, https://x.com/hakarenxin99/status/1923015853588594735, https://x.com/hakarenxin99/status/1921938479350456702, https://x.com/hakarenxin99/status/1921142662754660422, https://x.com/hakarenxin99/status/1919016596124975380, https://x.com/hakarenxin99/status/1918647442553377209, https://x.com/hakarenxin99/status/1917561050679107786, https://x.com/hakarenxin99/status/1916084865185026543, https://x.com/hakarenxin99/status/1913400833263427865, https://x.com/hakarenxin99/status/1912144310860124318, https://x.com/hakarenxin99/status/1911756104243286115

maker: Harinezumi Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (9): https://x.com/harinezumiws/status/2085191390632476899, https://x.com/harinezumiws/status/2069432009857159337, https://x.com/harinezumiws/status/2067149718279582037, https://x.com/harinezumiws/status/2066542732433342794, https://x.com/harinezumiws/status/2029570354348441778, https://x.com/harinezumiws/status/2022829255265251543, https://x.com/harinezumiws/status/2021977130171818233, https://x.com/harinezumiws/status/2021541435678560365, https://x.com/harinezumiws/status/2021237327327109436

maker: Huyaoshouzuo
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (1): https://x.com/Huyaoshouzuo/status/2013223958405890271
x.com kigurumi hashtag-only references (16): https://x.com/Huyaoshouzuo/status/2075101335553511501, https://x.com/Huyaoshouzuo/status/2075101088202858626, https://x.com/Huyaoshouzuo/status/2044595312518721795, https://x.com/Huyaoshouzuo/status/2044592754538479651, https://x.com/Huyaoshouzuo/status/2043494600611172465, https://x.com/Huyaoshouzuo/status/2043489059826541022, https://x.com/Huyaoshouzuo/status/2043487584563933673, https://x.com/Huyaoshouzuo/status/2043479710605377986, https://x.com/Huyaoshouzuo/status/2016736542191157266, https://x.com/Huyaoshouzuo/status/2015751970867548570, https://x.com/Huyaoshouzuo/status/2015453121842188406, https://x.com/Huyaoshouzuo/status/2013285347791089859, https://x.com/Huyaoshouzuo/status/2013274554878062716, https://x.com/Huyaoshouzuo/status/2009317518591316256, https://x.com/Huyaoshouzuo/status/2009316925684457733, https://x.com/Huyaoshouzuo/status/2009099543204577572

maker: Iris Kigurumi
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (2): https://x.com/IrisKigurumi/status/1943634270523633985, https://x.com/IrisKigurumi/status/1863124940565959034
x.com kigurumi hashtag-only references (7): https://x.com/IrisKigurumi/status/1941052561378992509, https://x.com/IrisKigurumi/status/1928680330833043794, https://x.com/IrisKigurumi/status/1923229317334507949, https://x.com/IrisKigurumi/status/1921433694570512411, https://x.com/IrisKigurumi/status/1893862358247768515, https://x.com/IrisKigurumi/status/1891414173277405437, https://x.com/IrisKigurumi/status/1888818037618606326

maker: Justin Bailey
region: Canada
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : http://justinbailey2430.blogspot.com/ | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/
site kigurumi references 2 : http://justinbailey2430.blogspot.com/p/products.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/p/products.html
site kigurumi references 3 : http://justinbailey2430.blogspot.com/p/contact.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/p/contact.html
site kigurumi references 4 : http://justinbailey2430.blogspot.com/2018/08/social-media-pagesprofiles.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2018/08/social-media-pagesprofiles.html
site kigurumi references 5 : http://justinbailey2430.blogspot.com/2015/11/pictures-from-otafest-aurora-lina.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/11/pictures-from-otafest-aurora-lina.html
site kigurumi references 6 : http://justinbailey2430.blogspot.com/2015/11/starting-on-lina-inverse-custom.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/11/starting-on-lina-inverse-custom.html
site kigurumi references 7 : http://justinbailey2430.blogspot.com/2015/11/photos-from-animethon-and-recent.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/11/photos-from-animethon-and-recent.html
site kigurumi references 8 : http://justinbailey2430.blogspot.com/2015/10/new-version-of-erika-mostly-complete.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/10/new-version-of-erika-mostly-complete.html
site kigurumi references 9 : http://justinbailey2430.blogspot.com/search?updated-max=2015-10-16T23:36:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2015-10-16T23:36:00-07:00&max-results=7
site kigurumi references 10 : http://justinbailey2430.blogspot.com/2018 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2018
site kigurumi references 11 : http://justinbailey2430.blogspot.com/2018/08 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2018/08
site kigurumi references 12 : http://justinbailey2430.blogspot.com/2015 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015
site kigurumi references 13 : http://justinbailey2430.blogspot.com/2015/11 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/11
site kigurumi references 14 : http://justinbailey2430.blogspot.com/2015/10 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/10
site kigurumi references 15 : http://justinbailey2430.blogspot.com/2015/06 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/06
site kigurumi references 16 : http://justinbailey2430.blogspot.com/2015/04 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/04
site kigurumi references 17 : http://justinbailey2430.blogspot.com/2015/01 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/01
site kigurumi references 18 : http://justinbailey2430.blogspot.com/2014 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014
site kigurumi references 19 : http://justinbailey2430.blogspot.com/2014/11 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/11
site kigurumi references 20 : http://justinbailey2430.blogspot.com/2014/10 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/10
site kigurumi references 21 : http://justinbailey2430.blogspot.com/2014/09 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/09
site kigurumi references 22 : http://justinbailey2430.blogspot.com/2014/08 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/08
site kigurumi references 23 : http://justinbailey2430.blogspot.com/2014/07 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/07
site kigurumi references 24 : http://justinbailey2430.blogspot.com/2014/06 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/06
site kigurumi references 25 : http://justinbailey2430.blogspot.com/2014/05 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/05
site kigurumi references 26 : http://justinbailey2430.blogspot.com/2014/04 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/04
site kigurumi references 27 : http://justinbailey2430.blogspot.com/2014/03 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/03
site kigurumi references 28 : http://justinbailey2430.blogspot.com/2014/02 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/02
site kigurumi references 29 : http://justinbailey2430.blogspot.com/2014/01 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/01
site kigurumi references 30 : http://justinbailey2430.blogspot.com/2013 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013
site kigurumi references 31 : http://justinbailey2430.blogspot.com/2013/12 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/12
site kigurumi references 32 : http://justinbailey2430.blogspot.com/2013/11 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/11
site kigurumi references 33 : http://justinbailey2430.blogspot.com/2013/10 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/10
site kigurumi references 34 : http://justinbailey2430.blogspot.com/2013/09 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/09
site kigurumi references 35 : http://justinbailey2430.blogspot.com/2013/08 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/08
site kigurumi references 36 : http://justinbailey2430.blogspot.com/2013/07 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/07
x.com kigurumi references (2): https://x.com/justinbailey243/status/2057725590531342340, https://x.com/justinbailey243/status/2057724442470711723
x.com kigurumi hashtag-only references (1): https://x.com/justinbailey243/status/2084155383388770712

maker: KaikaSakura Art
region: USA
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (14): https://x.com/KaikaKigu/status/2080790578908876869, https://x.com/KaikaKigu/status/2080022369771442598, https://x.com/KaikaKigu/status/2078857771848548421, https://x.com/KaikaKigu/status/2077513804682818047, https://x.com/KaikaKigu/status/2076667713963938051, https://x.com/KaikaKigu/status/2074131856174268727, https://x.com/KaikaKigu/status/2071963941220106625, https://x.com/KaikaKigu/status/2069801686659375610, https://x.com/KaikaKigu/status/2068684645412069510, https://x.com/KaikaKigu/status/2066533785869435344, https://x.com/KaikaKigu/status/2064456108215787742, https://x.com/KaikaKigu/status/2062945592557384039, https://x.com/KaikaKigu/status/2061527226823086326, https://x.com/KaikaKigu/status/2060338090405732473

maker: KigCos
region: Australia & Singapore
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (13): https://x.com/wyukig/status/2085994299553186084, https://x.com/wyukig/status/2084245523658395860, https://x.com/wyukig/status/2082107571868213533, https://x.com/wyukig/status/2082099269218226677, https://x.com/wyukig/status/2082058623250047284, https://x.com/wyukig/status/2081364334257799534, https://x.com/wyukig/status/2081171257614323926, https://x.com/wyukig/status/2081014152714440990, https://x.com/wyukig/status/2080692672432636264, https://x.com/wyukig/status/2080668973981724866, https://x.com/wyukig/status/2080644822302658809, https://x.com/wyukig/status/2080616498151014838, https://x.com/wyukig/status/2080280030874095811

maker: Kigmask
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (18): https://x.com/kig_mask/status/1821122006554939404, https://x.com/kig_mask/status/1819721878925459858, https://x.com/kig_mask/status/1819721729020932324, https://x.com/kig_mask/status/1819721593398120495, https://x.com/kig_mask/status/1819721448946319547, https://x.com/kig_mask/status/1819721345267355769, https://x.com/kig_mask/status/1819721201792712862, https://x.com/kig_mask/status/1728816548209635542, https://x.com/kig_mask/status/1727998350916755703, https://x.com/kig_mask/status/1705819959233065171, https://x.com/kig_mask/status/1687024725032382464, https://x.com/kig_mask/status/1682077725711040514, https://x.com/kig_mask/status/1681709904443359232, https://x.com/kig_mask/status/1678378466939658241, https://x.com/kig_mask/status/1678377532373241856, https://x.com/kig_mask/status/1646880722802855938, https://x.com/kig_mask/status/1642457898528935937, https://x.com/kig_mask/status/1638914384222392324

maker: Kigurumi Factory
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (9): https://x.com/sks1094/status/2013900754290090057, https://x.com/sks1094/status/1983130502094528787, https://x.com/sks1094/status/1974141004006736278, https://x.com/sks1094/status/1954834127330693417, https://x.com/sks1094/status/1941117381570654337, https://x.com/sks1094/status/1936681154440204416, https://x.com/sks1094/status/1904526397936460135, https://x.com/sks1094/status/1900123783027188162, https://x.com/sks1094/status/1879457264274387335

maker: Kigurumi Settings
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (1): https://x.com/Kig_Settings/status/1978324347338010706

maker: Kiguyobi
region: Taiwan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (1): https://x.com/kiguyobi/status/1896553141757477247
x.com kigurumi hashtag-only references: none (0)

maker: KIGzhz
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (3): https://x.com/kigzhzchafan/status/2066450746032398690, https://x.com/kigzhzchafan/status/2066424210105487528, https://x.com/kigzhzchafan/status/1913774254329627015
x.com kigurumi hashtag-only references: none (0)

maker: King Mask Studio
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (7): https://x.com/KingMask_studio/status/2078342535790154109, https://x.com/KingMask_studio/status/2068521995915202587, https://x.com/KingMask_studio/status/2057001568424309157, https://x.com/KingMask_studio/status/2049830862016184667, https://x.com/KingMask_studio/status/2049020152616997358, https://x.com/KingMask_studio/status/2034537849480241578, https://x.com/KingMask_studio/status/2033564603343688055

maker: Kuroneko Mask Shop
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (6): https://x.com/kuroneko_mask/status/2077568174594429198, https://x.com/kuroneko_mask/status/2077567029599691071, https://x.com/kuroneko_mask/status/2077566184900464975, https://x.com/kuroneko_mask/status/2061436563742150732, https://x.com/kuroneko_mask/status/2019596504529551747, https://x.com/kuroneko_mask/status/2019597781619601682

maker: Laoshu Zone
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (17): https://x.com/zone_rk3ly/status/2086078584561787160, https://x.com/zone_rk3ly/status/2075569158075682856, https://x.com/zone_rk3ly/status/2073004390932463865, https://x.com/zone_rk3ly/status/2070486101551395028, https://x.com/zone_rk3ly/status/2062873959893491979, https://x.com/zone_rk3ly/status/2055255148935668075, https://x.com/zone_rk3ly/status/2053116495270678674, https://x.com/zone_rk3ly/status/2048559953397637275, https://x.com/zone_rk3ly/status/2035004995607953542, https://x.com/zone_rk3ly/status/2032426927680803234, https://x.com/zone_rk3ly/status/2027763329394212912, https://x.com/zone_rk3ly/status/2022293077159993791, https://x.com/zone_rk3ly/status/2019750981332857089, https://x.com/zone_rk3ly/status/2019372356914053216, https://x.com/zone_rk3ly/status/2018654646555045980, https://x.com/zone_rk3ly/status/2009599419554185595, https://x.com/zone_rk3ly/status/1999667217525625129
x.com kigurumi hashtag-only references: none (0)

maker: Lucky Larus
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (3): https://x.com/Larus_kigurumi/status/2054603916617424901, https://x.com/Larus_kigurumi/status/2054254377473577303, https://x.com/Larus_kigurumi/status/2052420458285617542

maker: Magic Doll
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (4): https://x.com/MagicDoll1208/status/2012915517217014172, https://x.com/MagicDoll1208/status/2011447704594051293, https://x.com/MagicDoll1208/status/2011114887054082201, https://x.com/MagicDoll1208/status/1963834270541382113

maker: Maple Studio
region: Thailand
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (3): https://x.com/milkpockydoll/status/2079493141975937494, https://x.com/milkpockydoll/status/1988487357017043071, https://x.com/milkpockydoll/status/1983115902016213079
x.com kigurumi hashtag-only references (10): https://x.com/milkpockydoll/status/2083976124854624708, https://x.com/milkpockydoll/status/2083251348946944402, https://x.com/milkpockydoll/status/2080154665862451447, https://x.com/milkpockydoll/status/2058161900299649052, https://x.com/milkpockydoll/status/2057330546045497359, https://x.com/milkpockydoll/status/1993313373526892988, https://x.com/milkpockydoll/status/1991876356863611053, https://x.com/milkpockydoll/status/1983106379167764527, https://x.com/milkpockydoll/status/1970292033328652442, https://x.com/milkpockydoll/status/1969929641835327519

maker: Mirrodoll
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (3): https://x.com/mirrodoll/status/1963962594097860906, https://x.com/mirrodoll/status/1950885814742970764, https://x.com/mirrodoll/status/1950521320011407527
x.com kigurumi hashtag-only references (10): https://x.com/mirrodoll/status/1978061850869649895, https://x.com/mirrodoll/status/1977699343026024598, https://x.com/mirrodoll/status/1977014968370577677, https://x.com/mirrodoll/status/1976674222761230707, https://x.com/mirrodoll/status/1970804103438901708, https://x.com/mirrodoll/status/1960725743648039045, https://x.com/mirrodoll/status/1951279273051848917, https://x.com/mirrodoll/status/1948368162023518630, https://x.com/mirrodoll/status/1946846963690811902, https://x.com/mirrodoll/status/1946579679600881766

maker: Miaomiaoxing
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (20): https://x.com/mjnln274668/status/2084943390500876794, https://x.com/mjnln274668/status/2084492475759267899, https://x.com/mjnln274668/status/2081710699290804527, https://x.com/mjnln274668/status/2080895308603797668, https://x.com/mjnln274668/status/2080151051895013429, https://x.com/mjnln274668/status/2079517392103973145, https://x.com/mjnln274668/status/2078353838038487276, https://x.com/mjnln274668/status/2077704224377594049, https://x.com/mjnln274668/status/2075550430227292623, https://x.com/mjnln274668/status/2069438550282846471, https://x.com/mjnln274668/status/2067200300537319516, https://x.com/mjnln274668/status/2064004523933548567, https://x.com/mjnln274668/status/2057709523994042768, https://x.com/mjnln274668/status/2056675511729041614, https://x.com/mjnln274668/status/2054467521663906290, https://x.com/mjnln274668/status/2053058465086742874, https://x.com/mjnln274668/status/2051601938316398839, https://x.com/mjnln274668/status/2048754459220787203, https://x.com/mjnln274668/status/2043309980678582759, https://x.com/mjnln274668/status/2040803757236371817

maker: Moyu Kig
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (15): https://x.com/MoyuKig/status/2086274515445686304, https://x.com/MoyuKig/status/2085181362215276737, https://x.com/MoyuKig/status/2080245764882899144, https://x.com/MoyuKig/status/2079769625445962007, https://x.com/MoyuKig/status/2079139635918512482, https://x.com/MoyuKig/status/2078366659761623335, https://x.com/MoyuKig/status/2078002736751386664, https://x.com/MoyuKig/status/2077304075310477451, https://x.com/MoyuKig/status/2076973987507339286, https://x.com/MoyuKig/status/2075073310547963905, https://x.com/MoyuKig/status/2074488888824090909, https://x.com/MoyuKig/status/2074105126210695678, https://x.com/MoyuKig/status/2073370773411320103, https://x.com/MoyuKig/status/2072277118961226177, https://x.com/MoyuKig/status/2071905901439812032

maker: MRKT
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (6): https://x.com/IceKKKMID/status/1974625741255094525, https://x.com/IceKKKMID/status/1970797936465571975, https://x.com/IceKKKMID/status/1970797742290329998, https://x.com/IceKKKMID/status/1970797363087446296, https://x.com/IceKKKMID/status/1956302291549507965, https://x.com/IceKKKMID/status/1880893298036048054
x.com kigurumi hashtag-only references (6): https://x.com/IceKKKMID/status/1953739168577904897, https://x.com/IceKKKMID/status/1953738315175539176, https://x.com/IceKKKMID/status/1953737755047170083, https://x.com/IceKKKMID/status/1825556958147141898, https://x.com/IceKKKMID/status/1817084770037432361, https://x.com/IceKKKMID/status/1816296046940807550

maker: Munimuni Works
region: Japan
site animegao references 1 : https://www.munimuni.jp/p/00015 | archive: https://web.archive.org/web/20260809063938/https://www.munimuni.jp/p/00015
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://www.munimuni.jp/categories/4511657 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/categories/4511657
site kigurumi references 2 : https://www.munimuni.jp/categories/4511695 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/categories/4511695
site kigurumi references 3 : https://www.munimuni.jp/categories/4511698 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/categories/4511698
site kigurumi references 4 : https://www.munimuni.jp/p/00015 | archive: https://web.archive.org/web/20260809063938/https://www.munimuni.jp/p/00015
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)

maker: Mzdodo
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (7): https://x.com/Mzdodo599/status/2083388346060144794, https://x.com/Mzdodo599/status/2080837309377941824, https://x.com/Mzdodo599/status/2070909511112814664, https://x.com/Mzdodo599/status/2060370062109032653, https://x.com/Mzdodo599/status/2045781965530640582, https://x.com/Mzdodo599/status/2034611726512185374, https://x.com/Mzdodo599/status/2031954292299743721

maker: Nekotofu
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (19): https://x.com/nekotoufufu/status/2085641036827931091, https://x.com/nekotoufufu/status/2085276356322201698, https://x.com/nekotoufufu/status/2084944298064384491, https://x.com/nekotoufufu/status/2083458242479628793, https://x.com/nekotoufufu/status/2082807880655532437, https://x.com/nekotoufufu/status/2072271746003239314, https://x.com/nekotoufufu/status/2069182840877863263, https://x.com/nekotoufufu/status/2068206834423673143, https://x.com/nekotoufufu/status/2067907932726153726, https://x.com/nekotoufufu/status/2067523562110615604, https://x.com/nekotoufufu/status/2067106837791682872, https://x.com/nekotoufufu/status/2066647530394571203, https://x.com/nekotoufufu/status/2062848250118611415, https://x.com/nekotoufufu/status/2061681926554202382, https://x.com/nekotoufufu/status/2054784241142206668, https://x.com/nekotoufufu/status/2054396688580886613, https://x.com/nekotoufufu/status/2051898739523203137, https://x.com/nekotoufufu/status/2049421781166080356, https://x.com/nekotoufufu/status/2046222613748629682

maker: NM Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (2): https://x.com/nonhumanmasque/status/2013133151099666799, https://x.com/nonhumanmasque/status/1919232163435724993
x.com kigurumi hashtag-only references (11): https://x.com/nonhumanmasque/status/1963522358834323807, https://x.com/nonhumanmasque/status/1919936650743775456, https://x.com/nonhumanmasque/status/1914673682800349624, https://x.com/nonhumanmasque/status/1906862709544534163, https://x.com/nonhumanmasque/status/1906566717662216633, https://x.com/nonhumanmasque/status/1901266012575588616, https://x.com/nonhumanmasque/status/1900540128294031570, https://x.com/nonhumanmasque/status/1883967112961745090, https://x.com/nonhumanmasque/status/1877656826793095623, https://x.com/nonhumanmasque/status/1876797637824770273, https://x.com/nonhumanmasque/status/1876660674455114050

maker: Meis
region: Mainland China
site animegao references 1 : https://www.kigis.me/kigurumi | archive: https://web.archive.org/web/20260809064034/https://www.kigis.me/kigurumi
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://www.kigis.me/pinhaotou/ | archive: https://web.archive.org/web/*/https://www.kigis.me/pinhaotou/
site kigurumi references 2 : https://www.kigis.me/ | archive: https://web.archive.org/web/*/https://www.kigis.me/
site kigurumi references 3 : https://www.kigis.me/dolleveryday | archive: https://web.archive.org/web/*/https://www.kigis.me/dolleveryday
site kigurumi references 4 : https://www.kigis.me/piece | archive: https://web.archive.org/web/*/https://www.kigis.me/piece
site kigurumi references 5 : https://www.kigis.me/pht-01 | archive: https://web.archive.org/web/*/https://www.kigis.me/pht-01
site kigurumi references 6 : https://www.kigis.me/pht-02 | archive: https://web.archive.org/web/*/https://www.kigis.me/pht-02
site kigurumi references 7 : https://www.kigis.me/pht-03 | archive: https://web.archive.org/web/*/https://www.kigis.me/pht-03
site kigurumi references 8 : https://www.kigis.me/pht-04 | archive: https://web.archive.org/web/*/https://www.kigis.me/pht-04
site kigurumi references 9 : https://www.kigis.me/pht-05 | archive: https://web.archive.org/web/*/https://www.kigis.me/pht-05
site kigurumi references 10 : https://www.kigis.me/query | archive: https://web.archive.org/web/*/https://www.kigis.me/query
site kigurumi references 11 : https://www.kigis.me/contact | archive: https://web.archive.org/web/*/https://www.kigis.me/contact
site kigurumi references 12 : https://www.kigis.me/kigurumi | archive: https://web.archive.org/web/20260809064034/https://www.kigis.me/kigurumi
site kigurumi references 13 : https://www.kigis.me/about | archive: https://web.archive.org/web/*/https://www.kigis.me/about
site kigurumi references 14 : https://www.kigis.me/sitemap.xml | archive: https://web.archive.org/web/*/https://www.kigis.me/sitemap.xml
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (1): https://x.com/pinhaotou/status/2020148898203890151

maker: Raigeki Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (3): https://x.com/RAIGEKI_Li/status/2057147724118765707, https://x.com/RAIGEKI_Li/status/1984626024777462203, https://x.com/RAIGEKI_Li/status/1977391567523512654

maker: Salmon Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (17): https://x.com/samon_ii/status/2075917093132984443, https://x.com/samon_ii/status/2074450991601406402, https://x.com/samon_ii/status/2066069362264666305, https://x.com/samon_ii/status/2062765017192407542, https://x.com/samon_ii/status/2059530339429790009, https://x.com/samon_ii/status/2058865919049580839, https://x.com/samon_ii/status/2054152694529769850, https://x.com/samon_ii/status/2053128608739381399, https://x.com/samon_ii/status/2051546867855745430, https://x.com/samon_ii/status/2041871706244182070, https://x.com/samon_ii/status/2041723768662532136, https://x.com/samon_ii/status/2035222960978764144, https://x.com/samon_ii/status/2034608227107889561, https://x.com/samon_ii/status/2031950588192477631, https://x.com/samon_ii/status/2028778541316493485, https://x.com/samon_ii/status/1982746644539163013, https://x.com/samon_ii/status/1978337667621290119

maker: Shuijing Renxing
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (4): https://x.com/SJrenxing/status/1934542097321021851, https://x.com/SJrenxing/status/1934388759342232055, https://x.com/SJrenxing/status/1933356962047242720, https://x.com/SJrenxing/status/1884224305497792560

maker: Shushu Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (20): https://x.com/Shushu_kigurumi/status/2076677797066760256, https://x.com/Shushu_kigurumi/status/2076266008244011133, https://x.com/Shushu_kigurumi/status/2074825911225233757, https://x.com/Shushu_kigurumi/status/2074149634659037396, https://x.com/Shushu_kigurumi/status/2072189321529168247, https://x.com/Shushu_kigurumi/status/2071556616122757353, https://x.com/Shushu_kigurumi/status/2013260536096403780, https://x.com/Shushu_kigurumi/status/2012863766333984938, https://x.com/Shushu_kigurumi/status/2000939725260276181, https://x.com/Shushu_kigurumi/status/2000854544541270518, https://x.com/Shushu_kigurumi/status/2000608991639109778, https://x.com/Shushu_kigurumi/status/2000125059953005046, https://x.com/Shushu_kigurumi/status/1995488809736421632, https://x.com/Shushu_kigurumi/status/1995098577933406534, https://x.com/Shushu_kigurumi/status/1994686466921042156, https://x.com/Shushu_kigurumi/status/1989273303211733018, https://x.com/Shushu_kigurumi/status/1988925390627434928, https://x.com/Shushu_kigurumi/status/1985610683963359632, https://x.com/Shushu_kigurumi/status/1984952544477786202, https://x.com/Shushu_kigurumi/status/1983516699438838223

maker: Studio Delphinium
region: USA
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://www.studiodelphinium.com/ | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/
site kigurumi references 2 : https://www.studiodelphinium.com/gallery | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/gallery
site kigurumi references 3 : https://www.studiodelphinium.com/commissions | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/commissions
site kigurumi references 4 : https://www.studiodelphinium.com/commission-process | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/commission-process
site kigurumi references 5 : https://www.studiodelphinium.com/all-about-the-mask | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/all-about-the-mask
site kigurumi references 6 : https://www.studiodelphinium.com/mask-care | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/mask-care
site kigurumi references 7 : https://www.studiodelphinium.com/diy | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/diy
site kigurumi references 8 : https://www.studiodelphinium.com/how-to-dye-your-own-hadatai-fabric | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/how-to-dye-your-own-hadatai-fabric
site kigurumi references 9 : https://www.studiodelphinium.com/shipping-info | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/shipping-info
site kigurumi references 10 : https://www.studiodelphinium.com/faq | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/faq
site kigurumi references 11 : https://www.studiodelphinium.com/terms-conditions | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/terms-conditions
x.com kigurumi references (1): https://x.com/delphiniumkig/status/2056541522829463775
x.com kigurumi hashtag-only references (17): https://x.com/delphiniumkig/status/2069572683096871146, https://x.com/delphiniumkig/status/2068137803041390705, https://x.com/delphiniumkig/status/2067770095544213654, https://x.com/delphiniumkig/status/2067069337433682373, https://x.com/delphiniumkig/status/2066691598725808340, https://x.com/delphiniumkig/status/2056908978169233455, https://x.com/delphiniumkig/status/2055455971330146523, https://x.com/delphiniumkig/status/2054019854387081241, https://x.com/delphiniumkig/status/2053291173523947691, https://x.com/delphiniumkig/status/2049907044589687247, https://x.com/delphiniumkig/status/2048826860302209076, https://x.com/delphiniumkig/status/2034393642580730000, https://x.com/delphiniumkig/status/2033980071501852703, https://x.com/delphiniumkig/status/2015540622690529487, https://x.com/delphiniumkig/status/2004609633605091733, https://x.com/delphiniumkig/status/2004254207336202334, https://x.com/delphiniumkig/status/2003144842717839630

maker: Studio RonMaca
region: South Korea
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://www.studioronmaca.com/ | archive: https://web.archive.org/web/*/https://www.studioronmaca.com/
site kigurumi references 2 : https://www.studioronmaca.com/welcome | archive: https://web.archive.org/web/*/https://www.studioronmaca.com/welcome
site kigurumi references 3 : https://www.studioronmaca.com/welcome/english | archive: https://web.archive.org/web/*/https://www.studioronmaca.com/welcome/english
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (6): https://x.com/Studio_RonMaca/status/2085290314466750567, https://x.com/Studio_RonMaca/status/2067506601683271911, https://x.com/Studio_RonMaca/status/2059210439515680796, https://x.com/Studio_RonMaca/status/2029883555502023016, https://x.com/Studio_RonMaca/status/2010259692803723430, https://x.com/Studio_RonMaca/status/1982779968917492161

maker: Teitoku Workshop
region: Hong Kong
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references 1 : https://www.teitokuworkshop.com/ | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/
site kigurumi references 2 : https://www.teitokuworkshop.com/jp/news | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/news
site kigurumi references 3 : https://www.teitokuworkshop.com/jp/about | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/about
site kigurumi references 4 : https://www.teitokuworkshop.com/jp/production-portfolio | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/production-portfolio
site kigurumi references 5 : https://www.teitokuworkshop.com/jp/commission | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/commission
site kigurumi references 6 : https://www.teitokuworkshop.com/en/home | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/home
site kigurumi references 7 : https://www.teitokuworkshop.com/en/news | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/news
site kigurumi references 8 : https://www.teitokuworkshop.com/en/about-us | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/about-us
site kigurumi references 9 : https://www.teitokuworkshop.com/en/comission | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/comission
site kigurumi references 10 : https://www.teitokuworkshop.com/en/production-portfolio | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/production-portfolio
site kigurumi references 11 : https://www.teitokuworkshop.com/cart | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/cart
site kigurumi references 12 : https://www.teitokuworkshop.com/jp/home | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/home
site kigurumi references 13 : https://www.teitokuworkshop.com/en/home | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/home
site kigurumi references 14 : https://www.teitokuworkshop.com/jp/production-portfolio/202401-toru | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/production-portfolio/202401-toru
site kigurumi references 15 : https://www.teitokuworkshop.com/jp/production-portfolio/202401ninon | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/production-portfolio/202401ninon
site kigurumi references 16 : https://www.teitokuworkshop.com/jp/production-portfolio/ninon-joubert-49pp5-zax26 | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/production-portfolio/ninon-joubert-49pp5-zax26
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)

maker: Umoon Kigurumi
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (1): https://x.com/Umoon_kigurumi/status/1920768275463524577
x.com kigurumi hashtag-only references (5): https://x.com/Umoon_kigurumi/status/1921890311971717327, https://x.com/Umoon_kigurumi/status/1921780998036934698, https://x.com/Umoon_kigurumi/status/1920318939986264410, https://x.com/Umoon_kigurumi/status/1912516527993286895, https://x.com/Umoon_kigurumi/status/1912175808367788431

maker: Very Good Man's Mask Studio
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (1): https://x.com/mBtg5bjdhcvIx6H/status/2083892225822666804

maker: Vive Design
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (20): https://x.com/ViveKigu/status/2056281969558954138, https://x.com/ViveKigu/status/2051940553030500801, https://x.com/ViveKigu/status/2048996705866264687, https://x.com/ViveKigu/status/2048294285863514541, https://x.com/ViveKigu/status/2047604090872729748, https://x.com/ViveKigu/status/2046999771307717088, https://x.com/ViveKigu/status/2046261235218518366, https://x.com/ViveKigu/status/2045072048121389523, https://x.com/ViveKigu/status/2044315060512928154, https://x.com/ViveKigu/status/2043959443805933592, https://x.com/ViveKigu/status/2004573973011742813, https://x.com/ViveKigu/status/2004573201511469443, https://x.com/ViveKigu/status/2004546916831629755, https://x.com/ViveKigu/status/2003059144182685818, https://x.com/ViveKigu/status/2003059027836829775, https://x.com/ViveKigu/status/2001291009226146040, https://x.com/ViveKigu/status/2000523249587757140, https://x.com/ViveKigu/status/2000521826888561038, https://x.com/ViveKigu/status/2000521414705905691, https://x.com/ViveKigu/status/1999743176031248640

maker: Anxinli Leiqi
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (2): https://x.com/xi_qi24992/status/2026592521883890006, https://x.com/xi_qi24992/status/2013245766215893123
x.com kigurumi hashtag-only references (10): https://x.com/xi_qi24992/status/2021954726292812015, https://x.com/xi_qi24992/status/2019082155452936311, https://x.com/xi_qi24992/status/2018367880677716207, https://x.com/xi_qi24992/status/2018167575004545307, https://x.com/xi_qi24992/status/2016204754448482314, https://x.com/xi_qi24992/status/2015836960741527656, https://x.com/xi_qi24992/status/2015461586698485802, https://x.com/xi_qi24992/status/2015131365092872251, https://x.com/xi_qi24992/status/2015128728335216728, https://x.com/xi_qi24992/status/2014753423493890240

maker: Xianbei Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (20): https://x.com/Xianbei_KIG/status/2002336429721235670, https://x.com/Xianbei_KIG/status/2002336353288442157, https://x.com/Xianbei_KIG/status/2002336294320627838, https://x.com/Xianbei_KIG/status/2002336225974444463, https://x.com/Xianbei_KIG/status/2002336152658063591, https://x.com/Xianbei_KIG/status/2002336090766897369, https://x.com/Xianbei_KIG/status/2002336038933704833, https://x.com/Xianbei_KIG/status/2002335970017103931, https://x.com/Xianbei_KIG/status/2002335866673607101, https://x.com/Xianbei_KIG/status/2002335774050799636, https://x.com/Xianbei_KIG/status/1989648682871066885, https://x.com/Xianbei_KIG/status/1989648628131270851, https://x.com/Xianbei_KIG/status/1989648576222535848, https://x.com/Xianbei_KIG/status/1989648513362542713, https://x.com/Xianbei_KIG/status/1989648442537455846, https://x.com/Xianbei_KIG/status/1983820838534275582, https://x.com/Xianbei_KIG/status/1983417721242161526, https://x.com/Xianbei_KIG/status/1983417653797781581, https://x.com/Xianbei_KIG/status/1983417596482597192, https://x.com/Xianbei_KIG/status/1983417530015461534

maker: Xingyueqi Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (5): https://x.com/xyq_kig/status/2058548155223089160, https://x.com/xyq_kig/status/2056761504540790817, https://x.com/xyq_kig/status/2055167847589179604, https://x.com/xyq_kig/status/2054807372166799838, https://x.com/xyq_kig/status/2053465612903690531
x.com kigurumi hashtag-only references (15): https://x.com/xyq_kig/status/2077623780948734450, https://x.com/xyq_kig/status/2069772351802364309, https://x.com/xyq_kig/status/2066879807644971096, https://x.com/xyq_kig/status/2066128661791846838, https://x.com/xyq_kig/status/2064700762366914696, https://x.com/xyq_kig/status/2061819617082011900, https://x.com/xyq_kig/status/2061428327009906792, https://x.com/xyq_kig/status/2061004142500573654, https://x.com/xyq_kig/status/2060370974869262845, https://x.com/xyq_kig/status/2060004691719958854, https://x.com/xyq_kig/status/2058873024166990227, https://x.com/xyq_kig/status/2057429379198943509, https://x.com/xyq_kig/status/2055892711564320884, https://x.com/xyq_kig/status/2054526344776864066, https://x.com/xyq_kig/status/2053099726980219121

makers with zero animegao reference:
2D Fantasy Aria BHY Renxing Fantasy Masks Haagaau Kigurumi Workshop Heyaoheyao HiDolls Kaga Kigurumi KFY Aniplus KigLand Kirisame Factory Lightning Natural Factory New Face Doll RINS Sakurano Shinkai Workshop Build Up Studio SIGMA Scarlet0rabbit W Rabbit Mi 4uuone A2 Laboratory Atelier NaNaoGi Ayame Store BEADOLL Bear Technique Studio Boundary Chiba Subaru Chikima Chilca Chris and Meph Cover Dollkii Dora Studio ELYSIUM Ezo Fox Workshop Gurgle Love Haka Renxing Harinezumi Workshop Huyaoshouzuo Hyokkame Iris Kigurumi Justin Bailey Kagaribi Workshop KaikaSakura Art Kaiser Factory Kawaiidoll Kig Kemono Mori KigCos Kigmask Kigurumi Factory Kigurumi Settings Kiguyobi KIGzhz King Mask Studio Kirisaki Craft Kuroneko Mask Shop Laoshu Zone Lucky Larus Magic Doll Maple Studio Marshmarocy Miaoxing Zhonggong Mihashi Mato Mirrodoll Miaomiaoxing Moli's Monaka Workshop Moyu Kig MRKT Mzdodo Neko Laboratory Nekotofu NM Workshop Nukopan OM Doll JP Ozawa Dango Power Kigurumi Raigeki Workshop Ricky Works Rintaro Salmon Workshop Shuijing Renxing Shushu Workshop Start Cosplay Studio Delphinium Studio Fractal Studio RonMaca Teitoku Workshop Tokal Tokyo Fantasy Workshop Trevor Umoon Kigurumi Very Good Man's Mask Studio Vive Design Anxinli Leiqi Xianbei Workshop Xingyueqi Workshop Yousen DollKig Yu Mao Zhizao Zukokan

totals:
  animegao: 6 makers | site pages 18 | x.com general 0 | x.com hashtag-only 10
  kigurumi: 69 makers | site pages 231 | x.com general 142 | x.com hashtag-only 587
````

</details>
</details>

### A deeper dive into the output

Lets go maker by maker through those who used the term Animegao and inspect their usage.

#### Black Cat Kig

The first maker is Black Cat Kig from Mainland China. Indeed on and only on their gallery page they do mention "Animegao Kigurumi", once. Comparatively they use Kigumi on 41 other pages ranging from the homepage, to example masks, the ordering process, and general guides.

Their last 20 X posts do not mention the term Animegao at all, meanwhile 8 posts include general usage of the term Kigurumi and 11 feature #kigurumi.

#### Goukaou (GKO)

GKO is a maker from the region of Taiwan. The scan of their website did not find any mentions of the term Aniemgao, but did find multiple references to Kigurumi.

On their last 20 X posts they included both #Kigurumi and #Animegao in the last 10 posts, avoiding usage of either term in the body of the post itself. This is alongside a number of other related hashtags akin to:

#kig #kiger #着ぐるみ #Kigurumi #面具 #マスク #キグルミ #GKO #goukaou #GKO_Kigurumi_Studio #コスプレ #cosplay #costume #美少女着ぐるみ #animegao #animegaokigurumi #kigurumimask

Truly an example of "spray and pray" as it comes to hashtag usage, trying to cover every base possible and maximize reach.

#### MidDream Kigu (Formerly Kig Lover)

MidDream Kigu is a relatively newer maker from Mainland China. Unlike most other Chinese maker entities this is one specifically trying to target western buyers.

Their site indeed does mention the term Animegao Kigu across 13 pages, still being dwarfed by the 19 uses of kigurumi in general across their pages.
On their last 20 X posts they did not use animegao in any context, but did use Kigurumi in general once and #kigurumi in 7 posts.

I would prescribe their usage primarily trying to cover terms they believe western buyers may be searching for, although I do find it curious they use the term "animegao kigu" rather than "animegao kigurumi", but that is neither here nor there.

#### DAME

DAME is a UK based Kigurumi maker. In general they do use animegao on their main page and their home page. Like most other cases where this occurs, it's vastly dwarfed by 41 uses of Kigurumi across their other pages.
Zero references to the term Animegao in their last 20 X posts. One use of Kigurumi in the body of a post.

As we can see, even among western makers, the term Animegao is largely absent from usage.

#### Munimuni Works

Munimuni is a Japanese maker, there is a single reference detected on their website. Notably this reference (https://www.munimuni.jp/p/00015)[https://www.munimuni.jp/p/00015] essentially points out that in Japan what they call Kigurumi Masks, or Bishoujo Kigurumi, are in the west called Kigurumi, Animegao, "etc".

They do however use Kigurumi in english across four of their pages, with zero usage of either english phrasing in their last 20 X posts.

#### MEIS/Pinhaotou

Another mainland Chinese maker with a Japanese presence on X.
There is one usage of the term Animegao on their main page, on a Kigurumi mask primer page (https://www.kigis.me/kigurumi)[https://www.kigis.me/kigurumi] where they mention Animegao being used in western contexts and how it started being used around 2005, basically after the initial edit of wikipedia to include the term was done.
Comparatively they use Kigurumi on 14 other pages.

Across their last 20 X posts they did not use animegao in any context, but did use #kigurumi in 1 post.

### Summary

Going through the results you can find that almost all usage is just mentioning that the term Animegao exists as a western term, however makers almost exclusively will use the term Kigurumi when discussing the hobby in English.

The only notable usage on social media from makers is from studio GKO who tends to include over a dozen hashtags in each post to maximize reach, a practice which anecdotally I find reflects most remaining usage by performers online, existing as just another hashtag to throw in the wind.
