# twitter-unblur
Instructions for how to remove the "Warning: sensitive content" warnings on Twitter/X.

## Prerequisites 
1. Chrome or Chromium (Edge, Opera/GX, Brave, Vivaldi, etc.) browswers.
2. Twitter / X on a desktop computer.
3. Optional: [uBlock Origin](https://github.com/gorhill/uBlock)
   
## How to
1. Install the extension [X / Twitter Feature Flags](https://chromewebstore.google.com/detail/x-twitter-feature-flags/phioeneleonlckednejcmajbkmhhiepm).
2. Open Twitter, press "Features" (below "Profile" and above "More").
3. Using the search box at the top of the overlay, find the following flags and **un-check** the boxes for:
    1. `media_visibility_treatments_blurred_media_interstitial_enabled`
    2. `sensitive_tweet_warnings_enabled`
4. Press the Save Changes button at the bottom.
5. Refresh.

This fixed blur on my timeline, replies, and related tweets but the Media tab was still blurred for me. To fix that:

1. Open uBlock Origin's settings page (Extensions button in Chrome, click on uBlock Origin in the dropdown).
2. Select My filters and add the following filter rules:
    ````
    twitter.com##.r-yfv4eo:style(filter: none !important;)
    twitter.com##.r-1ffoksr:style(display: none !important;)
    twitter.com##.r-drfeu3:style(display: none !important;)
    twitter.com##.r-jwli3a:style(display: none !important;)
    twitter.com##.r-1cmwbt1:style(display: none !important;)
    ````
3. Press the Apply changes button at the top.
4. Refresh and you're done!

## Alternatives
- [Un-blur extension content script](https://t.co/rJlX1VVyh7) - works, but doesn't preserve video autoplay as you scroll the TL which personally I liked
- [unBlurd.](https://chromewebstore.google.com/detail/unblurd-by-wumbl3/gifejdknamachffbkgblclhpojdcjodk) - preserves video autoplay but doesn't always work
- [Twitter remove sensitive media crap](https://greasyfork.org/en/scripts/437359-twitter-hide-content-warning-crap) - doesn't work fully for me (and relies on a userscript manager).

## Notes
This is just what worked for me. As of right meow I don't think this is something Twitter/X will undo because I doubt they perceive it as a "bug" to begin with, so I figured it was worth the time to put together these instructions.

Adapted from Reddit information [here](https://www.reddit.com/r/Twitter/comments/1c0wi1x/workaround_for_sensitive_media/) and [here](https://www.reddit.com/r/Twitter/comments/1c0wi1x/workaround_for_sensitive_media/kz1n8za/). All I did was rewrite their instructions to be easier.
