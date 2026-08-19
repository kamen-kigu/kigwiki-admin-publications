---
title: Animegao Usage in 2026 - An Analytical Look
tags:
  - lore
  - animegao kigurumi
description: "A look at which makers actually still use the term Animegao in 2026. Spoiler, not many."
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

## TLDR

Here's the findings if you dont want to read methodology or the finer details:
107 makers scanned
76 mention Kigurumi in some capacity
Only 6 mention animegao

Two of the mentions are just to say that western performers sometimes call it animegao
One maker only uses it to extend SEO and social media reach
Another maker seemingly uses "animegao kigu" on some pages to target western buyers
The last two do use the term animegao on one or two pages however at a fraction the use of Kigurumi.

All uses of animegao or kigurumi animegao come secondary to plain old Kigurumi by a sizeable margin.

## Methodology of the scan

<details>
<summary>Script Details and Output</summary>

The following script can be run in the root directory of the Kig Wiki repository to scan our maker folders and their json files for mentions of Animegao and Kigurumi.
If Internet Archive environment variables are set, the site will also archive the pages in the state they are found.
The X.com bio and last 20 posts are scanned for mentions of Animegao and Kigurumi, as well as a maker's website. The website scan is limited to being two clicks deep, and up to 500 pages per site.

<details>
<summary>Python Script</summary>

