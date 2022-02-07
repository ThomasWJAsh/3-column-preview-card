# Frontend Mentor - 3-column preview card component solution

This is a solution to the [3-column preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/3column-preview-card-component-pH92eAR2-). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

###Step One
Decide what sort of container to use. I settled on grid for the main wrapper, as the cards sit flush with each other, so the space distributing benefits of flex aren't
so useful.

Grid also makes it easy to keep the items
consistent in length and I have a feeling grid will make the mobile design easier too.

###Step Two
Define some card divs and style them. I decided
this would be a good project to use Sass on, as although the
stylesheet will be relatively simple, nesting will make life easier with switching colours etc.

Fetched my fonts from Google using @import in the stylesheet rather than a link in the header. Logic being that this design would be used as a single page section on an existing website, so it'd be more faff in practice to have to add fonts to the head tag of each page it's used on.

*Added later: I decided to make the card items themselves flex containers, as I thought flex would be better due to varying amounts of text etc. Actually I probably should have stuck to grid.*

###Step Three
The cards are appearing on screen in the right colours, success! But before I built any more elements, I checked against the original design and noticed it was centred on a light gray background. My design was the full width of the screen so I created a 100% parent container, made it gray and used flex just to centre everything. I set the card-wrapper to 80% width and height.

Infuriatingly rounding the corners of the card-wrapper container took ages - they stubbornly stayed square until I tried setting overflow: hidden and learned that those square corners belonged to the children, not the parent!

###Step Four
Added the icons and buttons to the cards. Realised that my headerColor variable is poorly named, because I'm using it for my buttons too, but that's not a massive issue as this is a personal challenge, but will bear in mind for future.

Started to realise the problem I might have with using flex - the buttons aren't lining up with each other because their vertical positioning depends on the amount of text in each card, which of course varies.

I could go back and change the cards to grid at this point, but I'm going to try and persevere with flex. At the back of my mind I know I've had a similar problem before which I solved with the use of an empty div to maintain the spacing, so I don't think I'm painting myself into a corner.

###Step Five
Sizing. Tweaking the element sizing before I get stuck into the alignment issue as I might need to use rems as a spacing unit if I get stuck. Style guide says 15px so I set it to that and nothing changes.

Weird. Then I realised I cancelled sass --watch while I was committing changes just before, so I recompile the css and turn it back on. Immediately messed up a bunch of properties that I've already set using rem, like padding and border radius. Oops.

###Step Six
Trying to fix the button alignment. I realised I needed to keep the titles and icons aligned as well (this is why grid might have been better).

Eventually I found that grouping the content in a 'card-content' container did the trick - because now 'card-content' acts as a single flex item, rather than each element (img, h2, p) acting as separate flex items. space-between forces the now-two elements to the edge of the card (minus padding). No empty divs
required and I'm pretty happy with how it looks!

(Checking the design I notice the cards should have a small amount of drop-shadow, but I didn't like how this looked so I removed it. Sorry designer...)

###Step Seven
Part of the challenge is to change the state of the design according to the user's viewport (ie go vertical for mobile).

I didn't want to break my working design, so I started work on my mobile version in a branch.

To make the design mobile first, I put my desktop-specific properties (container width and height, card-wrapper width and height, card grid-row) inside a min-width media query and removed them from the main design. At this point I also decided to use % for the padding rather than rems, so that the card stayed in proportion on more viewports, and remove a little from the top and bottom in mobile and tablet view so the content fitted better. I then tinkered with the width of the mobile design until I was happy with it.

###Step Eight
My hover effects are also going in a media query.  This may seem a bit odd but is there any point adding hover effects to the base design when mobile users can't use them? Better to put them in a media query for desktop users IMO.

Had to go back and refactor the my Sass a bit because I needed
to reuse the card colours for the text on hover, so it made more sense to declare them as variables (enabling colour to be changed easily in future.)

And now I think I'm done!

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
