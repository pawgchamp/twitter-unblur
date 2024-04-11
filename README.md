# twitter-unblur
Instructions for how to remove the "Warning: sensitive content" warnings on X / Twitter.

## Prerequisites 
1. Desktop version of X / Twitter
2. Chrome or Chromium (Edge, Opera/GX, Brave, Vivaldi, etc.) browser, _not_ Firefox
3. Recommend [uBlock Origin](https://github.com/gorhill/uBlock)
   
## How to
1. Install [X / Twitter Feature Flags](https://chromewebstore.google.com/detail/x-twitter-feature-flags/phioeneleonlckednejcmajbkmhhiepm), should work like this even if you're not using Chrome in particular
2. Open Twitter, press "Features" (below "Profile" and above "More") in the left menu
3. Using the search box at the top, find the following and **un-check** the boxes to disable:
    - `media_visibility_treatments_blurred_media_interstitial_enabled`
    - `sensitive_tweet_warnings_enabled`
4. Press the Save Changes button at the bottom of the overlay
5. Refresh

This fixed it for my timeline, replies, and related tweets. To fix the Media tab being blurred too:

1. Open uBlock Origin's settings page (in Chrome: Extensions button > uBlock Origin > ⚙ icon/"settings")
2. Select My filters and add the following filter rules:
    ````
    twitter.com##.r-yfv4eo:style(filter: blur(0px) !important;)
    twitter.com##.r-drfeu3:style(display: none !important;)
    twitter.com##.r-1cmwbt1.r-1777fci:style(display: none !important;)
    ````
3. Press the Apply changes button at the top. You may need to check "Enable my custom filters" if it's not already
4. Refresh; you're done

> **Optional:** If you'd want to hide the Filters button that's been added by the extension, do that by adding the following filter in uBlock Origin (under the aforementioned):
> ````
> twitter.com##.featuresBtnContainer
> ````

## Alternatives
- [Twitter用 センシティブ画像大好き君](https://chromewebstore.google.com/detail/twitter%E7%94%A8-%E3%82%BB%E3%83%B3%E3%82%B7%E3%83%86%E3%82%A3%E3%83%96%E7%94%BB%E5%83%8F%E5%A4%A7%E5%A5%BD%E3%81%8D%E5%90%9B/gmmdlghnjobnnkochmhgbmdaoncibakj) - works but doesn't allow videos to autoplay
- [unBlurd.](https://chromewebstore.google.com/detail/unblurd-by-wumbl3/gifejdknamachffbkgblclhpojdcjodk) - has autoplay but didn't work reliably
- [Twitter hide content warning crap](https://greasyfork.org/en/scripts/437359-twitter-hide-content-warning-crap) - worked for my timeline but not Media tab
  
## Information
The above is only what I've found to work to work around the issue. I'll keep this up to date if this fix no longer works and/or I find a better solution. I don't anticipate they'll will undo this change, so it's up to us to find workarounds.

Credit: [Here](https://www.reddit.com/r/Twitter/comments/1c0wi1x/workaround_for_sensitive_media/) for the feature flags, and [here](https://www.reddit.com/r/Twitter/comments/1c0wi1x/workaround_for_sensitive_media/kz1n8za/) for the filter rules. I used different filter rules that worked for me.