The scanner is published separately at
[kamen-kigu/scan-animegao-script](https://github.com/kamen-kigu/scan-animegao-script),
with the script itself at
[`scan-animegao.py`](https://github.com/kamen-kigu/scan-animegao-script/blob/main/scan-animegao.py).

Run it from the root of a checkout of the Kig.wiki repository (so it can see
`makers/` and `unused_makers/`):

```bash
uv run path/to/scan-animegao.py
uv run path/to/scan-animegao.py --verbose
```

It looks for Animegao and Kigurumi (including hashtag-only vs normal usage) on maker
websites, X bios, and recent X posts. If Internet Archive credentials are set, hit
pages can also be submitted to the Wayback Machine.

</details>

<details>
<summary>Script Output (Very Long Text)</summary>

```text
maker: 2D Fantasy
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (20): https://x.com/2DFantasy111/status/1948314224578716125, https://x.com/2DFantasy111/status/1940040152656879935, https://x.com/2DFantasy111/status/1931692456300667100, https://x.com/2DFantasy111/status/1928788766161788964, https://x.com/2DFantasy111/status/1925110084411265516, https://x.com/2DFantasy111/status/1924444357442363546, https://x.com/2DFantasy111/status/1923665215113384269, https://x.com/2DFantasy111/status/1922989295666614353, https://x.com/2DFantasy111/status/1916755398578823387, https://x.com/2DFantasy111/status/1892823919167754601, https://x.com/2DFantasy111/status/1888065811224609088, https://x.com/2DFantasy111/status/1887341691780350293, https://x.com/2DFantasy111/status/1874335344084344878, https://x.com/2DFantasy111/status/1868617944743498204, https://x.com/2DFantasy111/status/1865266487893856758, https://x.com/2DFantasy111/status/1864175579530186997, https://x.com/2DFantasy111/status/1861673673444540497, https://x.com/2DFantasy111/status/1856193396940943844, https://x.com/2DFantasy111/status/1854754018565956011, https://x.com/2DFantasy111/status/1849995967875215659
x.com kigurumi bio references (1): https://x.com/2DFantasy111
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (20): https://x.com/2DFantasy111/status/1948314224578716125, https://x.com/2DFantasy111/status/1940040152656879935, https://x.com/2DFantasy111/status/1931692456300667100, https://x.com/2DFantasy111/status/1928788766161788964, https://x.com/2DFantasy111/status/1925110084411265516, https://x.com/2DFantasy111/status/1924444357442363546, https://x.com/2DFantasy111/status/1923665215113384269, https://x.com/2DFantasy111/status/1922989295666614353, https://x.com/2DFantasy111/status/1916755398578823387, https://x.com/2DFantasy111/status/1892823919167754601, https://x.com/2DFantasy111/status/1888065811224609088, https://x.com/2DFantasy111/status/1887341691780350293, https://x.com/2DFantasy111/status/1874335344084344878, https://x.com/2DFantasy111/status/1868617944743498204, https://x.com/2DFantasy111/status/1865266487893856758, https://x.com/2DFantasy111/status/1864175579530186997, https://x.com/2DFantasy111/status/1861673673444540497, https://x.com/2DFantasy111/status/1856193396940943844, https://x.com/2DFantasy111/status/1854754018565956011, https://x.com/2DFantasy111/status/1849995967875215659
x.com 着ぐるみ bio references: none (0)

maker: Aria
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (19): https://x.com/mitsukiriya/status/1993960415655809466, https://x.com/mitsukiriya/status/1984917681305522301, https://x.com/mitsukiriya/status/1984204121508110695, https://x.com/mitsukiriya/status/1983450676387844203, https://x.com/mitsukiriya/status/1982402809615237548, https://x.com/mitsukiriya/status/1982335224681033971, https://x.com/mitsukiriya/status/1981636320415158344, https://x.com/mitsukiriya/status/1981256489169014857, https://x.com/mitsukiriya/status/1980611020940001531, https://x.com/mitsukiriya/status/1980361057266020583, https://x.com/mitsukiriya/status/1936734156232482988, https://x.com/mitsukiriya/status/1929949730773364876, https://x.com/mitsukiriya/status/1927057671435206711, https://x.com/mitsukiriya/status/1916439966433100249, https://x.com/mitsukiriya/status/1912485504345673732, https://x.com/mitsukiriya/status/1911706257230021094, https://x.com/mitsukiriya/status/1884245127310544983, https://x.com/mitsukiriya/status/1881347890800706026, https://x.com/mitsukiriya/status/1880562297472688228
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: BHY Renxing
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://bhyrenxing.com | archive: https://web.archive.org/web/*/https://bhyrenxing.com
site kigurumi references 2 : https://bhyrenxing.com/collections/fixed | archive: https://web.archive.org/web/*/https://bhyrenxing.com/collections/fixed
site kigurumi references 3 : https://bhyrenxing.com/products/kigurumi-mask-black-fox | archive: https://web.archive.org/web/*/https://bhyrenxing.com/products/kigurumi-mask-black-fox
site kigurumi references 4 : https://bhyrenxing.com/products/kigurumi-mask-black-wang | archive: https://web.archive.org/web/*/https://bhyrenxing.com/products/kigurumi-mask-black-wang
site kigurumi references 5 : https://bhyrenxing.com/products/kigurumi-mask-miaomiao | archive: https://web.archive.org/web/*/https://bhyrenxing.com/products/kigurumi-mask-miaomiao
site kigurumi references 6 : https://bhyrenxing.com/products/final-payment-for-bhyrenxing-kigurumi-mask | archive: https://web.archive.org/web/*/https://bhyrenxing.com/products/final-payment-for-bhyrenxing-kigurumi-mask
site kigurumi references 7 : https://bhyrenxing.com/products/kigurumi-mask-cengdie | archive: https://web.archive.org/web/*/https://bhyrenxing.com/products/kigurumi-mask-cengdie
site kigurumi references 8 : https://bhyrenxing.com/products/%E6%AC%A2%E9%A2%9C | archive: https://web.archive.org/web/*/https://bhyrenxing.com/products/%E6%AC%A2%E9%A2%9C
site kigurumi references 9 : https://bhyrenxing.com/collections/all | archive: https://web.archive.org/web/*/https://bhyrenxing.com/collections/all
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (11): https://x.com/BHYrenxing/status/2065314747533410671, https://x.com/BHYrenxing/status/2044330423854256487, https://x.com/BHYrenxing/status/2038867555549622443, https://x.com/BHYrenxing/status/2037759419422003459, https://x.com/BHYrenxing/status/2006175883673891118, https://x.com/BHYrenxing/status/2000809541534200171, https://x.com/BHYrenxing/status/1998331341423649233, https://x.com/BHYrenxing/status/1996915592851607695, https://x.com/BHYrenxing/status/1996869634511995352, https://x.com/BHYrenxing/status/1996243006073315551, https://x.com/BHYrenxing/status/1994580938425340034
x.com kigurumi bio references (1): https://x.com/BHYrenxing
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (5): https://x.com/BHYrenxing/status/2065314747533410671, https://x.com/BHYrenxing/status/2044330423854256487, https://x.com/BHYrenxing/status/2038867555549622443, https://x.com/BHYrenxing/status/2037759419422003459, https://x.com/BHYrenxing/status/2006175883673891118
x.com 着ぐるみ bio references: none (0)

maker: Black Cat Kig
region: Mainland China
site animegao references 1 : https://blackcatkig.com/pages/gallery | archive: https://web.archive.org/web/20260809172156/https://blackcatkig.com/pages/gallery
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://blackcatkig.com/ | archive: https://web.archive.org/web/*/https://blackcatkig.com/
site kigurumi references 2 : https://blackcatkig.com/collections/customize-your-mask | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/customize-your-mask
site kigurumi references 3 : https://blackcatkig.com/collections/latest-designs-from-the-past-30-days-exhibition-only-discover-the-intricate-details-and-mastercraft-behind-our-newest-kigurumi-and-zentai-additions | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/latest-designs-from-the-past-30-days-exhibition-only-discover-the-intricate-details-and-mastercraft-behind-our-newest-kigurumi-and-zentai-additions
site kigurumi references 4 : https://blackcatkig.com/collections/2026a-kig-head-shell | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/2026a-kig-head-shell
site kigurumi references 5 : https://blackcatkig.com/collections/pre-made-masks | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/pre-made-masks
site kigurumi references 6 : https://blackcatkig.com/collections/in-stock-masks | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/in-stock-masks
site kigurumi references 7 : https://blackcatkig.com/collections/hadataiskinsuit | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/hadataiskinsuit
site kigurumi references 8 : https://blackcatkig.com/collections/breast | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/breast
site kigurumi references 9 : https://blackcatkig.com/collections/accessories | archive: https://web.archive.org/web/*/https://blackcatkig.com/collections/accessories
site kigurumi references 10 : https://blackcatkig.com/pages/gallery | archive: https://web.archive.org/web/20260809172156/https://blackcatkig.com/pages/gallery
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
site kigurumi references 42 : https://blackcatkig.com/products/hoshimi-miyabi-zenless-zone-zero-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/hoshimi-miyabi-zenless-zone-zero-kigurumi-mask-by-blackcatkig
site kigurumi references 43 : https://blackcatkig.com/products/jupiter-sailor-moon-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/jupiter-sailor-moon-kigurumi-mask-by-blackcatkig
site kigurumi references 44 : https://blackcatkig.com/products/astra-yao-zenless-zone-zero-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/astra-yao-zenless-zone-zero-kigurumi-mask-by-blackcatkig
site kigurumi references 45 : https://blackcatkig.com/pages/about-us | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/about-us
site kigurumi references 46 : https://blackcatkig.com/pages/contact | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/contact
site kigurumi references 47 : https://blackcatkig.com/policies/privacy-policy | archive: https://web.archive.org/web/*/https://blackcatkig.com/policies/privacy-policy
site kigurumi references 48 : https://blackcatkig.com/policies/terms-of-service | archive: https://web.archive.org/web/*/https://blackcatkig.com/policies/terms-of-service
site kigurumi references 49 : https://blackcatkig.com/apps/17TRACK | archive: https://web.archive.org/web/*/https://blackcatkig.com/apps/17TRACK
site kigurumi references 50 : https://blackcatkig.com/policies/refund-policy | archive: https://web.archive.org/web/*/https://blackcatkig.com/policies/refund-policy
site kigurumi references 51 : https://blackcatkig.com/products/sameko-saba-sameko-sab-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/sameko-saba-sameko-sab-kigurumi-mask-by-blackcatkig
site kigurumi references 52 : https://blackcatkig.com/products/yomi-honkai-star-rail-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/yomi-honkai-star-rail-kigurumi-mask-by-blackcatkig
site kigurumi references 53 : https://blackcatkig.com/products/subaru-awa-girls-band-cry-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/subaru-awa-girls-band-cry-kigurumi-mask-by-blackcatkig
site kigurumi references 54 : https://blackcatkig.com/products/kirara-genshin-impact-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kirara-genshin-impact-kigurumi-mask-by-blackcatkig
site kigurumi references 55 : https://blackcatkig.com/products/kozume-kenma-haikyuu-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kozume-kenma-haikyuu-kigurumi-mask-by-blackcatkig
site kigurumi references 56 : https://blackcatkig.com/products/cartethyia-wuthering-waves-kigurumi-mask-by-blackcatkig-1 | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/cartethyia-wuthering-waves-kigurumi-mask-by-blackcatkig-1
site kigurumi references 57 : https://blackcatkig.com/products/cartethyia-wuthering-waves-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/cartethyia-wuthering-waves-kigurumi-mask-by-blackcatkig
site kigurumi references 58 : https://blackcatkig.com/products/mutsumi-wakaba-bang-dream-it-s-mygo-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/mutsumi-wakaba-bang-dream-it-s-mygo-kigurumi-mask-by-blackcatkig
site kigurumi references 59 : https://blackcatkig.com/products/tessa-full-metal-panic-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/tessa-full-metal-panic-kigurumi-mask-by-blackcatkig
site kigurumi references 60 : https://blackcatkig.com/products/nefer-genshin-impact-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/nefer-genshin-impact-kigurumi-mask-by-blackcatkig
site kigurumi references 61 : https://blackcatkig.com/products/molis-zentai-skinsuit-light-skin-of-classic-series-super-spandex | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/molis-zentai-skinsuit-light-skin-of-classic-series-super-spandex
site kigurumi references 62 : https://blackcatkig.com/products/moli-s-zentai-skinsuit-lolita-of-classic-series-super-spandex | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/moli-s-zentai-skinsuit-lolita-of-classic-series-super-spandex
site kigurumi references 63 : https://blackcatkig.com/products/skinsuit2-kig-hadatai-for-kigurumi-baby-pink-zentai | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/skinsuit2-kig-hadatai-for-kigurumi-baby-pink-zentai
site kigurumi references 64 : https://blackcatkig.com/products/value-pack-for-zentai-suitswith-zentai-orders-necessary | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/value-pack-for-zentai-suitswith-zentai-orders-necessary
site kigurumi references 65 : https://blackcatkig.com/products/in-stock-skinsuit2-kig-hadatai-for-kigurumi-baby-pink-zentai | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/in-stock-skinsuit2-kig-hadatai-for-kigurumi-baby-pink-zentai
site kigurumi references 66 : https://blackcatkig.com/products/in-stockultra-thick-series-2nd-gen-12800d-heaviest-seam-reduced-zentai-for-kigurumi | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/in-stockultra-thick-series-2nd-gen-12800d-heaviest-seam-reduced-zentai-for-kigurumi
site kigurumi references 67 : https://blackcatkig.com/products/silicone-breast-formscup-a-z-for-zentai-breast-implantscleavage-pockets-and-3d-breaststeardrop-breast-forms | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/silicone-breast-formscup-a-z-for-zentai-breast-implantscleavage-pockets-and-3d-breaststeardrop-breast-forms
site kigurumi references 68 : https://blackcatkig.com/products/silicone-breast-formscup-a-z-for-zentai-breast-implantscleavage-pockets-and-3d-breastsround-breast-forms | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/silicone-breast-formscup-a-z-for-zentai-breast-implantscleavage-pockets-and-3d-breastsround-breast-forms
site kigurumi references 69 : https://blackcatkig.com/products/zero-touch-breasts-b-g-cup-silicone-breastplate-for-crossdressers | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/zero-touch-breasts-b-g-cup-silicone-breastplate-for-crossdressers
site kigurumi references 70 : https://blackcatkig.com/products/blackcatkig-hair-clips-stickers-keychains | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/blackcatkig-hair-clips-stickers-keychains
site kigurumi references 71 : https://blackcatkig.com/products/in-stock-wig-for-kigurumi-mask-by-blackcat | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/in-stock-wig-for-kigurumi-mask-by-blackcat
site kigurumi references 72 : https://blackcatkig.com/products/ellen-joe-cosplay-costume-zenless-zone-zero-incomplete-set | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/ellen-joe-cosplay-costume-zenless-zone-zero-incomplete-set
site kigurumi references 73 : https://blackcatkig.com/products/kirara-cosplay-costume-genshin-impact-pre-owned-sample | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kirara-cosplay-costume-genshin-impact-pre-owned-sample
site kigurumi references 74 : https://blackcatkig.com/products/nicole-demara-cosplay-costume-zenless-zone-zero-pre-owned-sample-1 | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/nicole-demara-cosplay-costume-zenless-zone-zero-pre-owned-sample-1
site kigurumi references 75 : https://blackcatkig.com/products/nicole-demara-cosplay-costume-zenless-zone-zero-pre-owned-sample | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/nicole-demara-cosplay-costume-zenless-zone-zero-pre-owned-sample
site kigurumi references 76 : https://blackcatkig.com/products/astra-yao-cosplay-costume-zenless-zone-zero-incomplete-set | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/astra-yao-cosplay-costume-zenless-zone-zero-incomplete-set
site kigurumi references 77 : https://blackcatkig.com/products/cartethyia-cosplay-costume-wuthering-waves-cosplay-outfit | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/cartethyia-cosplay-costume-wuthering-waves-cosplay-outfit
site kigurumi references 78 : https://blackcatkig.com/products/shirayuki-ren-shino-to-koi-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/shirayuki-ren-shino-to-koi-kigurumi-mask-by-blackcatkig
site kigurumi references 79 : https://blackcatkig.com/products/xueyi-honkai-star-rail-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/xueyi-honkai-star-rail-kigurumi-mask-by-blackcatkig
site kigurumi references 80 : https://blackcatkig.com/products/ellen-joe-zenless-zone-zero-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/ellen-joe-zenless-zone-zero-kigurumi-mask-by-blackcatkig
site kigurumi references 81 : https://blackcatkig.com/products/barbatos-fgo-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/barbatos-fgo-kigurumi-mask-by-blackcatkig
site kigurumi references 82 : https://blackcatkig.com/products/yelan-genshin-impact-kigurumi-mask-by-blackcatkig-3d-printed-hair | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/yelan-genshin-impact-kigurumi-mask-by-blackcatkig-3d-printed-hair
site kigurumi references 83 : https://blackcatkig.com/products/sakura-chiyo-gekkan-shoujo-nozaki-kun-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/sakura-chiyo-gekkan-shoujo-nozaki-kun-kigurumi-mask-by-blackcatkig
site kigurumi references 84 : https://blackcatkig.com/products/kaenbyou-rin-touhouproject-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kaenbyou-rin-touhouproject-kigurumi-mask-by-blackcatkig
site kigurumi references 85 : https://blackcatkig.com/products/castorice-honkai-star-rail-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/castorice-honkai-star-rail-kigurumi-mask-by-blackcatkig
site kigurumi references 86 : https://blackcatkig.com/products/gawr-gura-hololive-english-kigurumi-mask-by-blackcatkig | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/gawr-gura-hololive-english-kigurumi-mask-by-blackcatkig
site kigurumi references 87 : https://blackcatkig.com/pages/doll-weekend | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/doll-weekend
site kigurumi references 88 : https://blackcatkig.com/pages/doll-weekend-11 | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/doll-weekend-11
site kigurumi references 89 : https://blackcatkig.com/pages/doll-weekend-12 | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/doll-weekend-12
site kigurumi references 90 : https://blackcatkig.com/pages/doll-weekend-13 | archive: https://web.archive.org/web/*/https://blackcatkig.com/pages/doll-weekend-13
site kigurumi references 91 : https://blackcatkig.com/products/marin-kitagawa-my-dress-up-darling-kigurumi-mask-by-blackcatkig-1?_pos=2&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/marin-kitagawa-my-dress-up-darling-kigurumi-mask-by-blackcatkig-1?_pos=2&_sid=bf7dc28a0&_ss=r
site kigurumi references 92 : https://blackcatkig.com/products/kurageu-roa-kurageu-roa-kigurumi-mask-by-blackcatkig?_pos=13&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kurageu-roa-kurageu-roa-kigurumi-mask-by-blackcatkig?_pos=13&_sid=bf7dc28a0&_ss=r
site kigurumi references 93 : https://blackcatkig.com/products/marin-kitagawa-my-dress-up-darling-kigurumi-mask-by-blackcatkig?_pos=23&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/marin-kitagawa-my-dress-up-darling-kigurumi-mask-by-blackcatkig?_pos=23&_sid=bf7dc28a0&_ss=r
site kigurumi references 94 : https://blackcatkig.com/search?q=kigurumi-mask*&type=product&sort_by= | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?q=kigurumi-mask*&type=product&sort_by=
site kigurumi references 95 : https://blackcatkig.com/search?options%5Bprefix%5D=last&q=kigurumi-mask%2A&type=kigurumi-mask%2A | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?options%5Bprefix%5D=last&q=kigurumi-mask%2A&type=kigurumi-mask%2A
site kigurumi references 96 : https://blackcatkig.com/products/astra-yao-zenless-zone-zero-kigurumi-mask-by-blackcatkig?_pos=1&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/astra-yao-zenless-zone-zero-kigurumi-mask-by-blackcatkig?_pos=1&_sid=bf7dc28a0&_ss=r
site kigurumi references 97 : https://blackcatkig.com/products/in-stock-wig-for-kigurumi-mask-by-blackcat?_pos=3&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/in-stock-wig-for-kigurumi-mask-by-blackcat?_pos=3&_sid=bf7dc28a0&_ss=r
site kigurumi references 98 : https://blackcatkig.com/products/lacrimosa-nte-kigurumi-mask-by-blackcatkig?_pos=4&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/lacrimosa-nte-kigurumi-mask-by-blackcatkig?_pos=4&_sid=bf7dc28a0&_ss=r
site kigurumi references 99 : https://blackcatkig.com/products/hoshimi-miyabi-zenless-zone-zero-kigurumi-mask-by-blackcatkig?_pos=5&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/hoshimi-miyabi-zenless-zone-zero-kigurumi-mask-by-blackcatkig?_pos=5&_sid=bf7dc28a0&_ss=r
site kigurumi references 100 : https://blackcatkig.com/products/subaru-awa-girls-band-cry-kigurumi-mask-by-blackcatkig?_pos=6&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/subaru-awa-girls-band-cry-kigurumi-mask-by-blackcatkig?_pos=6&_sid=bf7dc28a0&_ss=r
site kigurumi references 101 : https://blackcatkig.com/products/kirara-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=7&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kirara-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=7&_sid=bf7dc28a0&_ss=r
site kigurumi references 102 : https://blackcatkig.com/products/ellen-joe-zenless-zone-zero-kigurumi-mask-by-blackcatkig?_pos=8&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/ellen-joe-zenless-zone-zero-kigurumi-mask-by-blackcatkig?_pos=8&_sid=bf7dc28a0&_ss=r
site kigurumi references 103 : https://blackcatkig.com/products/wanderer-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=9&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/wanderer-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=9&_sid=bf7dc28a0&_ss=r
site kigurumi references 104 : https://blackcatkig.com/products/kafka-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=11&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kafka-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=11&_sid=bf7dc28a0&_ss=r
site kigurumi references 105 : https://blackcatkig.com/products/akiyama-mizuki-hatsune-miku-colorful-stage-kigurumi-mask-by-blackcatkig?_pos=15&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/akiyama-mizuki-hatsune-miku-colorful-stage-kigurumi-mask-by-blackcatkig?_pos=15&_sid=bf7dc28a0&_ss=r
site kigurumi references 106 : https://blackcatkig.com/search?options%5Bprefix%5D=last&page=2&q=kigurumi-mask%2A&type=kigurumi-mask%2A | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?options%5Bprefix%5D=last&page=2&q=kigurumi-mask%2A&type=kigurumi-mask%2A
site kigurumi references 107 : https://blackcatkig.com/products/nian-arknights-kigurumi-mask-by-blackcatkig?_pos=16&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/nian-arknights-kigurumi-mask-by-blackcatkig?_pos=16&_sid=bf7dc28a0&_ss=r
site kigurumi references 108 : https://blackcatkig.com/products/castorice-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=17&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/castorice-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=17&_sid=bf7dc28a0&_ss=r
site kigurumi references 109 : https://blackcatkig.com/products/rapi-goddess-of-victory-kigurumi-mask-by-blackcatkig?_pos=18&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/rapi-goddess-of-victory-kigurumi-mask-by-blackcatkig?_pos=18&_sid=bf7dc28a0&_ss=r
site kigurumi references 110 : https://blackcatkig.com/products/yomi-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=19&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/yomi-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=19&_sid=bf7dc28a0&_ss=r
site kigurumi references 111 : https://blackcatkig.com/products/mobius-honkai-impact-3rd-kigurumi-mask-by-blackcatkig?_pos=20&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/mobius-honkai-impact-3rd-kigurumi-mask-by-blackcatkig?_pos=20&_sid=bf7dc28a0&_ss=r
site kigurumi references 112 : https://blackcatkig.com/products/shirayuki-ren-shino-to-koi-kigurumi-mask-by-blackcatkig?_pos=22&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/shirayuki-ren-shino-to-koi-kigurumi-mask-by-blackcatkig?_pos=22&_sid=bf7dc28a0&_ss=r
site kigurumi references 113 : https://blackcatkig.com/products/sirius-azur-lane-kigurumi-mask-by-blackcatkig?_pos=26&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/sirius-azur-lane-kigurumi-mask-by-blackcatkig?_pos=26&_sid=bf7dc28a0&_ss=r
site kigurumi references 114 : https://blackcatkig.com/products/mutsumi-wakaba-bang-dream-it-s-mygo-kigurumi-mask-by-blackcatkig?_pos=27&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/mutsumi-wakaba-bang-dream-it-s-mygo-kigurumi-mask-by-blackcatkig?_pos=27&_sid=bf7dc28a0&_ss=r
site kigurumi references 115 : https://blackcatkig.com/products/tessa-full-metal-panic-kigurumi-mask-by-blackcatkig?_pos=30&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/tessa-full-metal-panic-kigurumi-mask-by-blackcatkig?_pos=30&_sid=bf7dc28a0&_ss=r
site kigurumi references 116 : https://blackcatkig.com/products/yelan-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=35&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/yelan-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=35&_sid=bf7dc28a0&_ss=r
site kigurumi references 117 : https://blackcatkig.com/products/nefer-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=36&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/nefer-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=36&_sid=bf7dc28a0&_ss=r
site kigurumi references 118 : https://blackcatkig.com/products/nana-hoshi-food-for-the-soul-kigurumi-mask-by-blackcatkig?_pos=38&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/nana-hoshi-food-for-the-soul-kigurumi-mask-by-blackcatkig?_pos=38&_sid=bf7dc28a0&_ss=r
site kigurumi references 119 : https://blackcatkig.com/products/roxy-migurdia-mushoku-tensei-kigurumi-mask-by-blackcatkig?_pos=39&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/roxy-migurdia-mushoku-tensei-kigurumi-mask-by-blackcatkig?_pos=39&_sid=bf7dc28a0&_ss=r
site kigurumi references 120 : https://blackcatkig.com/products/theresa-arknights-kigurumi-mask-by-blackcatkig?_pos=41&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/theresa-arknights-kigurumi-mask-by-blackcatkig?_pos=41&_sid=bf7dc28a0&_ss=r
site kigurumi references 121 : https://blackcatkig.com/products/jupiter-sailor-moon-kigurumi-mask-by-blackcatkig?_pos=43&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/jupiter-sailor-moon-kigurumi-mask-by-blackcatkig?_pos=43&_sid=bf7dc28a0&_ss=r
site kigurumi references 122 : https://blackcatkig.com/products/ganyu-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=46&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/ganyu-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=46&_sid=bf7dc28a0&_ss=r
site kigurumi references 123 : https://blackcatkig.com/products/yae-miko-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=48&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/yae-miko-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=48&_sid=bf7dc28a0&_ss=r
site kigurumi references 124 : https://blackcatkig.com/products/chizuru-kinki-lyrical-lily-luminous-era-kigurumi-mask-by-blackcatkig?_pos=49&_sid=bf7dc28a0&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/chizuru-kinki-lyrical-lily-luminous-era-kigurumi-mask-by-blackcatkig?_pos=49&_sid=bf7dc28a0&_ss=r
site kigurumi references 125 : https://blackcatkig.com/search?q=zentai*&type=product&sort_by= | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?q=zentai*&type=product&sort_by=
site kigurumi references 126 : https://blackcatkig.com/search?options%5Bprefix%5D=last&q=zentai%2A&type=zentai%2A | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?options%5Bprefix%5D=last&q=zentai%2A&type=zentai%2A
site kigurumi references 127 : https://blackcatkig.com/products/value-pack-for-zentai-suitswith-zentai-orders-necessary?_pos=1&_sid=48380803e&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/value-pack-for-zentai-suitswith-zentai-orders-necessary?_pos=1&_sid=48380803e&_ss=r
site kigurumi references 128 : https://blackcatkig.com/products/in-stock-skinsuit2-kig-hadatai-for-kigurumi-baby-pink-zentai?_pos=2&_sid=48380803e&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/in-stock-skinsuit2-kig-hadatai-for-kigurumi-baby-pink-zentai?_pos=2&_sid=48380803e&_ss=r
site kigurumi references 129 : https://blackcatkig.com/products/silicone-breast-formscup-a-z-for-zentai-breast-implantscleavage-pockets-and-3d-breaststeardrop-breast-forms?_pos=3&_sid=48380803e&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/silicone-breast-formscup-a-z-for-zentai-breast-implantscleavage-pockets-and-3d-breaststeardrop-breast-forms?_pos=3&_sid=48380803e&_ss=r
site kigurumi references 130 : https://blackcatkig.com/products/in-stockultra-thick-series-2nd-gen-12800d-heaviest-seam-reduced-zentai-for-kigurumi?_pos=4&_sid=48380803e&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/in-stockultra-thick-series-2nd-gen-12800d-heaviest-seam-reduced-zentai-for-kigurumi?_pos=4&_sid=48380803e&_ss=r
site kigurumi references 131 : https://blackcatkig.com/products/molis-zentai-skinsuit-kig-pink-of-classic-series-super-spandex?_pos=5&_sid=48380803e&_ss=r&variant=43926067609772 | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/molis-zentai-skinsuit-kig-pink-of-classic-series-super-spandex?_pos=5&_sid=48380803e&_ss=r&variant=43926067609772
site kigurumi references 132 : https://blackcatkig.com/products/molis-zentai-skinsuit-light-skin-of-classic-series-super-spandex?_pos=8&_sid=48380803e&_ss=r&variant=43926066299052 | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/molis-zentai-skinsuit-light-skin-of-classic-series-super-spandex?_pos=8&_sid=48380803e&_ss=r&variant=43926066299052
site kigurumi references 133 : https://blackcatkig.com/search?q=genshin-impact*&type=product&sort_by= | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?q=genshin-impact*&type=product&sort_by=
site kigurumi references 134 : https://blackcatkig.com/search?options%5Bprefix%5D=last&q=genshin-impact%2A&type=genshin-impact%2A | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?options%5Bprefix%5D=last&q=genshin-impact%2A&type=genshin-impact%2A
site kigurumi references 135 : https://blackcatkig.com/products/kirara-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=1&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kirara-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=1&_sid=a33d3df1d&_ss=r
site kigurumi references 136 : https://blackcatkig.com/products/wanderer-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=2&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/wanderer-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=2&_sid=a33d3df1d&_ss=r
site kigurumi references 137 : https://blackcatkig.com/products/kirara-cosplay-costume-genshin-impact-pre-owned-sample?_pos=3&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kirara-cosplay-costume-genshin-impact-pre-owned-sample?_pos=3&_sid=a33d3df1d&_ss=r
site kigurumi references 138 : https://blackcatkig.com/products/subaru-awa-girls-band-cry-kigurumi-mask-by-blackcatkig?_pos=4&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/subaru-awa-girls-band-cry-kigurumi-mask-by-blackcatkig?_pos=4&_sid=a33d3df1d&_ss=r
site kigurumi references 139 : https://blackcatkig.com/products/selestia-vr-chat-kigurumi-mask-by-blackcatkig?_pos=7&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/selestia-vr-chat-kigurumi-mask-by-blackcatkig?_pos=7&_sid=a33d3df1d&_ss=r
site kigurumi references 140 : https://blackcatkig.com/products/shiro-no-game-no-life-kigurumi-mask-by-blackcatkig?_pos=8&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/shiro-no-game-no-life-kigurumi-mask-by-blackcatkig?_pos=8&_sid=a33d3df1d&_ss=r
site kigurumi references 141 : https://blackcatkig.com/products/shirai-kuroko-a-certain-scientific-railgun-kigurumi-mask-by-blackcatkig?_pos=11&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/shirai-kuroko-a-certain-scientific-railgun-kigurumi-mask-by-blackcatkig?_pos=11&_sid=a33d3df1d&_ss=r
site kigurumi references 142 : https://blackcatkig.com/products/yelan-genshin-impact-kigurumi-mask-by-blackcatkig-3d-printed-hair?_pos=13&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/yelan-genshin-impact-kigurumi-mask-by-blackcatkig-3d-printed-hair?_pos=13&_sid=a33d3df1d&_ss=r
site kigurumi references 143 : https://blackcatkig.com/products/jupiter-sailor-moon-kigurumi-mask-by-blackcatkig?_pos=15&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/jupiter-sailor-moon-kigurumi-mask-by-blackcatkig?_pos=15&_sid=a33d3df1d&_ss=r
site kigurumi references 144 : https://blackcatkig.com/search?options%5Bprefix%5D=last&page=2&q=genshin-impact%2A&type=genshin-impact%2A | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?options%5Bprefix%5D=last&page=2&q=genshin-impact%2A&type=genshin-impact%2A
site kigurumi references 145 : https://blackcatkig.com/products/ami-mizuno-sailor-moon-kigurumi-mask-by-blackcatkig?_pos=16&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/ami-mizuno-sailor-moon-kigurumi-mask-by-blackcatkig?_pos=16&_sid=a33d3df1d&_ss=r
site kigurumi references 146 : https://blackcatkig.com/products/blank-no-game-no-life-kigurumi-mask-by-blackcatkig?_pos=17&_sid=a33d3df1d&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/blank-no-game-no-life-kigurumi-mask-by-blackcatkig?_pos=17&_sid=a33d3df1d&_ss=r
site kigurumi references 147 : https://blackcatkig.com/products/kurageu-roa-kurageu-roa-kigurumi-mask-by-blackcatkig?_pos=11&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kurageu-roa-kurageu-roa-kigurumi-mask-by-blackcatkig?_pos=11&_sid=aa6243602&_ss=r
site kigurumi references 148 : https://blackcatkig.com/search?options%5Bprefix%5D=last&q=honkai-star-rail%2A&type=honkai-star-rail%2A | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?options%5Bprefix%5D=last&q=honkai-star-rail%2A&type=honkai-star-rail%2A
site kigurumi references 149 : https://blackcatkig.com/products/lacrimosa-nte-kigurumi-mask-by-blackcatkig?_pos=1&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/lacrimosa-nte-kigurumi-mask-by-blackcatkig?_pos=1&_sid=aa6243602&_ss=r
site kigurumi references 150 : https://blackcatkig.com/products/kafka-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=2&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kafka-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=2&_sid=aa6243602&_ss=r
site kigurumi references 151 : https://blackcatkig.com/products/xueyi-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=3&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/xueyi-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=3&_sid=aa6243602&_ss=r
site kigurumi references 152 : https://blackcatkig.com/products/yomi-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=4&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/yomi-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=4&_sid=aa6243602&_ss=r
site kigurumi references 153 : https://blackcatkig.com/products/castorice-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=5&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/castorice-honkai-star-rail-kigurumi-mask-by-blackcatkig?_pos=5&_sid=aa6243602&_ss=r
site kigurumi references 154 : https://blackcatkig.com/products/mobius-honkai-impact-3rd-kigurumi-mask-by-blackcatkig?_pos=7&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/mobius-honkai-impact-3rd-kigurumi-mask-by-blackcatkig?_pos=7&_sid=aa6243602&_ss=r
site kigurumi references 155 : https://blackcatkig.com/products/shirayuki-ren-shino-to-koi-kigurumi-mask-by-blackcatkig?_pos=13&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/shirayuki-ren-shino-to-koi-kigurumi-mask-by-blackcatkig?_pos=13&_sid=aa6243602&_ss=r
site kigurumi references 156 : https://blackcatkig.com/search?options%5Bprefix%5D=last&page=2&q=honkai-star-rail%2A&type=honkai-star-rail%2A | archive: https://web.archive.org/web/*/https://blackcatkig.com/search?options%5Bprefix%5D=last&page=2&q=honkai-star-rail%2A&type=honkai-star-rail%2A
site kigurumi references 157 : https://blackcatkig.com/products/entelechia-arknights-kigurumi-mask-by-blackcatkig?_pos=16&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/entelechia-arknights-kigurumi-mask-by-blackcatkig?_pos=16&_sid=aa6243602&_ss=r
site kigurumi references 158 : https://blackcatkig.com/products/kozume-kenma-haikyuu-kigurumi-mask-by-blackcatkig?_pos=17&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/kozume-kenma-haikyuu-kigurumi-mask-by-blackcatkig?_pos=17&_sid=aa6243602&_ss=r
site kigurumi references 159 : https://blackcatkig.com/products/yelan-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=18&_sid=aa6243602&_ss=r | archive: https://web.archive.org/web/*/https://blackcatkig.com/products/yelan-genshin-impact-kigurumi-mask-by-blackcatkig?_pos=18&_sid=aa6243602&_ss=r
x.com kigurumi references (8): https://x.com/BKC_BlacKCat/status/2084944990497894853, https://x.com/BKC_BlacKCat/status/2082778779081114053, https://x.com/BKC_BlacKCat/status/2079511506073600031, https://x.com/BKC_BlacKCat/status/2078067646327931227, https://x.com/BKC_BlacKCat/status/2075164729463775533, https://x.com/BKC_BlacKCat/status/2068988815361130851, https://x.com/BKC_BlacKCat/status/2067189602499391708, https://x.com/BKC_BlacKCat/status/2065363571605922052
x.com kigurumi hashtag-only references (11): https://x.com/BKC_BlacKCat/status/2085691343607865541, https://x.com/BKC_BlacKCat/status/2084223707103502631, https://x.com/BKC_BlacKCat/status/2082002456641499479, https://x.com/BKC_BlacKCat/status/2080478244927877473, https://x.com/BKC_BlacKCat/status/2077270706057007259, https://x.com/BKC_BlacKCat/status/2076519013937783187, https://x.com/BKC_BlacKCat/status/2073370235743121902, https://x.com/BKC_BlacKCat/status/2072626008151433463, https://x.com/BKC_BlacKCat/status/2071543647787753841, https://x.com/BKC_BlacKCat/status/2070099825459429611, https://x.com/BKC_BlacKCat/status/2066457488967553400
x.com kigurumi bio references (1): https://x.com/BKC_BlacKCat
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (2): https://x.com/BKC_BlacKCat/status/2082002456641499479, https://x.com/BKC_BlacKCat/status/2073370235743121902
x.com 着ぐるみ bio references: none (0)

maker: Fantasy Masks
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (15): https://x.com/FantasyMasks_/status/1955973619697459537, https://x.com/FantasyMasks_/status/1936786617022431672, https://x.com/FantasyMasks_/status/1927681118763155950, https://x.com/FantasyMasks_/status/1925503364982612123, https://x.com/FantasyMasks_/status/1920451153214476590, https://x.com/FantasyMasks_/status/1912338112623301092, https://x.com/FantasyMasks_/status/1909881745018957864, https://x.com/FantasyMasks_/status/1904785060416675907, https://x.com/FantasyMasks_/status/1901171196562985123, https://x.com/FantasyMasks_/status/1898202273538568242, https://x.com/FantasyMasks_/status/1895308901069042083, https://x.com/FantasyMasks_/status/1892789800383459528, https://x.com/FantasyMasks_/status/1886610794764492922, https://x.com/FantasyMasks_/status/1884253880361574810, https://x.com/FantasyMasks_/status/1883202136483545366
x.com kigurumi hashtag-only references (5): https://x.com/FantasyMasks_/status/1934297057168396625, https://x.com/FantasyMasks_/status/1929133013616431436, https://x.com/FantasyMasks_/status/1921959168535134264, https://x.com/FantasyMasks_/status/1909882251435032987, https://x.com/FantasyMasks_/status/1890625366668063028
x.com kigurumi bio references (1): https://x.com/FantasyMasks_
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Goukaou
region: Taiwan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references (10): https://x.com/goukaou/status/2085286749962645855, https://x.com/goukaou/status/2083084974660649171, https://x.com/goukaou/status/2080300622029660258, https://x.com/goukaou/status/2079141815576621308, https://x.com/goukaou/status/2078003083955912707, https://x.com/goukaou/status/2070020403490324484, https://x.com/goukaou/status/2067169158807408716, https://x.com/goukaou/status/2063987572779696172, https://x.com/goukaou/status/2060372437947334931, https://x.com/goukaou/status/2056273418157449254
x.com animegao bio references (1): https://x.com/goukaou
site kigurumi references 1 : https://www.gko-kig.com/ | archive: https://web.archive.org/web/*/https://www.gko-kig.com/
site kigurumi references 2 : https://www.gko-kig.com/goukaou | archive: https://web.archive.org/web/*/https://www.gko-kig.com/goukaou
site kigurumi references 3 : https://www.gko-kig.com/zentai-suit | archive: https://web.archive.org/web/*/https://www.gko-kig.com/zentai-suit
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (10): https://x.com/goukaou/status/2085286749962645855, https://x.com/goukaou/status/2083084974660649171, https://x.com/goukaou/status/2080300622029660258, https://x.com/goukaou/status/2079141815576621308, https://x.com/goukaou/status/2078003083955912707, https://x.com/goukaou/status/2070020403490324484, https://x.com/goukaou/status/2067169158807408716, https://x.com/goukaou/status/2063987572779696172, https://x.com/goukaou/status/2060372437947334931, https://x.com/goukaou/status/2056273418157449254
x.com kigurumi bio references (1): https://x.com/goukaou
site 着ぐるみ references 1 : https://www.gko-kig.com/diymask-jp | archive: https://web.archive.org/web/*/https://www.gko-kig.com/diymask-jp
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (10): https://x.com/goukaou/status/2085286749962645855, https://x.com/goukaou/status/2083084974660649171, https://x.com/goukaou/status/2080300622029660258, https://x.com/goukaou/status/2079141815576621308, https://x.com/goukaou/status/2078003083955912707, https://x.com/goukaou/status/2070020403490324484, https://x.com/goukaou/status/2067169158807408716, https://x.com/goukaou/status/2063987572779696172, https://x.com/goukaou/status/2060372437947334931, https://x.com/goukaou/status/2056273418157449254
x.com 着ぐるみ bio references (1): https://x.com/goukaou

maker: Haagaau Kigurumi Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (1): https://x.com/haagaau_GF_EN/status/1882438516879319451
x.com kigurumi hashtag-only references (1): https://x.com/haagaau_GF_EN/status/2003347284038418863
x.com kigurumi bio references (1): https://x.com/haagaau_GF_EN
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (18): https://x.com/haagaau_GF_EN/status/2003347284038418863, https://x.com/haagaau_GF_EN/status/1981966109013061686, https://x.com/haagaau_GF_EN/status/1942476046617698377, https://x.com/haagaau_GF_EN/status/1942475267559284943, https://x.com/haagaau_GF_EN/status/1906221803216801938, https://x.com/haagaau_GF_EN/status/1906221029451583572, https://x.com/haagaau_GF_EN/status/1906220406006010078, https://x.com/haagaau_GF_EN/status/1904360990390751576, https://x.com/haagaau_GF_EN/status/1904353091623022993, https://x.com/haagaau_GF_EN/status/1866423298545840329, https://x.com/haagaau_GF_EN/status/1866422861411291640, https://x.com/haagaau_GF_EN/status/1864527008845144558, https://x.com/haagaau_GF_EN/status/1864526765214855512, https://x.com/haagaau_GF_EN/status/1864329867447197700, https://x.com/haagaau_GF_EN/status/1864329587041218570, https://x.com/haagaau_GF_EN/status/1864329498608501176, https://x.com/haagaau_GF_EN/status/1830446743588134999, https://x.com/haagaau_GF_EN/status/1830443993554907228
x.com 着ぐるみ bio references: none (0)

maker: Heyaoheyao
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
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
site kigurumi references 17 : https://heyaoheyao.com/products/huajiao-hadatai-heyaoheyao-kigurumi-tights | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/huajiao-hadatai-heyaoheyao-kigurumi-tights
site kigurumi references 18 : https://heyaoheyao.com/products/huixiang-kigurumi-doll-suit-heyaoheyao | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/huixiang-kigurumi-doll-suit-heyaoheyao
site kigurumi references 19 : https://heyaoheyao.com/products/huajiao-hadatai-heyaoheyao-kigurumi-latex | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/huajiao-hadatai-heyaoheyao-kigurumi-latex
site kigurumi references 20 : https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-h | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-h
site kigurumi references 21 : https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-%E8%8A%B1%E5%8D%B7-02 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/in-stock-heyaoheyao-kigurumi-mask-%E8%8A%B1%E5%8D%B7-02
site kigurumi references 22 : https://heyaoheyao.com/collections/all?page=2 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/collections/all?page=2
site kigurumi references 23 : https://heyaoheyao.com/products/deposit2026 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/deposit2026
site kigurumi references 24 : https://heyaoheyao.com/products/final-payment2026 | archive: https://web.archive.org/web/*/https://heyaoheyao.com/products/final-payment2026
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: HiDolls
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (9): https://x.com/HiDolls_mm/status/2085908857671602482, https://x.com/HiDolls_mm/status/2083734529366540547, https://x.com/HiDolls_mm/status/2083372142591410643, https://x.com/HiDolls_mm/status/2082647369930387682, https://x.com/HiDolls_mm/status/2082284980517151150, https://x.com/HiDolls_mm/status/2081922591212916806, https://x.com/HiDolls_mm/status/2080835429364830243, https://x.com/HiDolls_mm/status/2080473042669687241, https://x.com/HiDolls_mm/status/2080112411701305766
x.com kigurumi hashtag-only references (10): https://x.com/HiDolls_mm/status/2086271249634705794, https://x.com/HiDolls_mm/status/2085576667959894361, https://x.com/HiDolls_mm/status/2085199179618414644, https://x.com/HiDolls_mm/status/2084821698294190179, https://x.com/HiDolls_mm/status/2084459307433631949, https://x.com/HiDolls_mm/status/2084112028634062897, https://x.com/HiDolls_mm/status/2083024864626270270, https://x.com/HiDolls_mm/status/2081575308843524481, https://x.com/HiDolls_mm/status/2081228012494983403, https://x.com/HiDolls_mm/status/2079778464115347783
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (4): https://x.com/HiDolls_mm/status/2084821698294190179, https://x.com/HiDolls_mm/status/2084112028634062897, https://x.com/HiDolls_mm/status/2081228012494983403, https://x.com/HiDolls_mm/status/2079778464115347783
x.com 着ぐるみ bio references (1): https://x.com/HiDolls_mm

maker: Kaga Kigurumi
region: Hong Kong
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://kagakii.com/ | archive: https://web.archive.org/web/*/https://kagakii.com/
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/kagakii
site 着ぐるみ references 1 : https://kagakii.com/ | archive: https://web.archive.org/web/*/https://kagakii.com/
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/kagakii

maker: KFY Aniplus
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (10): https://x.com/KFY_Aniplus/status/2061296681589588080, https://x.com/KFY_Aniplus/status/2057474865951805946, https://x.com/KFY_Aniplus/status/2054537859630239805, https://x.com/KFY_Aniplus/status/2051874597528592406, https://x.com/KFY_Aniplus/status/2044435302429937991, https://x.com/KFY_Aniplus/status/2036076062422241440, https://x.com/KFY_Aniplus/status/2031943265952362870, https://x.com/KFY_Aniplus/status/2029768939882868827, https://x.com/KFY_Aniplus/status/2027015870678245401, https://x.com/KFY_Aniplus/status/2018332959238156753
x.com kigurumi hashtag-only references (7): https://x.com/KFY_Aniplus/status/2060674932779200681, https://x.com/KFY_Aniplus/status/2055505652055978360, https://x.com/KFY_Aniplus/status/2051633425589961118, https://x.com/KFY_Aniplus/status/2042215946174235017, https://x.com/KFY_Aniplus/status/2035368357420261411, https://x.com/KFY_Aniplus/status/2029568547941482867, https://x.com/KFY_Aniplus/status/2020475520069115977
x.com kigurumi bio references (1): https://x.com/KFY_Aniplus
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/KFY_Aniplus

maker: KigLand
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://kig.land/en-US | archive: https://web.archive.org/web/*/https://kig.land/en-US
x.com kigurumi references (7): https://x.com/Remi_IO/status/2079506922462654550, https://x.com/Remi_IO/status/2079145540970070374, https://x.com/Remi_IO/status/2072619287500746827, https://x.com/Remi_IO/status/2055960272326852610, https://x.com/Remi_IO/status/2054916797468680253, https://x.com/Remi_IO/status/2052271837372100663, https://x.com/Remi_IO/status/2036040551636852881
x.com kigurumi hashtag-only references (5): https://x.com/Remi_IO/status/2082068847990046876, https://x.com/Remi_IO/status/2079870065260843337, https://x.com/Remi_IO/status/2052718675858526715, https://x.com/Remi_IO/status/2051691974726672537, https://x.com/Remi_IO/status/2043687957421609170
x.com kigurumi bio references (1): https://x.com/Remi_IO
site 着ぐるみ references 1 : https://kig.land/en-US | archive: https://web.archive.org/web/*/https://kig.land/en-US
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (4): https://x.com/Remi_IO/status/2082068847990046876, https://x.com/Remi_IO/status/2079870065260843337, https://x.com/Remi_IO/status/2079506922462654550, https://x.com/Remi_IO/status/2079145540970070374
x.com 着ぐるみ bio references: none (0)

maker: Kirisame Factory
region: Hong Kong/Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://kirisamefactory.com/en/ | archive: https://web.archive.org/web/*/https://kirisamefactory.com/en/
site kigurumi references 2 : https://kirisamefactory.com/en/prod/mask | archive: https://web.archive.org/web/*/https://kirisamefactory.com/en/prod/mask
site kigurumi references 3 : https://kirisamefactory.com/en/legal/guide | archive: https://web.archive.org/web/*/https://kirisamefactory.com/en/legal/guide
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (10): https://x.com/KirisameFactory/status/2028072788272255212, https://x.com/KirisameFactory/status/1946505910752530504, https://x.com/KirisameFactory/status/1939210413130031581, https://x.com/KirisameFactory/status/1930917275554767235, https://x.com/KirisameFactory/status/1920781976866288120, https://x.com/KirisameFactory/status/1905231060721598974, https://x.com/KirisameFactory/status/1905230619636056245, https://x.com/KirisameFactory/status/1903444706111172787, https://x.com/KirisameFactory/status/1899016846839583102, https://x.com/KirisameFactory/status/1895794219983519776
x.com kigurumi bio references (1): https://x.com/KirisameFactory
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (10): https://x.com/KirisameFactory/status/2028072788272255212, https://x.com/KirisameFactory/status/1946505910752530504, https://x.com/KirisameFactory/status/1939210413130031581, https://x.com/KirisameFactory/status/1930917275554767235, https://x.com/KirisameFactory/status/1920781976866288120, https://x.com/KirisameFactory/status/1905231060721598974, https://x.com/KirisameFactory/status/1905230619636056245, https://x.com/KirisameFactory/status/1903444706111172787, https://x.com/KirisameFactory/status/1899016846839583102, https://x.com/KirisameFactory/status/1895794219983519776
x.com 着ぐるみ bio references (1): https://x.com/KirisameFactory

maker: Lightning
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (19): https://x.com/lightning520/status/2004263619568263348, https://x.com/lightning520/status/1989277500539916645, https://x.com/lightning520/status/1989277268661940536, https://x.com/lightning520/status/1989277056996384769, https://x.com/lightning520/status/1989276751332348285, https://x.com/lightning520/status/1988169646684729673, https://x.com/lightning520/status/1981319161839223079, https://x.com/lightning520/status/1980292136525500662, https://x.com/lightning520/status/1978111220407509343, https://x.com/lightning520/status/1977397447975391477, https://x.com/lightning520/status/1976662274078318595, https://x.com/lightning520/status/1975218314139042053, https://x.com/lightning520/status/1974539022497353731, https://x.com/lightning520/status/1973797156709675438, https://x.com/lightning520/status/1971963523510292751, https://x.com/lightning520/status/1970864253176553662, https://x.com/lightning520/status/1970550108711461031, https://x.com/lightning520/status/1969091359412802026, https://x.com/lightning520/status/1968645307039670463
x.com kigurumi bio references (1): https://x.com/lightning520
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: MidDreamKigu
region: Mainland China
site animegao references 1 : https://kiglover.com/ | archive: https://web.archive.org/web/20260809182429/https://kiglover.com/
site animegao references 2 : https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide | archive: https://web.archive.org/web/20260809182442/https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide
site animegao references 3 : https://kiglover.com/products/kiglover-animegao-kigu-mask-quote-request | archive: https://web.archive.org/web/20260809182459/https://kiglover.com/products/kiglover-animegao-kigu-mask-quote-request
site animegao references 4 : https://kiglover.com/products/cute-little-devil-kigurumi-mask-middream-kigukiglover | archive: https://web.archive.org/web/20260809182512/https://kiglover.com/products/cute-little-devil-kigurumi-mask-middream-kigukiglover
site animegao references 5 : https://kiglover.com/products/liskarm-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182525/https://kiglover.com/products/liskarm-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site animegao references 6 : https://kiglover.com/products/w-wanted-ver-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182606/https://kiglover.com/products/w-wanted-ver-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site animegao references 7 : https://kiglover.com/products/mon3tr-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182619/https://kiglover.com/products/mon3tr-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site animegao references 8 : https://kiglover.com/products/original-character-animegao-kigurumi-cosplay-mask-from-sea83200776-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182628/https://kiglover.com/products/original-character-animegao-kigurumi-cosplay-mask-from-sea83200776-custom-commission-showcase-kiglover
site animegao references 9 : https://kiglover.com/products/zozzo-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182703/https://kiglover.com/products/zozzo-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site animegao references 10 : https://kiglover.com/products/azur-lane-laffey-ii-animegao-kigurumi-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182718/https://kiglover.com/products/azur-lane-laffey-ii-animegao-kigurumi-mask-custom-commission-showcase-kiglover
site animegao references 11 : https://kiglover.com/products/final-payment-handmake-kigu-mask-commission | archive: https://web.archive.org/web/20260809182737/https://kiglover.com/products/final-payment-handmake-kigu-mask-commission
site animegao references 12 : https://kiglover.com/products/animegao-kigu-mask-final-payment | archive: https://web.archive.org/web/20260809182746/https://kiglover.com/products/animegao-kigu-mask-final-payment
site animegao references 13 : https://kiglover.com/collections/custom-kigurumi-mask-commission-gallery-kiglover | archive: https://web.archive.org/web/*/https://kiglover.com/collections/custom-kigurumi-mask-commission-gallery-kiglover
site animegao references 14 : https://kiglover.com/collections/all | archive: https://web.archive.org/web/20260809182806/https://kiglover.com/collections/all
site animegao references 15 : https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information | archive: https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information
site animegao references 16 : https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide | archive: https://web.archive.org/web/20260809182442/https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://kiglover.com/ | archive: https://web.archive.org/web/20260809182429/https://kiglover.com/
site kigurumi references 2 : https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide | archive: https://web.archive.org/web/20260809182442/https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide
site kigurumi references 3 : https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/choose-your-kigu-mask-wig | archive: https://web.archive.org/web/*/https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/choose-your-kigu-mask-wig
site kigurumi references 4 : https://kiglover.com/policies/shipping-policy | archive: https://web.archive.org/web/*/https://kiglover.com/policies/shipping-policy
site kigurumi references 5 : https://kiglover.com/products/kiglover-animegao-kigu-mask-quote-request | archive: https://web.archive.org/web/20260809182459/https://kiglover.com/products/kiglover-animegao-kigu-mask-quote-request
site kigurumi references 6 : https://kiglover.com/products/order-balance-for-customer-someone-xe | archive: https://web.archive.org/web/*/https://kiglover.com/products/order-balance-for-customer-someone-xe
site kigurumi references 7 : https://kiglover.com/products/cute-little-devil-kigurumi-mask-middream-kigukiglover | archive: https://web.archive.org/web/20260809182512/https://kiglover.com/products/cute-little-devil-kigurumi-mask-middream-kigukiglover
site kigurumi references 8 : https://kiglover.com/products/faust-limbus-company-kigu-mask-custom-commission-showcase-dreamweave-kigu-formerly-kiglover | archive: https://web.archive.org/web/*/https://kiglover.com/products/faust-limbus-company-kigu-mask-custom-commission-showcase-dreamweave-kigu-formerly-kiglover
site kigurumi references 9 : https://kiglover.com/products/plum-vrchat-kigu-mask-custom-commission-showcase-dreamweave-kigu-formerly-kiglover | archive: https://web.archive.org/web/*/https://kiglover.com/products/plum-vrchat-kigu-mask-custom-commission-showcase-dreamweave-kigu-formerly-kiglover
site kigurumi references 10 : https://kiglover.com/products/liskarm-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182525/https://kiglover.com/products/liskarm-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site kigurumi references 11 : https://kiglover.com/products/w-wanted-ver-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182606/https://kiglover.com/products/w-wanted-ver-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site kigurumi references 12 : https://kiglover.com/products/mon3tr-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182619/https://kiglover.com/products/mon3tr-arknights-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site kigurumi references 13 : https://kiglover.com/products/original-character-animegao-kigurumi-cosplay-mask-from-sea83200776-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182628/https://kiglover.com/products/original-character-animegao-kigurumi-cosplay-mask-from-sea83200776-custom-commission-showcase-kiglover
site kigurumi references 14 : https://kiglover.com/products/zozzo-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182703/https://kiglover.com/products/zozzo-animegao-kigurumi-cosplay-mask-custom-commission-showcase-kiglover
site kigurumi references 15 : https://kiglover.com/products/azur-lane-laffey-ii-animegao-kigurumi-mask-custom-commission-showcase-kiglover | archive: https://web.archive.org/web/20260809182718/https://kiglover.com/products/azur-lane-laffey-ii-animegao-kigurumi-mask-custom-commission-showcase-kiglover
site kigurumi references 16 : https://kiglover.com/products/final-payment-handmake-kigu-mask-commission | archive: https://web.archive.org/web/20260809182737/https://kiglover.com/products/final-payment-handmake-kigu-mask-commission
site kigurumi references 17 : https://kiglover.com/products/animegao-kigu-mask-final-payment | archive: https://web.archive.org/web/20260809182746/https://kiglover.com/products/animegao-kigu-mask-final-payment
site kigurumi references 18 : https://kiglover.com/collections/custom-kigurumi-mask-commission-gallery-kiglover | archive: https://web.archive.org/web/*/https://kiglover.com/collections/custom-kigurumi-mask-commission-gallery-kiglover
site kigurumi references 19 : https://kiglover.com/policies/refund-policy | archive: https://web.archive.org/web/*/https://kiglover.com/policies/refund-policy
site kigurumi references 20 : https://kiglover.com/collections/all | archive: https://web.archive.org/web/20260809182806/https://kiglover.com/collections/all
site kigurumi references 21 : https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information | archive: https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information
site kigurumi references 22 : https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide | archive: https://web.archive.org/web/20260809182442/https://kiglover.com/blogs/kiglover-animegao-kigu-mask-commission-information/animegao-kigurumi-mask-commission-guide
site kigurumi references 23 : https://kiglover.com/products/manhattan-cafe-animegao-kigu-mask | archive: https://web.archive.org/web/*/https://kiglover.com/products/manhattan-cafe-animegao-kigu-mask
x.com kigurumi references (1): https://x.com/kiglover_site/status/2080313221924163854
x.com kigurumi hashtag-only references (7): https://x.com/kiglover_site/status/2085427233494065240, https://x.com/kiglover_site/status/2084672638765404667, https://x.com/kiglover_site/status/2083262857450229799, https://x.com/kiglover_site/status/2082002117892456563, https://x.com/kiglover_site/status/2078912860533424294, https://x.com/kiglover_site/status/2078163058086568118, https://x.com/kiglover_site/status/2076295979741987111
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (5): https://x.com/kiglover_site/status/2085427233494065240, https://x.com/kiglover_site/status/2084672638765404667, https://x.com/kiglover_site/status/2083262857450229799, https://x.com/kiglover_site/status/2082002117892456563, https://x.com/kiglover_site/status/2078912860533424294
x.com 着ぐるみ bio references: none (0)

maker: Natural Factory
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (10): https://x.com/NaturalFactory2/status/2086293189145841669, https://x.com/NaturalFactory2/status/2084504805322473799, https://x.com/NaturalFactory2/status/2068648413139444024, https://x.com/NaturalFactory2/status/2067117115799372175, https://x.com/NaturalFactory2/status/2065369051103478149, https://x.com/NaturalFactory2/status/2064370811830673523, https://x.com/NaturalFactory2/status/2058929448813256762, https://x.com/NaturalFactory2/status/2058126727986200958, https://x.com/NaturalFactory2/status/2056270098227450010, https://x.com/NaturalFactory2/status/2050882641067716663
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/NaturalFactory2
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (11): https://x.com/NaturalFactory2/status/2086293189145841669, https://x.com/NaturalFactory2/status/2084504805322473799, https://x.com/NaturalFactory2/status/2070110864955584542, https://x.com/NaturalFactory2/status/2068648413139444024, https://x.com/NaturalFactory2/status/2067117115799372175, https://x.com/NaturalFactory2/status/2065369051103478149, https://x.com/NaturalFactory2/status/2064370811830673523, https://x.com/NaturalFactory2/status/2058929448813256762, https://x.com/NaturalFactory2/status/2058126727986200958, https://x.com/NaturalFactory2/status/2056270098227450010, https://x.com/NaturalFactory2/status/2050882641067716663
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/NaturalFactory2

maker: New Face Doll
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
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
site kigurumi references 12 : https://x.com/Carilonponyplay/status/1905647695642902809 | archive: https://web.archive.org/web/*/https://x.com/Carilonponyplay/status/1905647695642902809
site kigurumi references 13 : https://x.com/saladma78034164/status/1732277111862567188 | archive: https://web.archive.org/web/*/https://x.com/saladma78034164/status/1732277111862567188
site kigurumi references 14 : https://x.com/Carno_Tor0/status/1993600866423885959 | archive: https://web.archive.org/web/*/https://x.com/Carno_Tor0/status/1993600866423885959
site kigurumi references 15 : https://x.com/KarinaKigu/status/1731504699247882579 | archive: https://web.archive.org/web/*/https://x.com/KarinaKigu/status/1731504699247882579
x.com kigurumi references (15): https://x.com/NewfacedolL/status/1731133903719784858, https://x.com/NewfacedolL/status/1730771515980009972, https://x.com/NewfacedolL/status/1730408876254605610, https://x.com/NewfacedolL/status/1730046237045629099, https://x.com/NewfacedolL/status/1729321209475822057, https://x.com/NewfacedolL/status/1728958569821638915, https://x.com/NewfacedolL/status/1728595930340012202, https://x.com/NewfacedolL/status/1728233039384183071, https://x.com/NewfacedolL/status/1727869896724500749, https://x.com/NewfacedolL/status/1727507258899382498, https://x.com/NewfacedolL/status/1727144617207111771, https://x.com/NewfacedolL/status/1726780971104587881, https://x.com/NewfacedolL/status/1726417282585575733, https://x.com/NewfacedolL/status/1725082656877294009, https://x.com/NewfacedolL/status/1684854432293613568
x.com kigurumi hashtag-only references (1): https://x.com/NewfacedolL/status/1615601569789267968
x.com kigurumi bio references (1): https://x.com/NewfacedolL
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (1): https://x.com/NewfacedolL/status/1615601569789267968
x.com 着ぐるみ bio references: none (0)

maker: Shinkai Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (14): https://x.com/ShinkaiWorkshop/status/2071152314824736837, https://x.com/ShinkaiWorkshop/status/2060720622968123891, https://x.com/ShinkaiWorkshop/status/2050251753002873073, https://x.com/ShinkaiWorkshop/status/2045791554925912084, https://x.com/ShinkaiWorkshop/status/2045096450712014909, https://x.com/ShinkaiWorkshop/status/2044723776039145912, https://x.com/ShinkaiWorkshop/status/2036077298667905079, https://x.com/ShinkaiWorkshop/status/2029532648717386069, https://x.com/ShinkaiWorkshop/status/2016502449037840865, https://x.com/ShinkaiWorkshop/status/2010097193907302468, https://x.com/ShinkaiWorkshop/status/2005615072266354824, https://x.com/ShinkaiWorkshop/status/2004789427059789926, https://x.com/ShinkaiWorkshop/status/2004511833315754161, https://x.com/ShinkaiWorkshop/status/2003450879312343529
x.com kigurumi bio references (1): https://x.com/ShinkaiWorkshop
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (14): https://x.com/ShinkaiWorkshop/status/2071152314824736837, https://x.com/ShinkaiWorkshop/status/2060720622968123891, https://x.com/ShinkaiWorkshop/status/2050251753002873073, https://x.com/ShinkaiWorkshop/status/2045791554925912084, https://x.com/ShinkaiWorkshop/status/2045096450712014909, https://x.com/ShinkaiWorkshop/status/2044723776039145912, https://x.com/ShinkaiWorkshop/status/2036077298667905079, https://x.com/ShinkaiWorkshop/status/2029532648717386069, https://x.com/ShinkaiWorkshop/status/2016502449037840865, https://x.com/ShinkaiWorkshop/status/2010097193907302468, https://x.com/ShinkaiWorkshop/status/2005615072266354824, https://x.com/ShinkaiWorkshop/status/2004789427059789926, https://x.com/ShinkaiWorkshop/status/2004511833315754161, https://x.com/ShinkaiWorkshop/status/2003450879312343529
x.com 着ぐるみ bio references (1): https://x.com/ShinkaiWorkshop

maker: Build Up Studio SIGMA
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://www.buildupstudiosigma.com/gallery/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/gallery/
site kigurumi references 2 : https://www.buildupstudiosigma.com/gallery/twinangel/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/gallery/twinangel/
site kigurumi references 3 : https://www.buildupstudiosigma.com/archive/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/archive/
site kigurumi references 4 : https://buildupstudiosigma.com/contents/ena15/message/17.html | archive: https://web.archive.org/web/*/https://buildupstudiosigma.com/contents/ena15/message/17.html
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references 1 : https://www.buildupstudiosigma.com/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/
site 着ぐるみ references 2 : https://www.buildupstudiosigma.com/about/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/about/
site 着ぐるみ references 3 : https://www.buildupstudiosigma.com/product/ena/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/ena/
site 着ぐるみ references 4 : https://www.buildupstudiosigma.com/gallery/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/gallery/
site 着ぐるみ references 5 : https://www.buildupstudiosigma.com/goods/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/goods/
site 着ぐるみ references 6 : https://www.buildupstudiosigma.com/ena20/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/ena20/
site 着ぐるみ references 7 : https://www.buildupstudiosigma.com/product/yurufuwa/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/yurufuwa/
site 着ぐるみ references 8 : https://www.buildupstudiosigma.com/product/yurufuwa/?t=overview | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/yurufuwa/?t=overview
site 着ぐるみ references 9 : https://www.buildupstudiosigma.com/product/yurufuwa/?t=spec | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/yurufuwa/?t=spec
site 着ぐるみ references 10 : https://www.buildupstudiosigma.com/product/yurufuwa/?t=option | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/yurufuwa/?t=option
site 着ぐるみ references 11 : https://www.buildupstudiosigma.com/product/amikomi/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/amikomi/
site 着ぐるみ references 12 : https://www.buildupstudiosigma.com/product/amikomi/?t=overview | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/amikomi/?t=overview
site 着ぐるみ references 13 : https://www.buildupstudiosigma.com/product/amikomi/?t=spec | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/amikomi/?t=spec
site 着ぐるみ references 14 : https://www.buildupstudiosigma.com/product/amikomi/?t=option | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/amikomi/?t=option
site 着ぐるみ references 15 : https://www.buildupstudiosigma.com/product/ena/?g=ena2 | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/ena/?g=ena2
site 着ぐるみ references 16 : https://www.buildupstudiosigma.com/product/ena/?g=ena3 | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/ena/?g=ena3
site 着ぐるみ references 17 : https://www.buildupstudiosigma.com/product/ena/?g=ena4 | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/ena/?g=ena4
site 着ぐるみ references 18 : https://www.buildupstudiosigma.com/product/ena/?g=ena5 | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/ena/?g=ena5
site 着ぐるみ references 19 : https://www.buildupstudiosigma.com/product/ena/?t=overview | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/ena/?t=overview
site 着ぐるみ references 20 : https://www.buildupstudiosigma.com/product/ena/?t=spec | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/ena/?t=spec
site 着ぐるみ references 21 : https://www.buildupstudiosigma.com/product/ena/?t=option | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/ena/?t=option
site 着ぐるみ references 22 : https://www.buildupstudiosigma.com/product/tio/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tio/
site 着ぐるみ references 23 : https://www.buildupstudiosigma.com/product/tio/?g=tio2 | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tio/?g=tio2
site 着ぐるみ references 24 : https://www.buildupstudiosigma.com/product/tio/?g=tio3 | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tio/?g=tio3
site 着ぐるみ references 25 : https://www.buildupstudiosigma.com/product/tio/?t=overview | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tio/?t=overview
site 着ぐるみ references 26 : https://www.buildupstudiosigma.com/product/tio/?t=spec | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tio/?t=spec
site 着ぐるみ references 27 : https://www.buildupstudiosigma.com/product/tio/?t=option | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tio/?t=option
site 着ぐるみ references 28 : https://www.buildupstudiosigma.com/product/tria/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tria/
site 着ぐるみ references 29 : https://www.buildupstudiosigma.com/product/tria/?g=tria2 | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tria/?g=tria2
site 着ぐるみ references 30 : https://www.buildupstudiosigma.com/product/tria/?t=overview | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tria/?t=overview
site 着ぐるみ references 31 : https://www.buildupstudiosigma.com/product/tria/?t=spec | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tria/?t=spec
site 着ぐるみ references 32 : https://www.buildupstudiosigma.com/product/tria/?t=option | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tria/?t=option
site 着ぐるみ references 33 : https://www.buildupstudiosigma.com/product/tris/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tris/
site 着ぐるみ references 34 : https://www.buildupstudiosigma.com/product/tris/?g=tris2 | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tris/?g=tris2
site 着ぐるみ references 35 : https://www.buildupstudiosigma.com/product/tris/?t=overview | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tris/?t=overview
site 着ぐるみ references 36 : https://www.buildupstudiosigma.com/product/tris/?t=spec | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tris/?t=spec
site 着ぐるみ references 37 : https://www.buildupstudiosigma.com/product/tris/?t=option | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/product/tris/?t=option
site 着ぐるみ references 38 : https://www.buildupstudiosigma.com/event/wf2018w/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/event/wf2018w/
site 着ぐるみ references 39 : https://www.buildupstudiosigma.com/gallery/twinangel/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/gallery/twinangel/
site 着ぐるみ references 40 : https://www.buildupstudiosigma.com/event/wf2018w-mask/ | archive: https://web.archive.org/web/*/https://www.buildupstudiosigma.com/event/wf2018w-mask/
site 着ぐるみ references 41 : https://buildupstudiosigma.com/contents/ena15/message/07.html | archive: https://web.archive.org/web/*/https://buildupstudiosigma.com/contents/ena15/message/07.html
site 着ぐるみ references 42 : https://buildupstudiosigma.com/contents/ena15/message/11.html | archive: https://web.archive.org/web/*/https://buildupstudiosigma.com/contents/ena15/message/11.html
site 着ぐるみ references 43 : https://buildupstudiosigma.com/contents/ena15/message/29.html | archive: https://web.archive.org/web/*/https://buildupstudiosigma.com/contents/ena15/message/29.html
site 着ぐるみ references 44 : https://buildupstudiosigma.com/contents/ena15/message/41.html | archive: https://web.archive.org/web/*/https://buildupstudiosigma.com/contents/ena15/message/41.html
site 着ぐるみ references 45 : https://buildupstudiosigma.com/contents/ena15/message/51.html | archive: https://web.archive.org/web/*/https://buildupstudiosigma.com/contents/ena15/message/51.html
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/SIGMA93996951

maker: Scarlet0rabbit
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (2): https://x.com/Scarlet0rabbit/status/1928374234864132544, https://x.com/Scarlet0rabbit/status/1903033375021208032
x.com kigurumi hashtag-only references (17): https://x.com/Scarlet0rabbit/status/2082821855417860509, https://x.com/Scarlet0rabbit/status/2082821437422030868, https://x.com/Scarlet0rabbit/status/2082821140096188894, https://x.com/Scarlet0rabbit/status/2036390960570216583, https://x.com/Scarlet0rabbit/status/1987915653584666675, https://x.com/Scarlet0rabbit/status/1979785083956625876, https://x.com/Scarlet0rabbit/status/1978878813259112470, https://x.com/Scarlet0rabbit/status/1960726357010473166, https://x.com/Scarlet0rabbit/status/1944604966200688980, https://x.com/Scarlet0rabbit/status/1935968594372051380, https://x.com/Scarlet0rabbit/status/1932316370211135969, https://x.com/Scarlet0rabbit/status/1932070426701861184, https://x.com/Scarlet0rabbit/status/1929477229232132254, https://x.com/Scarlet0rabbit/status/1921040108934807869, https://x.com/Scarlet0rabbit/status/1916517052711424327, https://x.com/Scarlet0rabbit/status/1911067982966501633, https://x.com/Scarlet0rabbit/status/1910176001101091210
x.com kigurumi bio references (1): https://x.com/Scarlet0rabbit
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (13): https://x.com/Scarlet0rabbit/status/2082821437422030868, https://x.com/Scarlet0rabbit/status/2082821140096188894, https://x.com/Scarlet0rabbit/status/2036390960570216583, https://x.com/Scarlet0rabbit/status/1979785083956625876, https://x.com/Scarlet0rabbit/status/1978878813259112470, https://x.com/Scarlet0rabbit/status/1960726357010473166, https://x.com/Scarlet0rabbit/status/1944604966200688980, https://x.com/Scarlet0rabbit/status/1929477229232132254, https://x.com/Scarlet0rabbit/status/1928374234864132544, https://x.com/Scarlet0rabbit/status/1921040108934807869, https://x.com/Scarlet0rabbit/status/1916517052711424327, https://x.com/Scarlet0rabbit/status/1910176001101091210, https://x.com/Scarlet0rabbit/status/1903033375021208032
x.com 着ぐるみ bio references (1): https://x.com/Scarlet0rabbit

maker: W Rabbit Mi
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (4): https://x.com/WithRabbitMI/status/1840017154286202924, https://x.com/WithRabbitMI/status/1806952419890192519, https://x.com/WithRabbitMI/status/1798649480293871875, https://x.com/WithRabbitMI/status/1798615646357582062
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: 4uuone
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/4uuone
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: A2 Laboratory
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (2): https://x.com/A2Laboratory/status/1892091641961320502, https://x.com/A2Laboratory/status/1892092101162049696
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (1): https://x.com/A2Laboratory/status/1892091639834763422
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/A2Laboratory

maker: Ayame Store
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references 1 : https://hadatai.jp/ja/easyorder.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/easyorder.html
site 着ぐるみ references 2 : https://hadatai.jp/ja/fullcustom.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/fullcustom.html
site 着ぐるみ references 3 : https://hadatai.jp/ja/app.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/app.html
site 着ぐるみ references 4 : https://hadatai.jp/ja/59b1bb.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/59b1bb.html
site 着ぐるみ references 5 : https://hadatai.jp/ja/1d1400.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/1d1400.html
site 着ぐるみ references 6 : https://hadatai.jp/ja/e5afc8.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/e5afc8.html
site 着ぐるみ references 7 : https://hadatai.jp/ja/7bf959.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/7bf959.html
site 着ぐるみ references 8 : https://hadatai.jp/ja/e665cf.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/e665cf.html
site 着ぐるみ references 9 : https://hadatai.jp/ja/829a83.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/829a83.html
site 着ぐるみ references 10 : https://hadatai.jp/ja/0cb731.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/0cb731.html
site 着ぐるみ references 11 : https://hadatai.jp/ja/1d8dae.html | archive: https://web.archive.org/web/*/https://hadatai.jp/ja/1d8dae.html
x.com 着ぐるみ references (2): https://x.com/ayamestore/status/2084839317000896554, https://x.com/ayamestore/status/2084476932431954070
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/ayamestore

maker: BEADOLL
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (1): https://x.com/BEADOLL_OS/status/2031627635709665722
x.com kigurumi hashtag-only references (11): https://x.com/BEADOLL_OS/status/2049853638051537111, https://x.com/BEADOLL_OS/status/2049853155891155315, https://x.com/BEADOLL_OS/status/2048763900745970064, https://x.com/BEADOLL_OS/status/2032020752460104046, https://x.com/BEADOLL_OS/status/2031720878975905869, https://x.com/BEADOLL_OS/status/2031432774461374527, https://x.com/BEADOLL_OS/status/2028439700210581871, https://x.com/BEADOLL_OS/status/2020824996093038684, https://x.com/BEADOLL_OS/status/2020819364291702917, https://x.com/BEADOLL_OS/status/2016855261848490371, https://x.com/BEADOLL_OS/status/2016850218588000414
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Bear Technique Studio
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (3): https://x.com/BearTechCenter/status/2082460192105746775, https://x.com/BearTechCenter/status/2076311453334929725, https://x.com/BearTechCenter/status/2073694080828334307
x.com kigurumi hashtag-only references (16): https://x.com/BearTechCenter/status/2081049618625032559, https://x.com/BearTechCenter/status/2080657980337627250, https://x.com/BearTechCenter/status/2079151063131902252, https://x.com/BearTechCenter/status/2077784180956762380, https://x.com/BearTechCenter/status/2075568438924415073, https://x.com/BearTechCenter/status/2075201629180273109, https://x.com/BearTechCenter/status/2074864795447386398, https://x.com/BearTechCenter/status/2074126987724300323, https://x.com/BearTechCenter/status/2073313869481836818, https://x.com/BearTechCenter/status/2073056460897185845, https://x.com/BearTechCenter/status/2071969229751156979, https://x.com/BearTechCenter/status/2071511294793126360, https://x.com/BearTechCenter/status/2070878703186587785, https://x.com/BearTechCenter/status/2070521513334415777, https://x.com/BearTechCenter/status/2069805104279265662, https://x.com/BearTechCenter/status/2069035308738658457
x.com kigurumi bio references (1): https://x.com/BearTechCenter
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Chiba Subaru
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/ChibaSubaru_Kig
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Chikima
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (3): https://x.com/i_chikima/status/2086467588532695231, https://x.com/i_chikima/status/2086465271645221144, https://x.com/i_chikima/status/2086421262159737148
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Chilca
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (1): https://x.com/CHILCACRAFTS/status/2016689013596496011
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/CHILCACRAFTS

maker: Chris and Meph
region: Canada
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://chrisandmeph.com/about/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/about/
site kigurumi references 2 : https://chrisandmeph.com/author/ctriff/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/author/ctriff/
site kigurumi references 3 : https://chrisandmeph.com/2022/04/30/lets-kick-this-old-school-with-trouble/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/2022/04/30/lets-kick-this-old-school-with-trouble/
site kigurumi references 4 : https://chrisandmeph.com/2022/04/27/here-comes-trouble/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/2022/04/27/here-comes-trouble/
site kigurumi references 5 : https://chrisandmeph.com/category/cosplay/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/category/cosplay/
site kigurumi references 6 : https://chrisandmeph.com/tag/cosplay/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/tag/cosplay/
site kigurumi references 7 : https://chrisandmeph.com/tag/cute/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/tag/cute/
site kigurumi references 8 : https://chrisandmeph.com/tag/kigurumi/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/tag/kigurumi/
site kigurumi references 9 : https://chrisandmeph.com/tag/making/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/tag/making/
site kigurumi references 10 : https://chrisandmeph.com/2019/02/14/cosplay-and-kigurumi-importance-of-play/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/2019/02/14/cosplay-and-kigurumi-importance-of-play/
site kigurumi references 11 : https://chrisandmeph.com/category/life/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/category/life/
site kigurumi references 12 : https://chrisandmeph.com/category/life/motivation/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/category/life/motivation/
site kigurumi references 13 : https://chrisandmeph.com/tag/conventions/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/tag/conventions/
site kigurumi references 14 : https://chrisandmeph.com/tag/life/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/tag/life/
site kigurumi references 15 : https://chrisandmeph.com/tag/passion/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/tag/passion/
site kigurumi references 16 : https://chrisandmeph.com/2019/01/24/why-kigurumi-why-that-scary-anime-mascot-thing/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/2019/01/24/why-kigurumi-why-that-scary-anime-mascot-thing/
site kigurumi references 17 : https://chrisandmeph.com/category/cosplay/kigurumi/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/category/cosplay/kigurumi/
site kigurumi references 18 : https://chrisandmeph.com/tag/crowds/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/tag/crowds/
site kigurumi references 19 : https://chrisandmeph.com/tag/friends/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/tag/friends/
site kigurumi references 20 : https://chrisandmeph.com/2019/01/06/learning-to-be-comfortable-with-being-uncomfortable/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/2019/01/06/learning-to-be-comfortable-with-being-uncomfortable/
site kigurumi references 21 : https://chrisandmeph.com/category/uncategorized/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/category/uncategorized/
site kigurumi references 22 : https://chrisandmeph.com/2019/01/03/attending-conventions-do-i-have-to-cosplay/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/2019/01/03/attending-conventions-do-i-have-to-cosplay/
site kigurumi references 23 : https://chrisandmeph.com/category/tradition/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/category/tradition/
site kigurumi references 24 : https://chrisandmeph.com/2019/01/02/making-friends-in-cosplay-how-i-met-your-mother/ | archive: https://web.archive.org/web/*/https://chrisandmeph.com/2019/01/02/making-friends-in-cosplay-how-i-met-your-mother/
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (4): https://x.com/ChrisAndMeph/status/2078287380860289290, https://x.com/ChrisAndMeph/status/1642665156714049537, https://x.com/ChrisAndMeph/status/1574121244819333120, https://x.com/ChrisAndMeph/status/1520602848752377856
x.com kigurumi bio references (1): https://x.com/ChrisAndMeph
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Cover
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (4): https://x.com/cover_plan/status/2081731109587698013, https://x.com/cover_plan/status/2081730916943299059, https://x.com/cover_plan/status/2081729936826732592, https://x.com/cover_plan/status/2081729394612261354
x.com kigurumi hashtag-only references (16): https://x.com/cover_plan/status/2086116867325018158, https://x.com/cover_plan/status/2086102206013641096, https://x.com/cover_plan/status/2085706582730723766, https://x.com/cover_plan/status/2085057296091299964, https://x.com/cover_plan/status/2084702389165338887, https://x.com/cover_plan/status/2084602384828043642, https://x.com/cover_plan/status/2084195475708919968, https://x.com/cover_plan/status/2083275420473114980, https://x.com/cover_plan/status/2082463092949287081, https://x.com/cover_plan/status/2081249566188540156, https://x.com/cover_plan/status/2080716890352361674, https://x.com/cover_plan/status/2080200773858992337, https://x.com/cover_plan/status/2079808875780522395, https://x.com/cover_plan/status/2079421339375714652, https://x.com/cover_plan/status/2078932773818298480, https://x.com/cover_plan/status/2078549979669713317
x.com kigurumi bio references (1): https://x.com/cover_plan
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: DAME Kigurumi
region: UK
site animegao references 1 : https://damekigurumi.com/ | archive: https://web.archive.org/web/20260809194235/https://damekigurumi.com/
site animegao references 2 : https://damekigurumi.com/Home | archive: https://web.archive.org/web/20260809194247/https://damekigurumi.com/Home
site animegao references 3 : https://damekigurumi.com/Blog/What-Happened-in-2021 | archive: https://web.archive.org/web/20260809195401/https://damekigurumi.com/Blog/What-Happened-in-2021
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://damekigurumi.com/ | archive: https://web.archive.org/web/20260809194235/https://damekigurumi.com/
site kigurumi references 2 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 3 : https://damekigurumi.com/Register | archive: https://web.archive.org/web/*/https://damekigurumi.com/Register
site kigurumi references 4 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 5 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 6 : https://damekigurumi.com/Cart | archive: https://web.archive.org/web/*/https://damekigurumi.com/Cart
site kigurumi references 7 : https://damekigurumi.com/Cart | archive: https://web.archive.org/web/*/https://damekigurumi.com/Cart
site kigurumi references 8 : https://damekigurumi.com/Home | archive: https://web.archive.org/web/20260809194247/https://damekigurumi.com/Home
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
site kigurumi references 42 : https://damekigurumi.com/Masks/Gen-3/M013-Anna-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/M013-Anna-Gen-3-Mask
site kigurumi references 43 : https://damekigurumi.com/Masks/Gen-3/M012-Alice-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/M012-Alice-Gen-3-Mask
site kigurumi references 44 : https://damekigurumi.com/Masks/Gen-3/M011-Ami-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/M011-Ami-Gen-3-Mask
site kigurumi references 45 : https://damekigurumi.com/Masks | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks
site kigurumi references 46 : https://damekigurumi.com/Masks/Gen-3/A003-Gen-3-Backplate | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/A003-Gen-3-Backplate
site kigurumi references 47 : https://damekigurumi.com/Skinsuits | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits
site kigurumi references 48 : https://damekigurumi.com/Blog | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog
site kigurumi references 49 : https://damekigurumi.com/M001-Anna-Gen-2-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/M001-Anna-Gen-2-Mask
site kigurumi references 50 : https://damekigurumi.com/M011-Ami-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/M011-Ami-Gen-3-Mask
site kigurumi references 51 : https://damekigurumi.com/A003-Gen-3-Backplate | archive: https://web.archive.org/web/*/https://damekigurumi.com/A003-Gen-3-Backplate
site kigurumi references 52 : https://damekigurumi.com/H011-Skinsuit | archive: https://web.archive.org/web/*/https://damekigurumi.com/H011-Skinsuit
site kigurumi references 53 : https://damekigurumi.com/P001-Fabric-Covered-Custom-Hip-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/P001-Fabric-Covered-Custom-Hip-Pads
site kigurumi references 54 : https://damekigurumi.com/M012-Alice-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/M012-Alice-Gen-3-Mask
site kigurumi references 55 : https://damekigurumi.com/About-Us | archive: https://web.archive.org/web/*/https://damekigurumi.com/About-Us
site kigurumi references 56 : https://damekigurumi.com/Shipping | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shipping
site kigurumi references 57 : https://damekigurumi.com/Privacy | archive: https://web.archive.org/web/*/https://damekigurumi.com/Privacy
site kigurumi references 58 : https://damekigurumi.com/Terms | archive: https://web.archive.org/web/*/https://damekigurumi.com/Terms
site kigurumi references 59 : https://damekigurumi.com/Definitions | archive: https://web.archive.org/web/*/https://damekigurumi.com/Definitions
site kigurumi references 60 : https://damekigurumi.com/Return | archive: https://web.archive.org/web/*/https://damekigurumi.com/Return
site kigurumi references 61 : https://damekigurumi.com/Site-Map | archive: https://web.archive.org/web/*/https://damekigurumi.com/Site-Map
site kigurumi references 62 : https://damekigurumi.com/Brand | archive: https://web.archive.org/web/*/https://damekigurumi.com/Brand
site kigurumi references 63 : https://damekigurumi.com/Voucher | archive: https://web.archive.org/web/*/https://damekigurumi.com/Voucher
site kigurumi references 64 : https://damekigurumi.com/Special-Offers | archive: https://web.archive.org/web/*/https://damekigurumi.com/Special-Offers
site kigurumi references 65 : https://damekigurumi.com/People | archive: https://web.archive.org/web/*/https://damekigurumi.com/People
site kigurumi references 66 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 67 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 68 : https://damekigurumi.com/Reset-Password | archive: https://web.archive.org/web/*/https://damekigurumi.com/Reset-Password
site kigurumi references 69 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 70 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 71 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 72 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 73 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 74 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 75 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 76 : https://damekigurumi.com/Compare | archive: https://web.archive.org/web/*/https://damekigurumi.com/Compare
site kigurumi references 77 : https://damekigurumi.com/Masks/M012-Alice-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/M012-Alice-Gen-3-Mask
site kigurumi references 78 : https://damekigurumi.com/Masks/M011-Ami-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/M011-Ami-Gen-3-Mask
site kigurumi references 79 : https://damekigurumi.com/Masks/M013-Anna-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/M013-Anna-Gen-3-Mask
site kigurumi references 80 : https://damekigurumi.com/Masks/M001-Anna-Gen-2-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/M001-Anna-Gen-2-Mask
site kigurumi references 81 : https://damekigurumi.com/Masks/A003-Gen-3-Backplate | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/A003-Gen-3-Backplate
site kigurumi references 82 : https://damekigurumi.com/Masks/A001-Gen-2-Backplate | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/A001-Gen-2-Backplate
site kigurumi references 83 : https://damekigurumi.com/Masks/Gen-3/M012-Alice-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/M012-Alice-Gen-3-Mask
site kigurumi references 84 : https://damekigurumi.com/Masks/Gen-3/M011-Ami-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/M011-Ami-Gen-3-Mask
site kigurumi references 85 : https://damekigurumi.com/Masks/Gen-3/M013-Anna-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/M013-Anna-Gen-3-Mask
site kigurumi references 86 : https://damekigurumi.com/Masks/Gen-3/A003-Gen-3-Backplate | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/A003-Gen-3-Backplate
site kigurumi references 87 : https://damekigurumi.com/Masks/Gen-2/M001-Anna-Gen-2-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-2/M001-Anna-Gen-2-Mask
site kigurumi references 88 : https://damekigurumi.com/Masks/Gen-2/A001-Gen-2-Backplate | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-2/A001-Gen-2-Backplate
site kigurumi references 89 : https://damekigurumi.com/Components/S002-Alice-Gen-3-Shell | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/S002-Alice-Gen-3-Shell
site kigurumi references 90 : https://damekigurumi.com/Components/S001-Ami-Gen-3-Shell | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/S001-Ami-Gen-3-Shell
site kigurumi references 91 : https://damekigurumi.com/Components/S003-Anna-Gen-3-Shell | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/S003-Anna-Gen-3-Shell
site kigurumi references 92 : https://damekigurumi.com/Components/E002-Standard-Alice-Eye-Inserts | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/E002-Standard-Alice-Eye-Inserts
site kigurumi references 93 : https://damekigurumi.com/Components/E001-Standard-Ami-Eye-Inserts | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/E001-Standard-Ami-Eye-Inserts
site kigurumi references 94 : https://damekigurumi.com/Components/E003-Standard-Anna-Eye-Inserts | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/E003-Standard-Anna-Eye-Inserts
site kigurumi references 95 : https://damekigurumi.com/Components/W202-Styled-Wig | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/W202-Styled-Wig
site kigurumi references 96 : https://damekigurumi.com/Components/W201-Unstyled-Wig | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/W201-Unstyled-Wig
site kigurumi references 97 : https://damekigurumi.com/Components/A002-Padding-Set | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/A002-Padding-Set
site kigurumi references 98 : https://damekigurumi.com/Components/A003-Gen-3-Backplate | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/A003-Gen-3-Backplate
site kigurumi references 99 : https://damekigurumi.com/Components/Shells/S002-Alice-Gen-3-Shell | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Shells/S002-Alice-Gen-3-Shell
site kigurumi references 100 : https://damekigurumi.com/Components/Shells/S001-Ami-Gen-3-Shell | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Shells/S001-Ami-Gen-3-Shell
site kigurumi references 101 : https://damekigurumi.com/Components/Shells/S003-Anna-Gen-3-Shell | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Shells/S003-Anna-Gen-3-Shell
site kigurumi references 102 : https://damekigurumi.com/Components/Shells/A002-Padding-Set | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Shells/A002-Padding-Set
site kigurumi references 103 : https://damekigurumi.com/Components/Shells/A003-Gen-3-Backplate | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Shells/A003-Gen-3-Backplate
site kigurumi references 104 : https://damekigurumi.com/Components/Eyes/E002-Standard-Alice-Eye-Inserts | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Eyes/E002-Standard-Alice-Eye-Inserts
site kigurumi references 105 : https://damekigurumi.com/Components/Eyes/E001-Standard-Ami-Eye-Inserts | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Eyes/E001-Standard-Ami-Eye-Inserts
site kigurumi references 106 : https://damekigurumi.com/Components/Eyes/E003-Standard-Anna-Eye-Inserts | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Eyes/E003-Standard-Anna-Eye-Inserts
site kigurumi references 107 : https://damekigurumi.com/Components/Wigs/W202-Styled-Wig | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Wigs/W202-Styled-Wig
site kigurumi references 108 : https://damekigurumi.com/Components/Wigs/W201-Unstyled-Wig | archive: https://web.archive.org/web/*/https://damekigurumi.com/Components/Wigs/W201-Unstyled-Wig
site kigurumi references 109 : https://damekigurumi.com/Accessories/A101-Witch-Hat | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/A101-Witch-Hat
site kigurumi references 110 : https://damekigurumi.com/Accessories/A102-Mini-Witch-Hat | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/A102-Mini-Witch-Hat
site kigurumi references 111 : https://damekigurumi.com/Accessories/A103-Santa-Hat | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/A103-Santa-Hat
site kigurumi references 112 : https://damekigurumi.com/Accessories/W001-Clip-On-Ponytail | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/W001-Clip-On-Ponytail
site kigurumi references 113 : https://damekigurumi.com/Accessories/W101-Wig-Brush | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/W101-Wig-Brush
site kigurumi references 114 : https://damekigurumi.com/Accessories/Hair/W001-Clip-On-Ponytail | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/Hair/W001-Clip-On-Ponytail
site kigurumi references 115 : https://damekigurumi.com/Accessories/Hair/W101-Wig-Brush | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/Hair/W101-Wig-Brush
site kigurumi references 116 : https://damekigurumi.com/Accessories/Hats/A101-Witch-Hat | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/Hats/A101-Witch-Hat
site kigurumi references 117 : https://damekigurumi.com/Accessories/Hats/A102-Mini-Witch-Hat | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/Hats/A102-Mini-Witch-Hat
site kigurumi references 118 : https://damekigurumi.com/Accessories/Hats/A103-Santa-Hat | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/Hats/A103-Santa-Hat
site kigurumi references 119 : https://damekigurumi.com/Skinsuits/H999-Fabric-Sample | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/H999-Fabric-Sample
site kigurumi references 120 : https://damekigurumi.com/Skinsuits/H011-Skinsuit | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/H011-Skinsuit
site kigurumi references 121 : https://damekigurumi.com/Skinsuits/H001-Skinsuit | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/H001-Skinsuit
site kigurumi references 122 : https://damekigurumi.com/Skinsuits/H012-Skinsuit-Gloves | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/H012-Skinsuit-Gloves
site kigurumi references 123 : https://damekigurumi.com/Skinsuits/H002-Skinsuit-Gloves | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/H002-Skinsuit-Gloves
site kigurumi references 124 : https://damekigurumi.com/Skinsuits/H013-Skinsuit-Hood | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/H013-Skinsuit-Hood
site kigurumi references 125 : https://damekigurumi.com/Skinsuits/H003-Skinsuit-Hood | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/H003-Skinsuit-Hood
site kigurumi references 126 : https://damekigurumi.com/Skinsuits/H042-Wash-Bag | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/H042-Wash-Bag
site kigurumi references 127 : https://damekigurumi.com/Skinsuits/Suits/H011-Skinsuit | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Suits/H011-Skinsuit
site kigurumi references 128 : https://damekigurumi.com/Skinsuits/Suits/H001-Skinsuit | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Suits/H001-Skinsuit
site kigurumi references 129 : https://damekigurumi.com/Skinsuits/Samples/H999-Fabric-Sample | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Samples/H999-Fabric-Sample
site kigurumi references 130 : https://damekigurumi.com/Skinsuits/Extras/H012-Skinsuit-Gloves | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Extras/H012-Skinsuit-Gloves
site kigurumi references 131 : https://damekigurumi.com/Skinsuits/Extras/H002-Skinsuit-Gloves | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Extras/H002-Skinsuit-Gloves
site kigurumi references 132 : https://damekigurumi.com/Skinsuits/Extras/H013-Skinsuit-Hood | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Extras/H013-Skinsuit-Hood
site kigurumi references 133 : https://damekigurumi.com/Skinsuits/Extras/H003-Skinsuit-Hood | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Extras/H003-Skinsuit-Hood
site kigurumi references 134 : https://damekigurumi.com/Skinsuits/Extras/H042-Wash-Bag | archive: https://web.archive.org/web/*/https://damekigurumi.com/Skinsuits/Extras/H042-Wash-Bag
site kigurumi references 135 : https://damekigurumi.com/Shapeware/P004-Butt-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/P004-Butt-Pads
site kigurumi references 136 : https://damekigurumi.com/Shapeware/B012-Breast-Forms | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/B012-Breast-Forms
site kigurumi references 137 : https://damekigurumi.com/Shapeware/P003-Hip-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/P003-Hip-Pads
site kigurumi references 138 : https://damekigurumi.com/Shapeware/P002-Custom-Hip-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/P002-Custom-Hip-Pads
site kigurumi references 139 : https://damekigurumi.com/Shapeware/P001-Fabric-Covered-Custom-Hip-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/P001-Fabric-Covered-Custom-Hip-Pads
site kigurumi references 140 : https://damekigurumi.com/Shapeware/Breast-Forms/B012-Breast-Forms | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/Breast-Forms/B012-Breast-Forms
site kigurumi references 141 : https://damekigurumi.com/Shapeware/Hip-Padding/P004-Butt-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/Hip-Padding/P004-Butt-Pads
site kigurumi references 142 : https://damekigurumi.com/Shapeware/Hip-Padding/P003-Hip-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/Hip-Padding/P003-Hip-Pads
site kigurumi references 143 : https://damekigurumi.com/Shapeware/Hip-Padding/P002-Custom-Hip-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/Hip-Padding/P002-Custom-Hip-Pads
site kigurumi references 144 : https://damekigurumi.com/Shapeware/Hip-Padding/P001-Fabric-Covered-Custom-Hip-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/Shapeware/Hip-Padding/P001-Fabric-Covered-Custom-Hip-Pads
site kigurumi references 145 : https://damekigurumi.com/ReadyToShip/C106-Alex-Blonde-Hair-Premade | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/C106-Alex-Blonde-Hair-Premade
site kigurumi references 146 : https://damekigurumi.com/ReadyToShip/C108-Ami-Lilac-Rose-Pink-Pre-Made-Wig | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/C108-Ami-Lilac-Rose-Pink-Pre-Made-Wig
site kigurumi references 147 : https://damekigurumi.com/ReadyToShip/M109-Grell-Sutcliff | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/M109-Grell-Sutcliff
site kigurumi references 148 : https://damekigurumi.com/ReadyToShip/Ready-Masks/C106-Alex-Blonde-Hair-Premade | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/Ready-Masks/C106-Alex-Blonde-Hair-Premade
site kigurumi references 149 : https://damekigurumi.com/ReadyToShip/Ready-Masks/M109-Grell-Sutcliff | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/Ready-Masks/M109-Grell-Sutcliff
site kigurumi references 150 : https://damekigurumi.com/ReadyToShip/Ready-Components/C108-Ami-Lilac-Rose-Pink-Pre-Made-Wig | archive: https://web.archive.org/web/*/https://damekigurumi.com/ReadyToShip/Ready-Components/C108-Ami-Lilac-Rose-Pink-Pre-Made-Wig
site kigurumi references 151 : https://damekigurumi.com/Blog/2021 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/2021
site kigurumi references 152 : https://damekigurumi.com/Blog/2022 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/2022
site kigurumi references 153 : https://damekigurumi.com/Blog/2023 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/2023
site kigurumi references 154 : https://damekigurumi.com/Blog/2024 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/2024
site kigurumi references 155 : https://damekigurumi.com/Blog/2025 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/2025
site kigurumi references 156 : https://damekigurumi.com/Blog/2026 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/2026
site kigurumi references 157 : https://damekigurumi.com/Blog/Dame | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Dame
site kigurumi references 158 : https://damekigurumi.com/Blog/Goals | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Goals
site kigurumi references 159 : https://damekigurumi.com/Blog/Website | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Website
site kigurumi references 160 : https://damekigurumi.com/Blog/Guides/Changing-A-Wig-on-A-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guides/Changing-A-Wig-on-A-Gen-3-Mask
site kigurumi references 161 : https://damekigurumi.com/People-Charlotte | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Charlotte
site kigurumi references 162 : https://damekigurumi.com/People-Lillian | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Lillian
site kigurumi references 163 : https://damekigurumi.com/People-Emily | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Emily
site kigurumi references 164 : https://damekigurumi.com/People-Convoluted | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Convoluted
site kigurumi references 165 : https://damekigurumi.com/People-Jean | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Jean
site kigurumi references 166 : https://damekigurumi.com/Sakuya-Izayoi-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Sakuya-Izayoi-Shoot
site kigurumi references 167 : https://damekigurumi.com/Twins-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Twins-Shoot
site kigurumi references 168 : https://damekigurumi.com/Album-Alice-Preview | archive: https://web.archive.org/web/*/https://damekigurumi.com/Album-Alice-Preview
site kigurumi references 169 : https://damekigurumi.com/Emilia-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Emilia-Shoot
site kigurumi references 170 : https://damekigurumi.com/Nekopara-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Nekopara-Shoot
site kigurumi references 171 : https://damekigurumi.com/Black-Butler-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Black-Butler-Shoot
site kigurumi references 172 : https://damekigurumi.com/Muffet-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Muffet-Shoot
site kigurumi references 173 : https://damekigurumi.com/Xelphie-Solid-Hair-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Xelphie-Solid-Hair-Shoot
site kigurumi references 174 : https://damekigurumi.com/Album-Anna-Happy-Elf | archive: https://web.archive.org/web/*/https://damekigurumi.com/Album-Anna-Happy-Elf
site kigurumi references 175 : https://damekigurumi.com/Plum-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Plum-Shoot
site kigurumi references 176 : https://damekigurumi.com/Copper-Elf-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Copper-Elf-Shoot
site kigurumi references 177 : https://damekigurumi.com/Black-Witch-and-Slushie-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Black-Witch-and-Slushie-Shoot
site kigurumi references 178 : https://damekigurumi.com/Fire-Kin-and-Ice-Elf-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Fire-Kin-and-Ice-Elf-Shoot
site kigurumi references 179 : https://damekigurumi.com/Caramel-and-Darkest-Purple-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Caramel-and-Darkest-Purple-Shoot
site kigurumi references 180 : https://damekigurumi.com/Succubus-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Succubus-Shoot
site kigurumi references 181 : https://damekigurumi.com/Gallery?page=2 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Gallery?page=2
site kigurumi references 182 : https://damekigurumi.com/Blog/Changing-A-Wig-on-A-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Changing-A-Wig-on-A-Gen-3-Mask
site kigurumi references 183 : https://damekigurumi.com/Blog/2026-Plans-and-Changes | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/2026-Plans-and-Changes
site kigurumi references 184 : https://damekigurumi.com/Blog/Tariffs-and-Country-Of-Origin | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Tariffs-and-Country-Of-Origin
site kigurumi references 185 : https://damekigurumi.com/Blog/Plaster-and-Plaits | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Plaster-and-Plaits
site kigurumi references 186 : https://damekigurumi.com/Blog/Mask-Padding-Guide | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Mask-Padding-Guide
site kigurumi references 187 : https://damekigurumi.com/Blog/Modernisation-Part-4 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Modernisation-Part-4
site kigurumi references 188 : https://damekigurumi.com/Blog/Gen-3-Launch-FAQ | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Gen-3-Launch-FAQ
site kigurumi references 189 : https://damekigurumi.com/Blog/What-Happened-in-2023 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/What-Happened-in-2023
site kigurumi references 190 : https://damekigurumi.com/Blog/Modernisation-Part-3 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Modernisation-Part-3
site kigurumi references 191 : https://damekigurumi.com/Blog/Shipping-Fees-Explained | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Shipping-Fees-Explained
site kigurumi references 192 : https://damekigurumi.com/Blog/Modernisation-Part-2 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Modernisation-Part-2
site kigurumi references 193 : https://damekigurumi.com/Blog/Modernisation-Part-1 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Modernisation-Part-1
site kigurumi references 194 : https://damekigurumi.com/Blog/What-to-Expect-in-2023 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/What-to-Expect-in-2023
site kigurumi references 195 : https://damekigurumi.com/Blog/2022-Wrap-Up | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/2022-Wrap-Up
site kigurumi references 196 : https://damekigurumi.com/Blog/Wig-Colours | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Wig-Colours
site kigurumi references 197 : https://damekigurumi.com/Blog?page=2 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog?page=2
site kigurumi references 198 : https://damekigurumi.com/Masks/Gen-3/A002-Padding-Set | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/A002-Padding-Set
site kigurumi references 199 : https://damekigurumi.com/Masks/Gen-3/Blog/Colours | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/Blog/Colours
site kigurumi references 200 : https://damekigurumi.com/Masks/Gen-3/Blog/Wig-Colours | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/Blog/Wig-Colours
site kigurumi references 201 : https://damekigurumi.com/Blog/Colours | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Colours
site kigurumi references 202 : https://damekigurumi.com/Blog/Wig-Colours | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Wig-Colours
site kigurumi references 203 : https://damekigurumi.com/A001-Gen-2-Backplate | archive: https://web.archive.org/web/*/https://damekigurumi.com/A001-Gen-2-Backplate
site kigurumi references 204 : https://damekigurumi.com/C106-Alex-Blonde-Hair-Premade | archive: https://web.archive.org/web/*/https://damekigurumi.com/C106-Alex-Blonde-Hair-Premade
site kigurumi references 205 : https://damekigurumi.com/S002-Alice-Gen-3-Shell | archive: https://web.archive.org/web/*/https://damekigurumi.com/S002-Alice-Gen-3-Shell
site kigurumi references 206 : https://damekigurumi.com/S001-Ami-Gen-3-Shell | archive: https://web.archive.org/web/*/https://damekigurumi.com/S001-Ami-Gen-3-Shell
site kigurumi references 207 : https://damekigurumi.com/C108-Ami-Lilac-Rose-Pink-Pre-Made-Wig | archive: https://web.archive.org/web/*/https://damekigurumi.com/C108-Ami-Lilac-Rose-Pink-Pre-Made-Wig
site kigurumi references 208 : https://damekigurumi.com/S003-Anna-Gen-3-Shell | archive: https://web.archive.org/web/*/https://damekigurumi.com/S003-Anna-Gen-3-Shell
site kigurumi references 209 : https://damekigurumi.com/P004-Butt-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/P004-Butt-Pads
site kigurumi references 210 : https://damekigurumi.com/W001-Clip-On-Ponytail | archive: https://web.archive.org/web/*/https://damekigurumi.com/W001-Clip-On-Ponytail
site kigurumi references 211 : https://damekigurumi.com/M109-Grell-Sutcliff | archive: https://web.archive.org/web/*/https://damekigurumi.com/M109-Grell-Sutcliff
site kigurumi references 212 : https://damekigurumi.com/P003-Hip-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/P003-Hip-Pads
site kigurumi references 213 : https://damekigurumi.com/H001-Skinsuit | archive: https://web.archive.org/web/*/https://damekigurumi.com/H001-Skinsuit
site kigurumi references 214 : https://damekigurumi.com/H012-Skinsuit-Gloves | archive: https://web.archive.org/web/*/https://damekigurumi.com/H012-Skinsuit-Gloves
site kigurumi references 215 : https://damekigurumi.com/H002-Skinsuit-Gloves | archive: https://web.archive.org/web/*/https://damekigurumi.com/H002-Skinsuit-Gloves
site kigurumi references 216 : https://damekigurumi.com/H013-Skinsuit-Hood | archive: https://web.archive.org/web/*/https://damekigurumi.com/H013-Skinsuit-Hood
site kigurumi references 217 : https://damekigurumi.com/H003-Skinsuit-Hood | archive: https://web.archive.org/web/*/https://damekigurumi.com/H003-Skinsuit-Hood
site kigurumi references 218 : https://damekigurumi.com/E002-Standard-Alice-Eye-Inserts | archive: https://web.archive.org/web/*/https://damekigurumi.com/E002-Standard-Alice-Eye-Inserts
site kigurumi references 219 : https://damekigurumi.com/E001-Standard-Ami-Eye-Inserts | archive: https://web.archive.org/web/*/https://damekigurumi.com/E001-Standard-Ami-Eye-Inserts
site kigurumi references 220 : https://damekigurumi.com/E003-Standard-Anna-Eye-Inserts | archive: https://web.archive.org/web/*/https://damekigurumi.com/E003-Standard-Anna-Eye-Inserts
site kigurumi references 221 : https://damekigurumi.com/A002-Padding-Set | archive: https://web.archive.org/web/*/https://damekigurumi.com/A002-Padding-Set
site kigurumi references 222 : https://damekigurumi.com/W202-Styled-Wig | archive: https://web.archive.org/web/*/https://damekigurumi.com/W202-Styled-Wig
site kigurumi references 223 : https://damekigurumi.com/B012-Breast-Forms | archive: https://web.archive.org/web/*/https://damekigurumi.com/B012-Breast-Forms
site kigurumi references 224 : https://damekigurumi.com/W201-Unstyled-Wig | archive: https://web.archive.org/web/*/https://damekigurumi.com/W201-Unstyled-Wig
site kigurumi references 225 : https://damekigurumi.com/H042-Wash-Bag | archive: https://web.archive.org/web/*/https://damekigurumi.com/H042-Wash-Bag
site kigurumi references 226 : https://damekigurumi.com/W101-Wig-Brush | archive: https://web.archive.org/web/*/https://damekigurumi.com/W101-Wig-Brush
site kigurumi references 227 : https://damekigurumi.com/Dame | archive: https://web.archive.org/web/*/https://damekigurumi.com/Dame
site kigurumi references 228 : https://damekigurumi.com/A101-Witch-Hat | archive: https://web.archive.org/web/*/https://damekigurumi.com/A101-Witch-Hat
site kigurumi references 229 : https://damekigurumi.com/A102-Mini-Witch-Hat | archive: https://web.archive.org/web/*/https://damekigurumi.com/A102-Mini-Witch-Hat
site kigurumi references 230 : https://damekigurumi.com/A103-Santa-Hat | archive: https://web.archive.org/web/*/https://damekigurumi.com/A103-Santa-Hat
site kigurumi references 231 : https://damekigurumi.com/M013-Anna-Gen-3-Mask | archive: https://web.archive.org/web/*/https://damekigurumi.com/M013-Anna-Gen-3-Mask
site kigurumi references 232 : https://damekigurumi.com/Masks/Gen-3/Blog/Backplate-Attachment-Guide | archive: https://web.archive.org/web/*/https://damekigurumi.com/Masks/Gen-3/Blog/Backplate-Attachment-Guide
site kigurumi references 233 : https://damekigurumi.com/Blog/Gen-3-Launch-FAQ | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Gen-3-Launch-FAQ
site kigurumi references 234 : https://damekigurumi.com/A002-Padding-Set | archive: https://web.archive.org/web/*/https://damekigurumi.com/A002-Padding-Set
site kigurumi references 235 : https://damekigurumi.com/H999-Fabric-Sample | archive: https://web.archive.org/web/*/https://damekigurumi.com/H999-Fabric-Sample
site kigurumi references 236 : https://damekigurumi.com/Accessories/W001-Clip-On-Ponytail | archive: https://web.archive.org/web/*/https://damekigurumi.com/Accessories/W001-Clip-On-Ponytail
site kigurumi references 237 : https://damekigurumi.com/Blog/Backplate-Attachment-Guide | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Backplate-Attachment-Guide
site kigurumi references 238 : https://damekigurumi.com/Cantillon | archive: https://web.archive.org/web/*/https://damekigurumi.com/Cantillon
site kigurumi references 239 : https://damekigurumi.com/H999-Fabric-Sample | archive: https://web.archive.org/web/*/https://damekigurumi.com/H999-Fabric-Sample
site kigurumi references 240 : https://damekigurumi.com/P002-Custom-Hip-Pads | archive: https://web.archive.org/web/*/https://damekigurumi.com/P002-Custom-Hip-Pads
site kigurumi references 241 : https://damekigurumi.com/Alpeia | archive: https://web.archive.org/web/*/https://damekigurumi.com/Alpeia
site kigurumi references 242 : https://damekigurumi.com/Blog/Shipping-Fees-Explained | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Shipping-Fees-Explained
site kigurumi references 243 : https://damekigurumi.com/Terms-2017 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Terms-2017
site kigurumi references 244 : https://damekigurumi.com/Terms-2020 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Terms-2020
site kigurumi references 245 : https://damekigurumi.com/Terms-2024 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Terms-2024
site kigurumi references 246 : https://damekigurumi.com/Contact-Us | archive: https://web.archive.org/web/*/https://damekigurumi.com/Contact-Us
site kigurumi references 247 : https://damekigurumi.com/Alice-Gen-3-Launch-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Alice-Gen-3-Launch-Shoot
site kigurumi references 248 : https://damekigurumi.com/Alice-Launch-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Alice-Launch-Shoot
site kigurumi references 249 : https://damekigurumi.com/Alice-Party-Dress-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Alice-Party-Dress-Shoot
site kigurumi references 250 : https://damekigurumi.com/Ami-Gen-3-Launch-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Ami-Gen-3-Launch-Shoot
site kigurumi references 251 : https://damekigurumi.com/Android-Doll-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Android-Doll-Shoot
site kigurumi references 252 : https://damekigurumi.com/Anna-School-Girl-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Anna-School-Girl-Shoot
site kigurumi references 253 : https://damekigurumi.com/Forest-Elf-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Forest-Elf-Shoot
site kigurumi references 254 : https://damekigurumi.com/Pink-Purple-Anna-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Pink-Purple-Anna-Shoot
site kigurumi references 255 : https://damekigurumi.com/Retro-Gamer-Girl-Shoot | archive: https://web.archive.org/web/*/https://damekigurumi.com/Retro-Gamer-Girl-Shoot
site kigurumi references 256 : https://damekigurumi.com/People-Amity-DeWolf | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Amity-DeWolf
site kigurumi references 257 : https://damekigurumi.com/People-Grimm | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Grimm
site kigurumi references 258 : https://damekigurumi.com/People-Hikari | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Hikari
site kigurumi references 259 : https://damekigurumi.com/People-Iz | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Iz
site kigurumi references 260 : https://damekigurumi.com/People-Kurikan | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Kurikan
site kigurumi references 261 : https://damekigurumi.com/People-Xelphie | archive: https://web.archive.org/web/*/https://damekigurumi.com/People-Xelphie
site kigurumi references 262 : https://damekigurumi.com/Blog/Guide-Skinsuit-Maintenance | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guide-Skinsuit-Maintenance
site kigurumi references 263 : https://damekigurumi.com/Blog/Guide-Wig-Tutorial | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guide-Wig-Tutorial
site kigurumi references 264 : https://damekigurumi.com/Blog/Global-Challenges | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Global-Challenges
site kigurumi references 265 : https://damekigurumi.com/Blog/Guide-Mask-Care | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Guide-Mask-Care
site kigurumi references 266 : https://damekigurumi.com/Blog/Why-Make-a-Blog | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Why-Make-a-Blog
site kigurumi references 267 : https://damekigurumi.com/Blog/What-Happened-in-2021 | archive: https://web.archive.org/web/20260809195401/https://damekigurumi.com/Blog/What-Happened-in-2021
site kigurumi references 268 : https://damekigurumi.com/Blog/Backplate-Attachment-Guide | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Backplate-Attachment-Guide
site kigurumi references 269 : https://damekigurumi.com/Blog/Direction-of-Dame | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Direction-of-Dame
site kigurumi references 270 : https://damekigurumi.com/Blog/Colours | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Colours
site kigurumi references 271 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 272 : https://damekigurumi.com/Login | archive: https://web.archive.org/web/*/https://damekigurumi.com/Login
site kigurumi references 273 : https://damekigurumi.com/Search | archive: https://web.archive.org/web/*/https://damekigurumi.com/Search
site kigurumi references 274 : https://damekigurumi.com/Blog/Global-Challenges | archive: https://web.archive.org/web/*/https://damekigurumi.com/Blog/Global-Challenges
site kigurumi references 275 : https://damekigurumi.com/Terms-2017 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Terms-2017
site kigurumi references 276 : https://damekigurumi.com/Terms-2020 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Terms-2020
site kigurumi references 277 : https://damekigurumi.com/Terms-2024 | archive: https://web.archive.org/web/*/https://damekigurumi.com/Terms-2024
site kigurumi references 278 : https://damekigurumi.com/index.php?route=product/manufacturer | archive: https://web.archive.org/web/*/https://damekigurumi.com/index.php?route=product/manufacturer
site kigurumi references 279 : https://damekigurumi.com/External | archive: https://web.archive.org/web/*/https://damekigurumi.com/External
site kigurumi references 280 : https://damekigurumi.com/Forever-Young | archive: https://web.archive.org/web/*/https://damekigurumi.com/Forever-Young
site kigurumi references 281 : https://damekigurumi.com/IVITA | archive: https://web.archive.org/web/*/https://damekigurumi.com/IVITA
site kigurumi references 282 : https://damekigurumi.com/Kigurumi-Menagerie | archive: https://web.archive.org/web/*/https://damekigurumi.com/Kigurumi-Menagerie
site kigurumi references 283 : https://damekigurumi.com/MWF | archive: https://web.archive.org/web/*/https://damekigurumi.com/MWF
site kigurumi references 284 : https://damekigurumi.com/Porkcube | archive: https://web.archive.org/web/*/https://damekigurumi.com/Porkcube
x.com kigurumi references (1): https://x.com/damekigurumi/status/2048811563121803521
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/damekigurumi
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Dora Studio
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (6): https://x.com/DoraKigStudio/status/1832364332275134834, https://x.com/DoraKigStudio/status/1830492360335343935, https://x.com/DoraKigStudio/status/1829733577380282593, https://x.com/DoraKigStudio/status/1825035976923865383, https://x.com/DoraKigStudio/status/1825035782358532210, https://x.com/DoraKigStudio/status/1825034722860474819
x.com kigurumi bio references (1): https://x.com/DoraKigStudio
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: ELYSIUM
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (5): https://x.com/ELYSIUM1688/status/2051563563614154835, https://x.com/ELYSIUM1688/status/1809809332026110187, https://x.com/ELYSIUM1688/status/1708371210109923442, https://x.com/ELYSIUM1688/status/1704392916347797975, https://x.com/ELYSIUM1688/status/1660097738120511490
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Ezo Fox Workshop
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/studioezofox
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/studioezofox

maker: Haka Renxing
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (17): https://x.com/hakarenxin99/status/1926910081343381629, https://x.com/hakarenxin99/status/1926661066206896396, https://x.com/hakarenxin99/status/1926221236952068320, https://x.com/hakarenxin99/status/1925887054384124148, https://x.com/hakarenxin99/status/1925506693255073890, https://x.com/hakarenxin99/status/1925200300257968347, https://x.com/hakarenxin99/status/1924103920961585378, https://x.com/hakarenxin99/status/1923015853588594735, https://x.com/hakarenxin99/status/1921938479350456702, https://x.com/hakarenxin99/status/1921142662754660422, https://x.com/hakarenxin99/status/1919016596124975380, https://x.com/hakarenxin99/status/1918647442553377209, https://x.com/hakarenxin99/status/1917561050679107786, https://x.com/hakarenxin99/status/1916084865185026543, https://x.com/hakarenxin99/status/1913400833263427865, https://x.com/hakarenxin99/status/1912144310860124318, https://x.com/hakarenxin99/status/1911756104243286115
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Harinezumi Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (9): https://x.com/harinezumiws/status/2085191390632476899, https://x.com/harinezumiws/status/2069432009857159337, https://x.com/harinezumiws/status/2067149718279582037, https://x.com/harinezumiws/status/2066542732433342794, https://x.com/harinezumiws/status/2029570354348441778, https://x.com/harinezumiws/status/2022829255265251543, https://x.com/harinezumiws/status/2021977130171818233, https://x.com/harinezumiws/status/2021541435678560365, https://x.com/harinezumiws/status/2021237327327109436
x.com kigurumi bio references (1): https://x.com/harinezumiws
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Huyaoshouzuo
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (1): https://x.com/Huyaoshouzuo/status/2013223958405890271
x.com kigurumi hashtag-only references (16): https://x.com/Huyaoshouzuo/status/2075101335553511501, https://x.com/Huyaoshouzuo/status/2075101088202858626, https://x.com/Huyaoshouzuo/status/2044595312518721795, https://x.com/Huyaoshouzuo/status/2044592754538479651, https://x.com/Huyaoshouzuo/status/2043494600611172465, https://x.com/Huyaoshouzuo/status/2043489059826541022, https://x.com/Huyaoshouzuo/status/2043487584563933673, https://x.com/Huyaoshouzuo/status/2043479710605377986, https://x.com/Huyaoshouzuo/status/2016736542191157266, https://x.com/Huyaoshouzuo/status/2015751970867548570, https://x.com/Huyaoshouzuo/status/2015453121842188406, https://x.com/Huyaoshouzuo/status/2013285347791089859, https://x.com/Huyaoshouzuo/status/2013274554878062716, https://x.com/Huyaoshouzuo/status/2009317518591316256, https://x.com/Huyaoshouzuo/status/2009316925684457733, https://x.com/Huyaoshouzuo/status/2009099543204577572
x.com kigurumi bio references (1): https://x.com/Huyaoshouzuo
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Iris Kigurumi
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (2): https://x.com/IrisKigurumi/status/1943634270523633985, https://x.com/IrisKigurumi/status/1863124940565959034
x.com kigurumi hashtag-only references (7): https://x.com/IrisKigurumi/status/1941052561378992509, https://x.com/IrisKigurumi/status/1928680330833043794, https://x.com/IrisKigurumi/status/1923229317334507949, https://x.com/IrisKigurumi/status/1921433694570512411, https://x.com/IrisKigurumi/status/1893862358247768515, https://x.com/IrisKigurumi/status/1891414173277405437, https://x.com/IrisKigurumi/status/1888818037618606326
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (2): https://x.com/IrisKigurumi/status/1928680330833043794, https://x.com/IrisKigurumi/status/1863124940565959034
x.com 着ぐるみ bio references: none (0)

maker: Justin Bailey
region: Canada
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
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
site kigurumi references 37 : http://justinbailey2430.blogspot.com/2015/06/three-cons-in-row.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/06/three-cons-in-row.html
site kigurumi references 38 : http://justinbailey2430.blogspot.com/2015/04/150421-mask-progress-updates.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/04/150421-mask-progress-updates.html
site kigurumi references 39 : http://justinbailey2430.blogspot.com/2015/01/hibiki-is-now-mostly-complete-several.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2015/01/hibiki-is-now-mostly-complete-several.html
site kigurumi references 40 : http://justinbailey2430.blogspot.com/search?updated-max=2015-01-12T00:51:00-08:00&max-results=7&start=3&by-date=false | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2015-01-12T00:51:00-08:00&max-results=7&start=3&by-date=false
site kigurumi references 41 : http://justinbailey2430.blogspot.com/search?updated-max=2018-08-23T03:20:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2018-08-23T03:20:00-07:00&max-results=7
site kigurumi references 42 : http://justinbailey2430.blogspot.com/search?updated-max=2015-11-03T16:56:00-08:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2015-11-03T16:56:00-08:00&max-results=7
site kigurumi references 43 : http://justinbailey2430.blogspot.com/search?updated-max=2015-06-01T20:24:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2015-06-01T20:24:00-07:00&max-results=7
site kigurumi references 44 : http://justinbailey2430.blogspot.com/search?updated-max=2015-04-21T02:19:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2015-04-21T02:19:00-07:00&max-results=7
site kigurumi references 45 : http://justinbailey2430.blogspot.com/search?updated-max=2015-01-12T00:51:00-08:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2015-01-12T00:51:00-08:00&max-results=7
site kigurumi references 46 : http://justinbailey2430.blogspot.com/2014/11/141104-mask-progress-updates.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/11/141104-mask-progress-updates.html
site kigurumi references 47 : http://justinbailey2430.blogspot.com/2014/11/141104-pictures-from-several.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/11/141104-pictures-from-several.html
site kigurumi references 48 : http://justinbailey2430.blogspot.com/search?updated-max=2018-08-23T03:20:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2018-08-23T03:20:00-07:00&max-results=7&reverse-paginate=true
site kigurumi references 49 : http://justinbailey2430.blogspot.com/search?updated-max=2014-11-04T01:05:00-08:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-11-04T01:05:00-08:00&max-results=7
site kigurumi references 50 : http://justinbailey2430.blogspot.com/2014/10/pictures-from-edmonton-expo-2014-mask.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/10/pictures-from-edmonton-expo-2014-mask.html
site kigurumi references 51 : http://justinbailey2430.blogspot.com/search?updated-max=2015-11-04T22:52:00-08:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2015-11-04T22:52:00-08:00&max-results=7&reverse-paginate=true
site kigurumi references 52 : http://justinbailey2430.blogspot.com/search?updated-max=2014-10-04T02:05:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-10-04T02:05:00-07:00&max-results=7
site kigurumi references 53 : http://justinbailey2430.blogspot.com/2014/09/140916-mask-progress-updates.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/09/140916-mask-progress-updates.html
site kigurumi references 54 : http://justinbailey2430.blogspot.com/search?updated-max=2015-11-03T16:56:00-08:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2015-11-03T16:56:00-08:00&max-results=7&reverse-paginate=true
site kigurumi references 55 : http://justinbailey2430.blogspot.com/search?updated-max=2014-09-16T15:48:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-09-16T15:48:00-07:00&max-results=7
site kigurumi references 56 : http://justinbailey2430.blogspot.com/2014/08/pictures-from-animethon-21-mask.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/08/pictures-from-animethon-21-mask.html
site kigurumi references 57 : http://justinbailey2430.blogspot.com/2014/08/140801-homura-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/08/140801-homura-update.html
site kigurumi references 58 : http://justinbailey2430.blogspot.com/search?updated-max=2015-10-16T23:36:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2015-10-16T23:36:00-07:00&max-results=7&reverse-paginate=true
site kigurumi references 59 : http://justinbailey2430.blogspot.com/search?updated-max=2014-08-01T03:28:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-08-01T03:28:00-07:00&max-results=7
site kigurumi references 60 : http://justinbailey2430.blogspot.com/2014/07/140730-homura-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/07/140730-homura-update.html
site kigurumi references 61 : http://justinbailey2430.blogspot.com/2014/07/started-printing-homura.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/07/started-printing-homura.html
site kigurumi references 62 : http://justinbailey2430.blogspot.com/2014/07/140613-sayakahibiki-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/07/140613-sayakahibiki-update.html
site kigurumi references 63 : http://justinbailey2430.blogspot.com/2014/07/140706-sayaka-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/07/140706-sayaka-update.html
site kigurumi references 64 : http://justinbailey2430.blogspot.com/2014/07/140703-sayaka-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/07/140703-sayaka-update.html
site kigurumi references 65 : http://justinbailey2430.blogspot.com/search?updated-max=2015-04-21T02:19:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2015-04-21T02:19:00-07:00&max-results=7&reverse-paginate=true
site kigurumi references 66 : http://justinbailey2430.blogspot.com/search?updated-max=2014-07-03T01:22:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-07-03T01:22:00-07:00&max-results=7
site kigurumi references 67 : http://justinbailey2430.blogspot.com/2014/06/140628-sayaka-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/06/140628-sayaka-update.html
site kigurumi references 68 : http://justinbailey2430.blogspot.com/2014/06/140623-sayakahibiki-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/06/140623-sayakahibiki-update.html
site kigurumi references 69 : http://justinbailey2430.blogspot.com/2014/06/pictures-from-edmonton-pride-festival.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/06/pictures-from-edmonton-pride-festival.html
site kigurumi references 70 : http://justinbailey2430.blogspot.com/search?updated-max=2014-09-16T15:48:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-09-16T15:48:00-07:00&max-results=7&reverse-paginate=true
site kigurumi references 71 : http://justinbailey2430.blogspot.com/search?updated-max=2014-06-13T02:06:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-06-13T02:06:00-07:00&max-results=7
site kigurumi references 72 : http://justinbailey2430.blogspot.com/2014/05/140530-mask-progress-updates.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/05/140530-mask-progress-updates.html
site kigurumi references 73 : http://justinbailey2430.blogspot.com/2014/05/pictures-from-otafest.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/05/pictures-from-otafest.html
site kigurumi references 74 : http://justinbailey2430.blogspot.com/search?updated-max=2014-07-30T18:22:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-07-30T18:22:00-07:00&max-results=7&reverse-paginate=true
site kigurumi references 75 : http://justinbailey2430.blogspot.com/search?updated-max=2014-05-30T00:29:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-05-30T00:29:00-07:00&max-results=7
site kigurumi references 76 : http://justinbailey2430.blogspot.com/2014/05/ichigo-finished.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/05/ichigo-finished.html
site kigurumi references 77 : http://justinbailey2430.blogspot.com/2014/05/mask-progress-updates-fur-eh-2014.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/05/mask-progress-updates-fur-eh-2014.html
site kigurumi references 78 : http://justinbailey2430.blogspot.com/2014/04/finished-reimi-started-segmenting.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/04/finished-reimi-started-segmenting.html
site kigurumi references 79 : http://justinbailey2430.blogspot.com/search?updated-max=2014-07-03T01:22:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-07-03T01:22:00-07:00&max-results=7&reverse-paginate=true
site kigurumi references 80 : http://justinbailey2430.blogspot.com/search?updated-max=2014-04-17T20:08:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-04-17T20:08:00-07:00&max-results=7
site kigurumi references 81 : http://justinbailey2430.blogspot.com/2014/03/140328-mask-progress-updates.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/03/140328-mask-progress-updates.html
site kigurumi references 82 : http://justinbailey2430.blogspot.com/2014/03/140316-mask-progress-updates.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/03/140316-mask-progress-updates.html
site kigurumi references 83 : http://justinbailey2430.blogspot.com/2014/03/140307-mask-progress-updates.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/03/140307-mask-progress-updates.html
site kigurumi references 84 : http://justinbailey2430.blogspot.com/search?updated-max=2014-06-28T22:43:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-06-28T22:43:00-07:00&max-results=7&reverse-paginate=true
site kigurumi references 85 : http://justinbailey2430.blogspot.com/search?updated-max=2014-03-07T01:36:00-08:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-03-07T01:36:00-08:00&max-results=7
site kigurumi references 86 : http://justinbailey2430.blogspot.com/2014/02/started-printing-reimi-ichigo-progress.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/02/started-printing-reimi-ichigo-progress.html
site kigurumi references 87 : http://justinbailey2430.blogspot.com/2014/02/mask-progress-updates-more-pictures.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/02/mask-progress-updates-more-pictures.html
site kigurumi references 88 : http://justinbailey2430.blogspot.com/2014/02/taste-of-animethon-2014.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/02/taste-of-animethon-2014.html
site kigurumi references 89 : http://justinbailey2430.blogspot.com/search?updated-max=2014-05-30T20:57:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-05-30T20:57:00-07:00&max-results=7&reverse-paginate=true
site kigurumi references 90 : http://justinbailey2430.blogspot.com/search?updated-max=2014-02-03T01:05:00-08:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-02-03T01:05:00-08:00&max-results=7
site kigurumi references 91 : http://justinbailey2430.blogspot.com/2014/01/new-version-of-erika-finished.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/01/new-version-of-erika-finished.html
site kigurumi references 92 : http://justinbailey2430.blogspot.com/2014/01/finished-assembling-erika.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/01/finished-assembling-erika.html
site kigurumi references 93 : http://justinbailey2430.blogspot.com/2014/01/finished-printing-erika.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/01/finished-printing-erika.html
site kigurumi references 94 : http://justinbailey2430.blogspot.com/2014/01/started-printing-third-version-of-erika.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/01/started-printing-third-version-of-erika.html
site kigurumi references 95 : http://justinbailey2430.blogspot.com/2014/01/130105-reimierika-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2014/01/130105-reimierika-update.html
site kigurumi references 96 : http://justinbailey2430.blogspot.com/search?updated-max=2014-05-04T17:33:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-05-04T17:33:00-07:00&max-results=7&reverse-paginate=true
site kigurumi references 97 : http://justinbailey2430.blogspot.com/search?updated-max=2014-01-05T21:51:00-08:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-01-05T21:51:00-08:00&max-results=7
site kigurumi references 98 : http://justinbailey2430.blogspot.com/2013/12/131229-reimierika-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/12/131229-reimierika-update.html
site kigurumi references 99 : http://justinbailey2430.blogspot.com/2013/12/started-on-third-version-of-erika.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/12/started-on-third-version-of-erika.html
site kigurumi references 100 : http://justinbailey2430.blogspot.com/2013/12/130913-reimi-custom-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/12/130913-reimi-custom-update.html
site kigurumi references 101 : http://justinbailey2430.blogspot.com/2013/12/131209-reimi-custom-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/12/131209-reimi-custom-update.html
site kigurumi references 102 : http://justinbailey2430.blogspot.com/2013/12/131205-reimi-custom-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/12/131205-reimi-custom-update.html
site kigurumi references 103 : http://justinbailey2430.blogspot.com/2013/12/131203-reimi-custom-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/12/131203-reimi-custom-update.html
site kigurumi references 104 : http://justinbailey2430.blogspot.com/2013/11/131130-reimi-custom-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/11/131130-reimi-custom-update.html
site kigurumi references 105 : http://justinbailey2430.blogspot.com/2013/11/131120-reimi-custom-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/11/131120-reimi-custom-update.html
site kigurumi references 106 : http://justinbailey2430.blogspot.com/search?updated-max=2014-02-27T21:23:00-08:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-02-27T21:23:00-08:00&max-results=7&reverse-paginate=true
site kigurumi references 107 : http://justinbailey2430.blogspot.com/search?updated-max=2013-11-20T22:03:00-08:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2013-11-20T22:03:00-08:00&max-results=7
site kigurumi references 108 : http://justinbailey2430.blogspot.com/search?updated-max=2013-12-02T23:24:00-08:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2013-12-02T23:24:00-08:00&max-results=7
site kigurumi references 109 : http://justinbailey2430.blogspot.com/2013/11/131101-reimi-custom-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/11/131101-reimi-custom-update.html
site kigurumi references 110 : http://justinbailey2430.blogspot.com/search?updated-max=2014-01-17T01:19:00-08:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2014-01-17T01:19:00-08:00&max-results=7&reverse-paginate=true
site kigurumi references 111 : http://justinbailey2430.blogspot.com/search?updated-max=2013-11-03T15:16:00-08:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2013-11-03T15:16:00-08:00&max-results=7
site kigurumi references 112 : http://justinbailey2430.blogspot.com/2013/10/131028-reimi-custom-mask-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/10/131028-reimi-custom-mask-update.html
site kigurumi references 113 : http://justinbailey2430.blogspot.com/2013/10/reimi-custom-progress.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/10/reimi-custom-progress.html
site kigurumi references 114 : http://justinbailey2430.blogspot.com/2013/10/131014-reimi-custom-mask-update.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/10/131014-reimi-custom-mask-update.html
site kigurumi references 115 : http://justinbailey2430.blogspot.com/2013/10/ive-now-started-on-youngs-reimi-custom.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/10/ive-now-started-on-youngs-reimi-custom.html
site kigurumi references 116 : http://justinbailey2430.blogspot.com/2013/10/version-21-of-erika-shell.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/10/version-21-of-erika-shell.html
site kigurumi references 117 : http://justinbailey2430.blogspot.com/2013/10/edmonton-comic-and-entertainment-expo.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/10/edmonton-comic-and-entertainment-expo.html
site kigurumi references 118 : http://justinbailey2430.blogspot.com/search?updated-max=2013-12-26T00:47:00-08:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2013-12-26T00:47:00-08:00&max-results=7&reverse-paginate=true
site kigurumi references 119 : http://justinbailey2430.blogspot.com/search?updated-max=2013-10-04T03:27:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2013-10-04T03:27:00-07:00&max-results=7
site kigurumi references 120 : http://justinbailey2430.blogspot.com/2013/09/reimi-saionji-full-custom-for.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/09/reimi-saionji-full-custom-for.html
site kigurumi references 121 : http://justinbailey2430.blogspot.com/2013/09/some-photos-from-previous-outings.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/09/some-photos-from-previous-outings.html
site kigurumi references 122 : http://justinbailey2430.blogspot.com/search?updated-max=2013-11-20T22:03:00-08:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2013-11-20T22:03:00-08:00&max-results=7&reverse-paginate=true
site kigurumi references 123 : http://justinbailey2430.blogspot.com/search?updated-max=2013-09-04T15:45:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2013-09-04T15:45:00-07:00&max-results=7
site kigurumi references 124 : http://justinbailey2430.blogspot.com/2013/08/130822-edmonton-international-fringe.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/08/130822-edmonton-international-fringe.html
site kigurumi references 125 : http://justinbailey2430.blogspot.com/search?updated-max=2013-10-28T02:42:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2013-10-28T02:42:00-07:00&max-results=7&reverse-paginate=true
site kigurumi references 126 : http://justinbailey2430.blogspot.com/search?updated-max=2013-08-28T16:51:00-07:00&max-results=7 | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2013-08-28T16:51:00-07:00&max-results=7
site kigurumi references 127 : http://justinbailey2430.blogspot.com/2013/08/pictures-from-animethon.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/08/pictures-from-animethon.html
site kigurumi references 128 : http://justinbailey2430.blogspot.com/2013/08/animethon-20-day-2.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/08/animethon-20-day-2.html
site kigurumi references 129 : http://justinbailey2430.blogspot.com/2013/08/animethon-20-day-1.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/08/animethon-20-day-1.html
site kigurumi references 130 : http://justinbailey2430.blogspot.com/2013/08/preparing-for-animethon.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/08/preparing-for-animethon.html
site kigurumi references 131 : http://justinbailey2430.blogspot.com/2013/08/commissions-now-open-new-version-of.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/08/commissions-now-open-new-version-of.html
site kigurumi references 132 : http://justinbailey2430.blogspot.com/2013/07/introduction.html | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/2013/07/introduction.html
site kigurumi references 133 : http://justinbailey2430.blogspot.com/search?updated-max=2013-09-20T18:05:00-07:00&max-results=7&reverse-paginate=true | archive: https://web.archive.org/web/*/http://justinbailey2430.blogspot.com/search?updated-max=2013-09-20T18:05:00-07:00&max-results=7&reverse-paginate=true
x.com kigurumi references (2): https://x.com/justinbailey243/status/2057725590531342340, https://x.com/justinbailey243/status/2057724442470711723
x.com kigurumi hashtag-only references (1): https://x.com/justinbailey243/status/2084155383388770712
x.com kigurumi bio references (1): https://x.com/justinbailey243
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Kagaribi Workshop
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (1): https://x.com/kagaribi_shop/status/2076622590710632637
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/kagaribi_shop

maker: KaikaSakura Art
region: USA
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (14): https://x.com/KaikaKigu/status/2080790578908876869, https://x.com/KaikaKigu/status/2080022369771442598, https://x.com/KaikaKigu/status/2078857771848548421, https://x.com/KaikaKigu/status/2077513804682818047, https://x.com/KaikaKigu/status/2076667713963938051, https://x.com/KaikaKigu/status/2074131856174268727, https://x.com/KaikaKigu/status/2071963941220106625, https://x.com/KaikaKigu/status/2069801686659375610, https://x.com/KaikaKigu/status/2068684645412069510, https://x.com/KaikaKigu/status/2066533785869435344, https://x.com/KaikaKigu/status/2064456108215787742, https://x.com/KaikaKigu/status/2062945592557384039, https://x.com/KaikaKigu/status/2061527226823086326, https://x.com/KaikaKigu/status/2060338090405732473
x.com kigurumi bio references (1): https://x.com/KaikaKigu
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (12): https://x.com/KaikaKigu/status/2080022369771442598, https://x.com/KaikaKigu/status/2078857771848548421, https://x.com/KaikaKigu/status/2077513804682818047, https://x.com/KaikaKigu/status/2076667713963938051, https://x.com/KaikaKigu/status/2074131856174268727, https://x.com/KaikaKigu/status/2071963941220106625, https://x.com/KaikaKigu/status/2068684645412069510, https://x.com/KaikaKigu/status/2066533785869435344, https://x.com/KaikaKigu/status/2064456108215787742, https://x.com/KaikaKigu/status/2062945592557384039, https://x.com/KaikaKigu/status/2061527226823086326, https://x.com/KaikaKigu/status/2060338090405732473
x.com 着ぐるみ bio references: none (0)

maker: KigCos
region: Australia & Singapore
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (13): https://x.com/wyukig/status/2085994299553186084, https://x.com/wyukig/status/2084245523658395860, https://x.com/wyukig/status/2082107571868213533, https://x.com/wyukig/status/2082099269218226677, https://x.com/wyukig/status/2082058623250047284, https://x.com/wyukig/status/2081364334257799534, https://x.com/wyukig/status/2081171257614323926, https://x.com/wyukig/status/2081014152714440990, https://x.com/wyukig/status/2080692672432636264, https://x.com/wyukig/status/2080668973981724866, https://x.com/wyukig/status/2080644822302658809, https://x.com/wyukig/status/2080616498151014838, https://x.com/wyukig/status/2080280030874095811
x.com kigurumi bio references (1): https://x.com/wyukig
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Kigmask
region: Mainland China
website note: HTTP 403
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (18): https://x.com/kig_mask/status/1821122006554939404, https://x.com/kig_mask/status/1819721878925459858, https://x.com/kig_mask/status/1819721729020932324, https://x.com/kig_mask/status/1819721593398120495, https://x.com/kig_mask/status/1819721448946319547, https://x.com/kig_mask/status/1819721345267355769, https://x.com/kig_mask/status/1819721201792712862, https://x.com/kig_mask/status/1728816548209635542, https://x.com/kig_mask/status/1727998350916755703, https://x.com/kig_mask/status/1705819959233065171, https://x.com/kig_mask/status/1687024725032382464, https://x.com/kig_mask/status/1682077725711040514, https://x.com/kig_mask/status/1681709904443359232, https://x.com/kig_mask/status/1678378466939658241, https://x.com/kig_mask/status/1678377532373241856, https://x.com/kig_mask/status/1646880722802855938, https://x.com/kig_mask/status/1642457898528935937, https://x.com/kig_mask/status/1638914384222392324
x.com kigurumi bio references (1): https://x.com/kig_mask
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (5): https://x.com/kig_mask/status/1687024725032382464, https://x.com/kig_mask/status/1682077725711040514, https://x.com/kig_mask/status/1681709904443359232, https://x.com/kig_mask/status/1678378466939658241, https://x.com/kig_mask/status/1678377532373241856
x.com 着ぐるみ bio references: none (0)

maker: Kigurumi Factory
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (9): https://x.com/sks1094/status/2013900754290090057, https://x.com/sks1094/status/1983130502094528787, https://x.com/sks1094/status/1974141004006736278, https://x.com/sks1094/status/1954834127330693417, https://x.com/sks1094/status/1941117381570654337, https://x.com/sks1094/status/1936681154440204416, https://x.com/sks1094/status/1904526397936460135, https://x.com/sks1094/status/1900123783027188162, https://x.com/sks1094/status/1879457264274387335
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (1): https://x.com/sks1094/status/1985481136513171591
x.com 着ぐるみ hashtag-only references (1): https://x.com/sks1094/status/1941117381570654337
x.com 着ぐるみ bio references: none (0)

maker: Kigurumi Settings
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (1): https://x.com/Kig_Settings/status/1978324347338010706
x.com kigurumi bio references (1): https://x.com/Kig_Settings
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Kiguyobi
region: Taiwan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (1): https://x.com/kiguyobi/status/1896553141757477247
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: KIGzhz
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (3): https://x.com/kigzhzchafan/status/2066450746032398690, https://x.com/kigzhzchafan/status/2066424210105487528, https://x.com/kigzhzchafan/status/1913774254329627015
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/kigzhzchafan
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: King Mask Studio
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (7): https://x.com/KingMask_studio/status/2078342535790154109, https://x.com/KingMask_studio/status/2068521995915202587, https://x.com/KingMask_studio/status/2057001568424309157, https://x.com/KingMask_studio/status/2049830862016184667, https://x.com/KingMask_studio/status/2049020152616997358, https://x.com/KingMask_studio/status/2034537849480241578, https://x.com/KingMask_studio/status/2033564603343688055
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (7): https://x.com/KingMask_studio/status/2078342535790154109, https://x.com/KingMask_studio/status/2068521995915202587, https://x.com/KingMask_studio/status/2057001568424309157, https://x.com/KingMask_studio/status/2049830862016184667, https://x.com/KingMask_studio/status/2049020152616997358, https://x.com/KingMask_studio/status/2034537849480241578, https://x.com/KingMask_studio/status/2033564603343688055
x.com 着ぐるみ bio references: none (0)

maker: Kirisaki Craft
region: Japan
website note: HTTP 403
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (1): https://x.com/kirisaki_craft/status/1580541602812276737
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Kuroneko Mask Shop
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (6): https://x.com/kuroneko_mask/status/2077568174594429198, https://x.com/kuroneko_mask/status/2077567029599691071, https://x.com/kuroneko_mask/status/2077566184900464975, https://x.com/kuroneko_mask/status/2061436563742150732, https://x.com/kuroneko_mask/status/2019596504529551747, https://x.com/kuroneko_mask/status/2019597781619601682
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (2): https://x.com/kuroneko_mask/status/2077563960753270940, https://x.com/kuroneko_mask/status/2019596504529551747
x.com 着ぐるみ hashtag-only references (4): https://x.com/kuroneko_mask/status/2077568174594429198, https://x.com/kuroneko_mask/status/2077567029599691071, https://x.com/kuroneko_mask/status/2061436563742150732, https://x.com/kuroneko_mask/status/2019597781619601682
x.com 着ぐるみ bio references (1): https://x.com/kuroneko_mask

maker: Laoshu Zone
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (17): https://x.com/zone_rk3ly/status/2086078584561787160, https://x.com/zone_rk3ly/status/2075569158075682856, https://x.com/zone_rk3ly/status/2073004390932463865, https://x.com/zone_rk3ly/status/2070486101551395028, https://x.com/zone_rk3ly/status/2062873959893491979, https://x.com/zone_rk3ly/status/2055255148935668075, https://x.com/zone_rk3ly/status/2053116495270678674, https://x.com/zone_rk3ly/status/2048559953397637275, https://x.com/zone_rk3ly/status/2035004995607953542, https://x.com/zone_rk3ly/status/2032426927680803234, https://x.com/zone_rk3ly/status/2027763329394212912, https://x.com/zone_rk3ly/status/2022293077159993791, https://x.com/zone_rk3ly/status/2019750981332857089, https://x.com/zone_rk3ly/status/2019372356914053216, https://x.com/zone_rk3ly/status/2018654646555045980, https://x.com/zone_rk3ly/status/2009599419554185595, https://x.com/zone_rk3ly/status/1999667217525625129
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Lucky Larus
region: Mainland China
website note: HTTP 403
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (3): https://x.com/Larus_kigurumi/status/2054603916617424901, https://x.com/Larus_kigurumi/status/2054254377473577303, https://x.com/Larus_kigurumi/status/2052420458285617542
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Magic Doll
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (4): https://x.com/MagicDoll1208/status/2012915517217014172, https://x.com/MagicDoll1208/status/2011447704594051293, https://x.com/MagicDoll1208/status/2011114887054082201, https://x.com/MagicDoll1208/status/1963834270541382113
x.com kigurumi bio references (1): https://x.com/MagicDoll1208
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Maple Studio
region: Thailand
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (3): https://x.com/milkpockydoll/status/2079493141975937494, https://x.com/milkpockydoll/status/1988487357017043071, https://x.com/milkpockydoll/status/1983115902016213079
x.com kigurumi hashtag-only references (10): https://x.com/milkpockydoll/status/2083976124854624708, https://x.com/milkpockydoll/status/2083251348946944402, https://x.com/milkpockydoll/status/2080154665862451447, https://x.com/milkpockydoll/status/2058161900299649052, https://x.com/milkpockydoll/status/2057330546045497359, https://x.com/milkpockydoll/status/1993313373526892988, https://x.com/milkpockydoll/status/1991876356863611053, https://x.com/milkpockydoll/status/1983106379167764527, https://x.com/milkpockydoll/status/1970292033328652442, https://x.com/milkpockydoll/status/1969929641835327519
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (3): https://x.com/milkpockydoll/status/1983106379167764527, https://x.com/milkpockydoll/status/1970292033328652442, https://x.com/milkpockydoll/status/1969929641835327519
x.com 着ぐるみ bio references: none (0)

maker: Marshmarocy
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (1): https://x.com/marshmarocy/status/2067950407264109048
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/marshmarocy

maker: Meis
region: Mainland China
site animegao references 1 : https://www.kigis.me/kigurumi | archive: https://web.archive.org/web/20260809173506/https://www.kigis.me/kigurumi
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://www.kigis.me/ | archive: https://web.archive.org/web/*/https://www.kigis.me/
site kigurumi references 2 : https://www.kigis.me/pinhaotou | archive: https://web.archive.org/web/*/https://www.kigis.me/pinhaotou
site kigurumi references 3 : https://www.kigis.me/dolleveryday | archive: https://web.archive.org/web/*/https://www.kigis.me/dolleveryday
site kigurumi references 4 : https://www.kigis.me/kigurumi | archive: https://web.archive.org/web/20260809173506/https://www.kigis.me/kigurumi
site kigurumi references 5 : https://www.kigis.me/query | archive: https://web.archive.org/web/*/https://www.kigis.me/query
site kigurumi references 6 : https://www.kigis.me/piece | archive: https://web.archive.org/web/*/https://www.kigis.me/piece
site kigurumi references 7 : https://www.kigis.me/contact | archive: https://web.archive.org/web/*/https://www.kigis.me/contact
site kigurumi references 8 : https://www.kigis.me/about | archive: https://web.archive.org/web/*/https://www.kigis.me/about
site kigurumi references 9 : https://www.kigis.me/sitemap.xml | archive: https://web.archive.org/web/*/https://www.kigis.me/sitemap.xml
site kigurumi references 10 : https://www.kigis.me/pht-01 | archive: https://web.archive.org/web/*/https://www.kigis.me/pht-01
site kigurumi references 11 : https://www.kigis.me/pht-02 | archive: https://web.archive.org/web/*/https://www.kigis.me/pht-02
site kigurumi references 12 : https://www.kigis.me/pht-03 | archive: https://web.archive.org/web/*/https://www.kigis.me/pht-03
site kigurumi references 13 : https://www.kigis.me/pht-04 | archive: https://web.archive.org/web/*/https://www.kigis.me/pht-04
site kigurumi references 14 : https://www.kigis.me/pht-05 | archive: https://web.archive.org/web/*/https://www.kigis.me/pht-05
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (1): https://x.com/pinhaotou/status/2020148898203890151
x.com kigurumi bio references (1): https://x.com/pinhaotou
site 着ぐるみ references 1 : https://www.kigis.me/kigurumi | archive: https://web.archive.org/web/20260809173506/https://www.kigis.me/kigurumi
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (1): https://x.com/pinhaotou/status/2020148898203890151
x.com 着ぐるみ bio references (1): https://x.com/pinhaotou

maker: Mirrodoll
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (3): https://x.com/mirrodoll/status/1963962594097860906, https://x.com/mirrodoll/status/1950885814742970764, https://x.com/mirrodoll/status/1950521320011407527
x.com kigurumi hashtag-only references (10): https://x.com/mirrodoll/status/1978061850869649895, https://x.com/mirrodoll/status/1977699343026024598, https://x.com/mirrodoll/status/1977014968370577677, https://x.com/mirrodoll/status/1976674222761230707, https://x.com/mirrodoll/status/1970804103438901708, https://x.com/mirrodoll/status/1960725743648039045, https://x.com/mirrodoll/status/1951279273051848917, https://x.com/mirrodoll/status/1948368162023518630, https://x.com/mirrodoll/status/1946846963690811902, https://x.com/mirrodoll/status/1946579679600881766
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (1): https://x.com/mirrodoll/status/1978061850869649895
x.com 着ぐるみ bio references: none (0)

maker: Miaomiaoxing
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (20): https://x.com/mjnln274668/status/2084943390500876794, https://x.com/mjnln274668/status/2084492475759267899, https://x.com/mjnln274668/status/2081710699290804527, https://x.com/mjnln274668/status/2080895308603797668, https://x.com/mjnln274668/status/2080151051895013429, https://x.com/mjnln274668/status/2079517392103973145, https://x.com/mjnln274668/status/2078353838038487276, https://x.com/mjnln274668/status/2077704224377594049, https://x.com/mjnln274668/status/2075550430227292623, https://x.com/mjnln274668/status/2069438550282846471, https://x.com/mjnln274668/status/2067200300537319516, https://x.com/mjnln274668/status/2064004523933548567, https://x.com/mjnln274668/status/2057709523994042768, https://x.com/mjnln274668/status/2056675511729041614, https://x.com/mjnln274668/status/2054467521663906290, https://x.com/mjnln274668/status/2053058465086742874, https://x.com/mjnln274668/status/2051601938316398839, https://x.com/mjnln274668/status/2048754459220787203, https://x.com/mjnln274668/status/2043309980678582759, https://x.com/mjnln274668/status/2040803757236371817
x.com kigurumi bio references (1): https://x.com/mjnln274668
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Monaka Workshop
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/kitijouji

maker: Moyu Kig
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (15): https://x.com/MoyuKig/status/2086274515445686304, https://x.com/MoyuKig/status/2085181362215276737, https://x.com/MoyuKig/status/2080245764882899144, https://x.com/MoyuKig/status/2079769625445962007, https://x.com/MoyuKig/status/2079139635918512482, https://x.com/MoyuKig/status/2078366659761623335, https://x.com/MoyuKig/status/2078002736751386664, https://x.com/MoyuKig/status/2077304075310477451, https://x.com/MoyuKig/status/2076973987507339286, https://x.com/MoyuKig/status/2075073310547963905, https://x.com/MoyuKig/status/2074488888824090909, https://x.com/MoyuKig/status/2074105126210695678, https://x.com/MoyuKig/status/2073370773411320103, https://x.com/MoyuKig/status/2072277118961226177, https://x.com/MoyuKig/status/2071905901439812032
x.com kigurumi bio references (1): https://x.com/MoyuKig
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (16): https://x.com/MoyuKig/status/2086274515445686304, https://x.com/MoyuKig/status/2085181362215276737, https://x.com/MoyuKig/status/2081212921682768331, https://x.com/MoyuKig/status/2080657295034474692, https://x.com/MoyuKig/status/2080245764882899144, https://x.com/MoyuKig/status/2079769625445962007, https://x.com/MoyuKig/status/2079139635918512482, https://x.com/MoyuKig/status/2078366659761623335, https://x.com/MoyuKig/status/2078002736751386664, https://x.com/MoyuKig/status/2077304075310477451, https://x.com/MoyuKig/status/2076973987507339286, https://x.com/MoyuKig/status/2075073310547963905, https://x.com/MoyuKig/status/2074488888824090909, https://x.com/MoyuKig/status/2074105126210695678, https://x.com/MoyuKig/status/2073370773411320103, https://x.com/MoyuKig/status/2071905901439812032
x.com 着ぐるみ bio references: none (0)

maker: MRKT
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (6): https://x.com/IceKKKMID/status/1974625741255094525, https://x.com/IceKKKMID/status/1970797936465571975, https://x.com/IceKKKMID/status/1970797742290329998, https://x.com/IceKKKMID/status/1970797363087446296, https://x.com/IceKKKMID/status/1956302291549507965, https://x.com/IceKKKMID/status/1880893298036048054
x.com kigurumi hashtag-only references (6): https://x.com/IceKKKMID/status/1953739168577904897, https://x.com/IceKKKMID/status/1953738315175539176, https://x.com/IceKKKMID/status/1953737755047170083, https://x.com/IceKKKMID/status/1825556958147141898, https://x.com/IceKKKMID/status/1817084770037432361, https://x.com/IceKKKMID/status/1816296046940807550
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Munimuni Works
region: Japan
site animegao references 1 : https://www.munimuni.jp/p/00015 | archive: https://web.archive.org/web/20260809174025/https://www.munimuni.jp/p/00015
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://www.munimuni.jp/categories/4511657 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/categories/4511657
site kigurumi references 2 : https://www.munimuni.jp/categories/4511695 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/categories/4511695
site kigurumi references 3 : https://www.munimuni.jp/categories/4511698 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/categories/4511698
site kigurumi references 4 : https://www.munimuni.jp/p/00015 | archive: https://web.archive.org/web/20260809174025/https://www.munimuni.jp/p/00015
site kigurumi references 5 : https://www.munimuni.jp/items/64836167 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64836167
site kigurumi references 6 : https://www.munimuni.jp/items/64835285 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64835285
site kigurumi references 7 : https://www.munimuni.jp/items/64835541 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64835541
site kigurumi references 8 : https://www.munimuni.jp/items/64835766 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64835766
site kigurumi references 9 : https://www.munimuni.jp/items/64835959 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64835959
site kigurumi references 10 : https://www.munimuni.jp/items/64837294 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64837294
site kigurumi references 11 : https://www.munimuni.jp/items/64837522 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64837522
site kigurumi references 12 : https://www.munimuni.jp/items/64837728 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64837728
site kigurumi references 13 : https://www.munimuni.jp/items/64837969 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64837969
site kigurumi references 14 : https://www.munimuni.jp/items/64838456 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64838456
site kigurumi references 15 : https://www.munimuni.jp/items/64839478 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64839478
site kigurumi references 16 : https://www.munimuni.jp/items/64839809 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64839809
site kigurumi references 17 : https://www.munimuni.jp/items/64840803 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64840803
site kigurumi references 18 : https://www.munimuni.jp/items/64841096 | archive: https://web.archive.org/web/*/https://www.munimuni.jp/items/64841096
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Mzdodo
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (7): https://x.com/Mzdodo599/status/2083388346060144794, https://x.com/Mzdodo599/status/2080837309377941824, https://x.com/Mzdodo599/status/2070909511112814664, https://x.com/Mzdodo599/status/2060370062109032653, https://x.com/Mzdodo599/status/2045781965530640582, https://x.com/Mzdodo599/status/2034611726512185374, https://x.com/Mzdodo599/status/2031954292299743721
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Neko Laboratory
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (2): https://x.com/NeccoLaboratory/status/1964549351960957050, https://x.com/NeccoLaboratory/status/1964306007586459657
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Nekotofu
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (19): https://x.com/nekotoufufu/status/2085641036827931091, https://x.com/nekotoufufu/status/2085276356322201698, https://x.com/nekotoufufu/status/2084944298064384491, https://x.com/nekotoufufu/status/2083458242479628793, https://x.com/nekotoufufu/status/2082807880655532437, https://x.com/nekotoufufu/status/2072271746003239314, https://x.com/nekotoufufu/status/2069182840877863263, https://x.com/nekotoufufu/status/2068206834423673143, https://x.com/nekotoufufu/status/2067907932726153726, https://x.com/nekotoufufu/status/2067523562110615604, https://x.com/nekotoufufu/status/2067106837791682872, https://x.com/nekotoufufu/status/2066647530394571203, https://x.com/nekotoufufu/status/2062848250118611415, https://x.com/nekotoufufu/status/2061681926554202382, https://x.com/nekotoufufu/status/2054784241142206668, https://x.com/nekotoufufu/status/2054396688580886613, https://x.com/nekotoufufu/status/2051898739523203137, https://x.com/nekotoufufu/status/2049421781166080356, https://x.com/nekotoufufu/status/2046222613748629682
x.com kigurumi bio references (1): https://x.com/nekotoufufu
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (19): https://x.com/nekotoufufu/status/2085641036827931091, https://x.com/nekotoufufu/status/2085276356322201698, https://x.com/nekotoufufu/status/2084944298064384491, https://x.com/nekotoufufu/status/2083458242479628793, https://x.com/nekotoufufu/status/2082807880655532437, https://x.com/nekotoufufu/status/2072271746003239314, https://x.com/nekotoufufu/status/2069182840877863263, https://x.com/nekotoufufu/status/2068206834423673143, https://x.com/nekotoufufu/status/2067907932726153726, https://x.com/nekotoufufu/status/2067523562110615604, https://x.com/nekotoufufu/status/2067106837791682872, https://x.com/nekotoufufu/status/2066647530394571203, https://x.com/nekotoufufu/status/2062848250118611415, https://x.com/nekotoufufu/status/2061681926554202382, https://x.com/nekotoufufu/status/2054784241142206668, https://x.com/nekotoufufu/status/2054396688580886613, https://x.com/nekotoufufu/status/2051898739523203137, https://x.com/nekotoufufu/status/2049421781166080356, https://x.com/nekotoufufu/status/2046222613748629682
x.com 着ぐるみ bio references: none (0)

maker: NM Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (2): https://x.com/nonhumanmasque/status/2013133151099666799, https://x.com/nonhumanmasque/status/1919232163435724993
x.com kigurumi hashtag-only references (11): https://x.com/nonhumanmasque/status/1963522358834323807, https://x.com/nonhumanmasque/status/1919936650743775456, https://x.com/nonhumanmasque/status/1914673682800349624, https://x.com/nonhumanmasque/status/1906862709544534163, https://x.com/nonhumanmasque/status/1906566717662216633, https://x.com/nonhumanmasque/status/1901266012575588616, https://x.com/nonhumanmasque/status/1900540128294031570, https://x.com/nonhumanmasque/status/1883967112961745090, https://x.com/nonhumanmasque/status/1877656826793095623, https://x.com/nonhumanmasque/status/1876797637824770273, https://x.com/nonhumanmasque/status/1876660674455114050
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Nukopan
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/nukopan
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/nukopan

maker: OM Doll JP
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/omdolljp

maker: Ozawa Dango
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/ozawa_dango

maker: Power Kigurumi
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/Power_9567
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Raigeki Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (3): https://x.com/RAIGEKI_Li/status/2057147724118765707, https://x.com/RAIGEKI_Li/status/1984626024777462203, https://x.com/RAIGEKI_Li/status/1977391567523512654
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (3): https://x.com/RAIGEKI_Li/status/2057147724118765707, https://x.com/RAIGEKI_Li/status/1984626024777462203, https://x.com/RAIGEKI_Li/status/1977391567523512654
x.com 着ぐるみ bio references (1): https://x.com/RAIGEKI_Li

maker: Ricky Works
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (3): https://x.com/Ricky_Works/status/2013589526179127368, https://x.com/Ricky_Works/status/1888510954708852889, https://x.com/Ricky_Works/status/1888356342211174909
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/Ricky_Works

maker: Rintaro
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/RINKIGooo

maker: Salmon Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (17): https://x.com/samon_ii/status/2075917093132984443, https://x.com/samon_ii/status/2074450991601406402, https://x.com/samon_ii/status/2066069362264666305, https://x.com/samon_ii/status/2062765017192407542, https://x.com/samon_ii/status/2059530339429790009, https://x.com/samon_ii/status/2058865919049580839, https://x.com/samon_ii/status/2054152694529769850, https://x.com/samon_ii/status/2053128608739381399, https://x.com/samon_ii/status/2051546867855745430, https://x.com/samon_ii/status/2041871706244182070, https://x.com/samon_ii/status/2041723768662532136, https://x.com/samon_ii/status/2035222960978764144, https://x.com/samon_ii/status/2034608227107889561, https://x.com/samon_ii/status/2031950588192477631, https://x.com/samon_ii/status/2028778541316493485, https://x.com/samon_ii/status/1982746644539163013, https://x.com/samon_ii/status/1978337667621290119
x.com kigurumi bio references (1): https://x.com/samon_ii
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (17): https://x.com/samon_ii/status/2075917093132984443, https://x.com/samon_ii/status/2074450991601406402, https://x.com/samon_ii/status/2066069362264666305, https://x.com/samon_ii/status/2062765017192407542, https://x.com/samon_ii/status/2059530339429790009, https://x.com/samon_ii/status/2058865919049580839, https://x.com/samon_ii/status/2054152694529769850, https://x.com/samon_ii/status/2053128608739381399, https://x.com/samon_ii/status/2051546867855745430, https://x.com/samon_ii/status/2041871706244182070, https://x.com/samon_ii/status/2041723768662532136, https://x.com/samon_ii/status/2035222960978764144, https://x.com/samon_ii/status/2034608227107889561, https://x.com/samon_ii/status/2031950588192477631, https://x.com/samon_ii/status/2028778541316493485, https://x.com/samon_ii/status/1982746644539163013, https://x.com/samon_ii/status/1978337667621290119
x.com 着ぐるみ bio references: none (0)

maker: Shuijing Renxing
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (4): https://x.com/SJrenxing/status/1934542097321021851, https://x.com/SJrenxing/status/1934388759342232055, https://x.com/SJrenxing/status/1933356962047242720, https://x.com/SJrenxing/status/1884224305497792560
x.com kigurumi bio references (1): https://x.com/SJrenxing
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Shushu Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (20): https://x.com/Shushu_kigurumi/status/2076677797066760256, https://x.com/Shushu_kigurumi/status/2076266008244011133, https://x.com/Shushu_kigurumi/status/2074825911225233757, https://x.com/Shushu_kigurumi/status/2074149634659037396, https://x.com/Shushu_kigurumi/status/2072189321529168247, https://x.com/Shushu_kigurumi/status/2071556616122757353, https://x.com/Shushu_kigurumi/status/2013260536096403780, https://x.com/Shushu_kigurumi/status/2012863766333984938, https://x.com/Shushu_kigurumi/status/2000939725260276181, https://x.com/Shushu_kigurumi/status/2000854544541270518, https://x.com/Shushu_kigurumi/status/2000608991639109778, https://x.com/Shushu_kigurumi/status/2000125059953005046, https://x.com/Shushu_kigurumi/status/1995488809736421632, https://x.com/Shushu_kigurumi/status/1995098577933406534, https://x.com/Shushu_kigurumi/status/1994686466921042156, https://x.com/Shushu_kigurumi/status/1989273303211733018, https://x.com/Shushu_kigurumi/status/1988925390627434928, https://x.com/Shushu_kigurumi/status/1985610683963359632, https://x.com/Shushu_kigurumi/status/1984952544477786202, https://x.com/Shushu_kigurumi/status/1983516699438838223
x.com kigurumi bio references (1): https://x.com/Shushu_kigurumi
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Studio Delphinium
region: USA
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://www.studiodelphinium.com/ | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/
site kigurumi references 2 : https://www.studiodelphinium.com/gallery | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/gallery
site kigurumi references 3 : https://www.studiodelphinium.com/commissions | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/commissions
site kigurumi references 4 : https://www.studiodelphinium.com/commission-process | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/commission-process
site kigurumi references 5 : https://www.studiodelphinium.com/all-about-the-mask | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/all-about-the-mask
site kigurumi references 6 : https://www.studiodelphinium.com/mask-care | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/mask-care
site kigurumi references 7 : https://www.studiodelphinium.com/diy | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/diy
site kigurumi references 8 : https://www.studiodelphinium.com/how-to-dye-your-own-hadatai-fabric | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/how-to-dye-your-own-hadatai-fabric
site kigurumi references 9 : https://www.studiodelphinium.com/shipping-info | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/shipping-info
site kigurumi references 10 : https://www.studiodelphinium.com/terms-conditions | archive: https://web.archive.org/web/*/https://www.studiodelphinium.com/terms-conditions
x.com kigurumi references (1): https://x.com/delphiniumkig/status/2056541522829463775
x.com kigurumi hashtag-only references (17): https://x.com/delphiniumkig/status/2069572683096871146, https://x.com/delphiniumkig/status/2068137803041390705, https://x.com/delphiniumkig/status/2067770095544213654, https://x.com/delphiniumkig/status/2067069337433682373, https://x.com/delphiniumkig/status/2066691598725808340, https://x.com/delphiniumkig/status/2056908978169233455, https://x.com/delphiniumkig/status/2055455971330146523, https://x.com/delphiniumkig/status/2054019854387081241, https://x.com/delphiniumkig/status/2053291173523947691, https://x.com/delphiniumkig/status/2049907044589687247, https://x.com/delphiniumkig/status/2048826860302209076, https://x.com/delphiniumkig/status/2034393642580730000, https://x.com/delphiniumkig/status/2033980071501852703, https://x.com/delphiniumkig/status/2015540622690529487, https://x.com/delphiniumkig/status/2004609633605091733, https://x.com/delphiniumkig/status/2004254207336202334, https://x.com/delphiniumkig/status/2003144842717839630
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (18): https://x.com/delphiniumkig/status/2069572683096871146, https://x.com/delphiniumkig/status/2068137803041390705, https://x.com/delphiniumkig/status/2067770095544213654, https://x.com/delphiniumkig/status/2067069337433682373, https://x.com/delphiniumkig/status/2066691598725808340, https://x.com/delphiniumkig/status/2056908978169233455, https://x.com/delphiniumkig/status/2056541522829463775, https://x.com/delphiniumkig/status/2055455971330146523, https://x.com/delphiniumkig/status/2054019854387081241, https://x.com/delphiniumkig/status/2053291173523947691, https://x.com/delphiniumkig/status/2049907044589687247, https://x.com/delphiniumkig/status/2048826860302209076, https://x.com/delphiniumkig/status/2034393642580730000, https://x.com/delphiniumkig/status/2033980071501852703, https://x.com/delphiniumkig/status/2015540622690529487, https://x.com/delphiniumkig/status/2004609633605091733, https://x.com/delphiniumkig/status/2004254207336202334, https://x.com/delphiniumkig/status/2003144842717839630
x.com 着ぐるみ bio references: none (0)

maker: Studio RonMaca
region: South Korea
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references 1 : https://www.studioronmaca.com/ | archive: https://web.archive.org/web/*/https://www.studioronmaca.com/
site kigurumi references 2 : https://www.studioronmaca.com/welcome | archive: https://web.archive.org/web/*/https://www.studioronmaca.com/welcome
site kigurumi references 3 : https://www.studioronmaca.com/welcome/english | archive: https://web.archive.org/web/*/https://www.studioronmaca.com/welcome/english
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (6): https://x.com/Studio_RonMaca/status/2085290314466750567, https://x.com/Studio_RonMaca/status/2067506601683271911, https://x.com/Studio_RonMaca/status/2059210439515680796, https://x.com/Studio_RonMaca/status/2029883555502023016, https://x.com/Studio_RonMaca/status/2010259692803723430, https://x.com/Studio_RonMaca/status/1982779968917492161
x.com kigurumi bio references (1): https://x.com/Studio_RonMaca
site 着ぐるみ references 1 : https://www.studioronmaca.com/welcome/%E6%97%A5%E6%9C%AC%E8%AA%9E | archive: https://web.archive.org/web/*/https://www.studioronmaca.com/welcome/%E6%97%A5%E6%9C%AC%E8%AA%9E
x.com 着ぐるみ references (1): https://x.com/Studio_RonMaca/status/2034234839814307875
x.com 着ぐるみ hashtag-only references (8): https://x.com/Studio_RonMaca/status/2085290314466750567, https://x.com/Studio_RonMaca/status/2067506601683271911, https://x.com/Studio_RonMaca/status/2059210439515680796, https://x.com/Studio_RonMaca/status/2048672783467737138, https://x.com/Studio_RonMaca/status/2043996831722750032, https://x.com/Studio_RonMaca/status/2029883555502023016, https://x.com/Studio_RonMaca/status/2010259692803723430, https://x.com/Studio_RonMaca/status/1982779968917492161
x.com 着ぐるみ bio references: none (0)

maker: Teitoku Workshop
region: Hong Kong
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
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
site kigurumi references 17 : https://www.teitokuworkshop.com/jp/news/10thanni | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/news/10thanni
site kigurumi references 18 : https://www.teitokuworkshop.com/jp/production-portfolio/category/prod | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/production-portfolio/category/prod
site kigurumi references 19 : https://www.teitokuworkshop.com/jp/production-portfolio/ninon-joubert-49pp5-jzt7t-ppe9g | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/production-portfolio/ninon-joubert-49pp5-jzt7t-ppe9g
site kigurumi references 20 : https://www.teitokuworkshop.com/en/production-portfolio/ninon-joubert-49pp5-jzt7t | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/production-portfolio/ninon-joubert-49pp5-jzt7t
site kigurumi references 21 : https://www.teitokuworkshop.com/en/production-portfolio/ninon-joubert-49pp5 | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/production-portfolio/ninon-joubert-49pp5
site kigurumi references 22 : https://www.teitokuworkshop.com/en/production-portfolio/ninon-joubert | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/production-portfolio/ninon-joubert
site kigurumi references 23 : https://www.teitokuworkshop.com/en/news/10thanniversary | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/news/10thanniversary
site kigurumi references 24 : https://www.teitokuworkshop.com/en/production-portfolio/category/prod | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/en/production-portfolio/category/prod
site kigurumi references 25 : https://www.teitokuworkshop.com/jp/production-portfolio?author=65ee16ae92c04741b761b3a5 | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/production-portfolio?author=65ee16ae92c04741b761b3a5
site kigurumi references 26 : https://www.teitokuworkshop.com/jp/production-portfolio?author=65edf85df830bf44e193ecb5 | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/production-portfolio?author=65edf85df830bf44e193ecb5
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/Teitoku_shop
site 着ぐるみ references 1 : https://www.teitokuworkshop.com/ | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/
site 着ぐるみ references 2 : https://www.teitokuworkshop.com/jp/about | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/about
site 着ぐるみ references 3 : https://www.teitokuworkshop.com/jp/home | archive: https://web.archive.org/web/*/https://www.teitokuworkshop.com/jp/home
x.com 着ぐるみ references (3): https://x.com/Teitoku_shop/status/2058602315997995356, https://x.com/Teitoku_shop/status/1940733509607321904, https://x.com/Teitoku_shop/status/1850150932333609169
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Tokal
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (18): https://x.com/tokalcms/status/2072267129320308883, https://x.com/tokalcms/status/1999036422075158961, https://x.com/tokalcms/status/1991441589881958781, https://x.com/tokalcms/status/1976593521567281551, https://x.com/tokalcms/status/1929492417767497789, https://x.com/tokalcms/status/1926484032071589999, https://x.com/tokalcms/status/1897546300905648528, https://x.com/tokalcms/status/1880193846338052577, https://x.com/tokalcms/status/1870057593932321025, https://x.com/tokalcms/status/1867168162942452130, https://x.com/tokalcms/status/1796096996891107561, https://x.com/tokalcms/status/1782707855495479322, https://x.com/tokalcms/status/1782342569768489152, https://x.com/tokalcms/status/1730512277139570842, https://x.com/tokalcms/status/1724358531531637147, https://x.com/tokalcms/status/1724358863263252976, https://x.com/tokalcms/status/1542349344648876032, https://x.com/tokalcms/status/1695766105762230444
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/tokalcms

maker: Tokyo Fantasy Workshop
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/TotGensFactory
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (1): https://x.com/TotGensFactory/status/2073788928755433871
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references (1): https://x.com/TotGensFactory

maker: Umoon Kigurumi
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (1): https://x.com/Umoon_kigurumi/status/1920768275463524577
x.com kigurumi hashtag-only references (5): https://x.com/Umoon_kigurumi/status/1921890311971717327, https://x.com/Umoon_kigurumi/status/1921780998036934698, https://x.com/Umoon_kigurumi/status/1920318939986264410, https://x.com/Umoon_kigurumi/status/1912516527993286895, https://x.com/Umoon_kigurumi/status/1912175808367788431
x.com kigurumi bio references (1): https://x.com/Umoon_kigurumi
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (5): https://x.com/Umoon_kigurumi/status/1921890311971717327, https://x.com/Umoon_kigurumi/status/1921780998036934698, https://x.com/Umoon_kigurumi/status/1920318939986264410, https://x.com/Umoon_kigurumi/status/1912516527993286895, https://x.com/Umoon_kigurumi/status/1912175808367788431
x.com 着ぐるみ bio references: none (0)

maker: Very Good Man's Mask Studio
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (1): https://x.com/mBtg5bjdhcvIx6H/status/2083892225822666804
x.com kigurumi bio references (1): https://x.com/mBtg5bjdhcvIx6H
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (1): https://x.com/mBtg5bjdhcvIx6H/status/2083892225822666804
x.com 着ぐるみ bio references (1): https://x.com/mBtg5bjdhcvIx6H

maker: Vive Design
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (20): https://x.com/ViveKigu/status/2056281969558954138, https://x.com/ViveKigu/status/2051940553030500801, https://x.com/ViveKigu/status/2048996705866264687, https://x.com/ViveKigu/status/2048294285863514541, https://x.com/ViveKigu/status/2047604090872729748, https://x.com/ViveKigu/status/2046999771307717088, https://x.com/ViveKigu/status/2046261235218518366, https://x.com/ViveKigu/status/2045072048121389523, https://x.com/ViveKigu/status/2044315060512928154, https://x.com/ViveKigu/status/2043959443805933592, https://x.com/ViveKigu/status/2004573973011742813, https://x.com/ViveKigu/status/2004573201511469443, https://x.com/ViveKigu/status/2004546916831629755, https://x.com/ViveKigu/status/2003059144182685818, https://x.com/ViveKigu/status/2003059027836829775, https://x.com/ViveKigu/status/2001291009226146040, https://x.com/ViveKigu/status/2000523249587757140, https://x.com/ViveKigu/status/2000521826888561038, https://x.com/ViveKigu/status/2000521414705905691, https://x.com/ViveKigu/status/1999743176031248640
x.com kigurumi bio references (1): https://x.com/ViveKigu
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Anxinli Leiqi
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (2): https://x.com/xi_qi24992/status/2026592521883890006, https://x.com/xi_qi24992/status/2013245766215893123
x.com kigurumi hashtag-only references (10): https://x.com/xi_qi24992/status/2021954726292812015, https://x.com/xi_qi24992/status/2019082155452936311, https://x.com/xi_qi24992/status/2018367880677716207, https://x.com/xi_qi24992/status/2018167575004545307, https://x.com/xi_qi24992/status/2016204754448482314, https://x.com/xi_qi24992/status/2015836960741527656, https://x.com/xi_qi24992/status/2015461586698485802, https://x.com/xi_qi24992/status/2015131365092872251, https://x.com/xi_qi24992/status/2015128728335216728, https://x.com/xi_qi24992/status/2014753423493890240
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (7): https://x.com/xi_qi24992/status/2018167575004545307, https://x.com/xi_qi24992/status/2016204754448482314, https://x.com/xi_qi24992/status/2015836960741527656, https://x.com/xi_qi24992/status/2015461586698485802, https://x.com/xi_qi24992/status/2015131365092872251, https://x.com/xi_qi24992/status/2015128728335216728, https://x.com/xi_qi24992/status/2013245766215893123
x.com 着ぐるみ bio references: none (0)

maker: Xianbei Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references (20): https://x.com/Xianbei_KIG/status/2002336429721235670, https://x.com/Xianbei_KIG/status/2002336353288442157, https://x.com/Xianbei_KIG/status/2002336294320627838, https://x.com/Xianbei_KIG/status/2002336225974444463, https://x.com/Xianbei_KIG/status/2002336152658063591, https://x.com/Xianbei_KIG/status/2002336090766897369, https://x.com/Xianbei_KIG/status/2002336038933704833, https://x.com/Xianbei_KIG/status/2002335970017103931, https://x.com/Xianbei_KIG/status/2002335866673607101, https://x.com/Xianbei_KIG/status/2002335774050799636, https://x.com/Xianbei_KIG/status/1989648682871066885, https://x.com/Xianbei_KIG/status/1989648628131270851, https://x.com/Xianbei_KIG/status/1989648576222535848, https://x.com/Xianbei_KIG/status/1989648513362542713, https://x.com/Xianbei_KIG/status/1989648442537455846, https://x.com/Xianbei_KIG/status/1983820838534275582, https://x.com/Xianbei_KIG/status/1983417721242161526, https://x.com/Xianbei_KIG/status/1983417653797781581, https://x.com/Xianbei_KIG/status/1983417596482597192, https://x.com/Xianbei_KIG/status/1983417530015461534
x.com kigurumi bio references (1): https://x.com/Xianbei_KIG
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Xingyueqi Workshop
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references (5): https://x.com/xyq_kig/status/2058548155223089160, https://x.com/xyq_kig/status/2056761504540790817, https://x.com/xyq_kig/status/2055167847589179604, https://x.com/xyq_kig/status/2054807372166799838, https://x.com/xyq_kig/status/2053465612903690531
x.com kigurumi hashtag-only references (15): https://x.com/xyq_kig/status/2077623780948734450, https://x.com/xyq_kig/status/2069772351802364309, https://x.com/xyq_kig/status/2066879807644971096, https://x.com/xyq_kig/status/2066128661791846838, https://x.com/xyq_kig/status/2064700762366914696, https://x.com/xyq_kig/status/2061819617082011900, https://x.com/xyq_kig/status/2061428327009906792, https://x.com/xyq_kig/status/2061004142500573654, https://x.com/xyq_kig/status/2060370974869262845, https://x.com/xyq_kig/status/2060004691719958854, https://x.com/xyq_kig/status/2058873024166990227, https://x.com/xyq_kig/status/2057429379198943509, https://x.com/xyq_kig/status/2055892711564320884, https://x.com/xyq_kig/status/2054526344776864066, https://x.com/xyq_kig/status/2053099726980219121
x.com kigurumi bio references (1): https://x.com/xyq_kig
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references (19): https://x.com/xyq_kig/status/2077623780948734450, https://x.com/xyq_kig/status/2069772351802364309, https://x.com/xyq_kig/status/2066879807644971096, https://x.com/xyq_kig/status/2066128661791846838, https://x.com/xyq_kig/status/2064700762366914696, https://x.com/xyq_kig/status/2061819617082011900, https://x.com/xyq_kig/status/2061428327009906792, https://x.com/xyq_kig/status/2061004142500573654, https://x.com/xyq_kig/status/2060370974869262845, https://x.com/xyq_kig/status/2060004691719958854, https://x.com/xyq_kig/status/2058873024166990227, https://x.com/xyq_kig/status/2058548155223089160, https://x.com/xyq_kig/status/2057429379198943509, https://x.com/xyq_kig/status/2056761504540790817, https://x.com/xyq_kig/status/2055892711564320884, https://x.com/xyq_kig/status/2055167847589179604, https://x.com/xyq_kig/status/2054807372166799838, https://x.com/xyq_kig/status/2053465612903690531, https://x.com/xyq_kig/status/2053099726980219121
x.com 着ぐるみ bio references: none (0)

maker: Yu Mao Zhizao
region: Mainland China
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references (1): https://x.com/qingkongmiaoao
site 着ぐるみ references: none (0)
x.com 着ぐるみ references: none (0)
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

maker: Zukokan
region: Japan
site animegao references: none (0)
x.com animegao references: none (0)
x.com animegao hashtag-only references: none (0)
x.com animegao bio references: none (0)
site kigurumi references: none (0)
x.com kigurumi references: none (0)
x.com kigurumi hashtag-only references: none (0)
x.com kigurumi bio references: none (0)
site 着ぐるみ references: none (0)
x.com 着ぐるみ references (1): https://x.com/zukomill/status/2086457829381296143
x.com 着ぐるみ hashtag-only references: none (0)
x.com 着ぐるみ bio references: none (0)

makers with zero animegao reference:
2D Fantasy Aria BHY Renxing Fantasy Masks Haagaau Kigurumi Workshop Heyaoheyao HiDolls Kaga Kigurumi KFY Aniplus KigLand Kirisame Factory Lightning Natural Factory New Face Doll RINS Sakurano Shinkai Workshop Build Up Studio SIGMA Scarlet0rabbit W Rabbit Mi 4uuone A2 Laboratory Atelier NaNaoGi Ayame Store BEADOLL Bear Technique Studio Boundary Chiba Subaru Chikima Chilca Chris and Meph Cover Dollkii Dora Studio ELYSIUM Ezo Fox Workshop Gurgle Love Haka Renxing Harinezumi Workshop Huyaoshouzuo Hyokkame Iris Kigurumi Justin Bailey Kagaribi Workshop KaikaSakura Art Kaiser Factory Kawaiidoll Kig Kemono Mori KigCos Kigmask Kigurumi Factory Kigurumi Settings Kiguyobi KIGzhz King Mask Studio Kirisaki Craft Kuroneko Mask Shop Laoshu Zone Lucky Larus Magic Doll Maple Studio Marshmarocy Miaoxing Zhonggong Mihashi Mato Mirrodoll Miaomiaoxing Moli's Monaka Workshop Moyu Kig MRKT Mzdodo Neko Laboratory Nekotofu NM Workshop Nukopan OM Doll JP Ozawa Dango Power Kigurumi Raigeki Workshop Ricky Works Rintaro Salmon Workshop Shuijing Renxing Shushu Workshop Start Cosplay Studio Delphinium Studio Fractal Studio RonMaca Teitoku Workshop Tokal Tokyo Fantasy Workshop Trevor Umoon Kigurumi Very Good Man's Mask Studio Vive Design Anxinli Leiqi Xianbei Workshop Xingyueqi Workshop Yousen DollKig Yu Mao Zhizao Zukokan

totals:
  animegao: 6 makers | site 5 | x.com general 0 | x.com hashtag-only 1 | x.com bio 1
  kigurumi: 76 makers | site 18 | x.com general 30 | x.com hashtag-only 57 | x.com bio 50
  着ぐるみ: 54 makers | site 8 | x.com general 17 | x.com hashtag-only 31 | x.com bio 27
```

</details>
</details>

## Makers and their usage

Totals:

Only 6 makers out of 107 used the term Animegao. Five of those uses were on websites, with a single maker, GKO, using it on X. In specific GKO has on their bio "A kigurumi mask, animegao studio in Taiwan", and uses #animegao with over a dozen other hashtags on most of their posts. Still, they remain Kigurumi Mask first and foremost in usage.

76 makers out of 107 specifically used Kigurumi in English. Of those that had websites, 18 mentioned Kigurumi on them. On X, 50 had kigurumi in their bio, 57 used #kigurumi, and 30 mentioned kigurumi in the body of at least one of their last 20 posts.

The rest of the makers did not use either, using only terms in their own language for Kigurumi. This is also due to many makers simply not targeting western markets.

For example, 54 makers used the Japanese for Kigurumi, 着ぐるみ. On websites: 8 instances. On X: 17 instances in posts, 31 #着ぐるみ uses in the last 20 posts, and 27 had it in their X bios.

For those new to Kigurumi who may be asking "why X social media?", the answer is simple. Despite the state of X (formerly Twitter) it is where almost all makers, regardless of region, are present and posting. X is the de facto platform for Kigurumi makers and performers. Although many makers will still post on other platforms, such as many Chinese makers posting on Xiaohongshu.

### Those that used Animegao

Lets go through maker by maker to see those who used the term Animegao and inspect their usage. Each section covers website usage, then X, then a short takeaway.

#### Black Cat Kig

Located in Mainland China Region.

**Website:** On and only on their [gallery](https://blackcatkig.com/pages/gallery) page they mention "Animegao Kigurumi", once. Comparatively they use Kigurumi on at least 159 other pages, ranging from the homepage, to example masks, the ordering process, and general guides.

**X (last 20 posts):** No mentions of Animegao. 8 posts include general usage of Kigurumi, 11 feature #kigurumi, and 2 feature #着ぐるみ.

**Takeaway:** One gallery mention against heavy Kigurumi usage everywhere else. Not really in their vocabulary.

#### Goukaou (GKO)

Located in Taiwan Region.

**Website:** No mentions of Animegao. Multiple references to Kigurumi.

**X (last 20 posts):** Both #Kigurumi and #Animegao show up in 10 posts, largely avoiding either term in the body of the post itself. This is alongside a number of other related hashtags including #着ぐるみ, for example:
`#kig #kiger #着ぐるみ #Kigurumi #面具 #マスク #キグルミ #GKO #goukaou #GKO_Kigurumi_Studio #コスプレ #cosplay #costume #美少女着ぐるみ #animegao #animegaokigurumi #kigurumimask`

Truly an example of "spray and pray" as it comes to hashtag usage, trying to cover every base possible and maximize reach.

**Bio:** "A kigurumi mask, animegao studio in Taiwan". Primary focus is still on "kigurumi mask" over "animegao". The Japanese part of their bio is essentially similar but says "anime character design" in place of animegao.

**Takeaway:** The only maker with real social media Animegao usage, and even then it is almost entirely hashtag padding. Kigurumi Mask usage remains first and foremost.

#### MidDream Kigu (Formerly Kig Lover)

Located in Mainland China Region.
Relatively newer maker, and unlike most other Mainland Chinese maker entities, this is one specifically trying to target western buyers.

**Website:** Mentions "Animegao Kigu" across 16 pages, still dwarfed by 23 uses of kigurumi in general across their pages.

**X (last 20 posts):** No animegao in any context. Kigurumi in general is mentioned once, #kigurumi in 7 posts.

**Takeaway:** I would prescribe their usage as primarily trying to cover terms they believe western buyers may be searching for. Curiously they use "animegao kigu" rather than "animegao kigurumi", but that is neither here nor there.

#### DAME

Located in the UK.

**Website:** On their homepage they mention "animegao kigurumi" after previously describing themselves as a "new kigurumi enterprise". That page is duplicated across both https://damekigurumi.com/ and https://damekigurumi.com/home. Other than that, the only other found reference to animegao is an embedded X post on https://damekigurumi.com/Blog/What-Happened-in-2021 from the now deleted X account @StephanieNeckk.

**X (last 20 posts):** Zero references to Animegao. One use of Kigurumi in the body of a post. Their X bio uses kigurumi, not animegao.

**Takeaway:** Even among western makers, Animegao is largely absent from usage.

#### MEIS/Pinhaotou

Located in Mainland China Region, with a Japanese presence on X.

**Website:** One usage of Animegao on their main Kigurumi mask primer page, https://www.kigis.me/kigurumi, where they mention Animegao being used in western contexts and how it started being used around 2005, basically after the initial edit of wikipedia to include the term was done. Comparatively they use Kigurumi on 14 other pages.

**X (last 20 posts):** No animegao in any context. #kigurumi in 1 post. Bio mentions Kigurumi and 着ぐるみ, not animegao.

**Takeaway:** Mentions Animegao only to explain it as a western term. Actual branding stays on Kigurumi / 着ぐるみ.

#### Munimuni Works

Located in Japan.

**Website:** A single reference detected. Notably https://www.munimuni.jp/p/00015 essentially points out that in Japan what they call Kigurumi Masks, or Bishoujo Kigurumi, are in the west called Kigurumi, Animegao, "etc". They do however use Kigurumi in English across four of their pages.

**X (last 20 posts):** Zero usage of either English phrasing. Bio has no explicit mention of Kigurumi, 着ぐるみ, or animegao.

**Takeaway:** Same pattern as MEIS. Animegao shows up only as "this is what the west calls it", not generally in their marketing.

### Summary

Going through the results, almost all usage is just mentioning that the term Animegao exists as a western term, or trying to capture SEO. Notably makers almost exclusively will use Kigurumi or Kigurumi Mask when discussing the hobby in English.

The only real usage on social media from makers is by GKO, who tends to include over a dozen hashtags in each post to maximize reach. Anecdotally that reflects most remaining usage by performers online too, existing as just another hashtag to throw in the wind.

## Kigurumi vs Kigurumi Mask - August 11th Addendum

This addendum comes two days after the initial posting of this publication, and is a follow up to the initial scan.
The script was updated to include comparison of Kigurumi vs Kigurumi Mask in usage, and the results are summarized as follows:

Of the 76 makers that used Kigurumi, 46 used Kigurumi without any mention of Kigurumi Mask, while the remaining 30 did use Kigurumi Mask in some capacity.

In general websites were the most likely to use the term Kigurumi Mask, possibly owing to the storefront and gallery natures of many of the sites.

On X, Kigurumi Mask usage was a fraction of plain Kigurumi usage across general usage in posts, as hashtags, and in bios. In general posts this was 143 instances of kigurumi vs 11 of kigurumi mask, in hashtag 587 uses of Kigurumi vs 82 of Kigurumi Mask, and in bios 50 mentions of Kigurumi vs 13 of Kigurumi Mask.

The full August 11th script output is available [here](https://github.com/kamen-kigu/scan-animegao-script/blob/main/scan-output-Aug11.txt) and can be used to further inspect the results.

This will hopefully be the last addendum to this publication.
