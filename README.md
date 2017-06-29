The new Macbook Pros (from 2016) support a wider color gamut. There's this weird issue though:

![](http://dropbox.jeremyricketts.com.s3.amazonaws.com/chrome_desatureate.png)

You can see that Chrome is accurately representing the CSS hex value #FF8252. [Sip](http://sipapp.io/) confirms it. Firefox shows the same thing – an accurate rendering of color in the web browser.

## Issue 1: The colors look terrible.

You can tell on websites with solid, bright colors that something is wrong. I noticed as soon as I installed Chrome on my new machine and others have commented as well (usually saying something like "Has the website always been that bright?" or "Did we change colors?" It's most visible on the red side of the spectrum. It's not specific to the monitor either – the issue manifests on the laptop screen as well as the LG 5k monitor now sold in Apple stores.

## Issue 2: Safari is rendering a different, more muted color.

Clearly, Apple agrees that the colors are garish because Safari is not rendering the colors accurately (as shown above). It's rendering more palatable, muted tones we're used to seeing for those colors.

## A workaround (for Chrome at least):

Neither myself or the designers on staff have found a solution for this. We've tried munging with the display calibration, but that doesn't get us very far since this issue of oversaturated colors is really only visible in Chrome and Firefox. We don't want to change the monitor profile and dull down the rest of the operating system (that would screw up work in Photoshop/Lightroom/etc).

Until there's a more permanent solution, I've written a teeny Chrome plugin to desaturate and then lighten the colors to more closely match what Safari is rendering. It's not a perfect match and there's no way to know what exactly MacOS is doing to help Safari render colors that don't make our eyes bleed.

## Examples of results:

![](http://dropbox.jeremyricketts.com.s3.amazonaws.com/chrome_desatureate_sample1.png)

![](http://dropbox.jeremyricketts.com.s3.amazonaws.com/chrome_desatureate_sample2.png)

![](http://dropbox.jeremyricketts.com.s3.amazonaws.com/chrome_desatureate_sample3.png)

## Installation:

1. Clone this repo.
2. Open the Extensions view in Chrome. ([chrome://extensions](chrome://extensions))
3. Enable Developer Mode.
4. Load unpacked extension...
5. Select the root folder
6. Once installed, make sure the plugin is enabled and allowed to run in incognito mode.

![](http://dropbox.jeremyricketts.com.s3.amazonaws.com/steps.png)

## Modification:

Look, it's a CSS file. It loads one line of CSS for any web page you visit in Chrome:

`filter: grayscale(15%);`

That's what I've found works best, but feel free to experiment.
