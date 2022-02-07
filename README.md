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

- Step One: Decide what sort of container to use. I settled on grid for the main wrapper, as the cards sit flush with each other, so the space distributing benefits of flex aren't
so useful.

Grid also makes it easy to keep the items
consistent in length and I have a feeling grid will make the mobile design easier too.

- Step Two: Define some card divs and style them. I decided
this would be a good project to use Sass on, as although the
stylesheet will be relatively simple, nesting will make life easier with switching colours etc.

Fetched my fonts from Google using @import in the stylesheet rather than a link in the header. Logic being that this design would be used as a single page section on an existing website, so it'd be more faff in practice to have to add fonts to the head tag of each page it's used on.

*Added later: I decided to make the card items themselves flex containers, as I thought flex would be better due to varying amounts of text etc. Actually I probably should have stuck to grid.*

- Step Three: The cards are appearing on screen in the right
colours, success! But before I built any more elements, I checked against the original design and noticed it was centred on a light gray background. My design was the full width of the screen so I created a 100% parent container, made it gray and used flex just to centre everything. I set the card-wrapper to 80% width and height.

Infuriatingly rounding the corners of the card-wrapper container took ages - they stubbornly stayed square until I tried setting overflow: hidden and learned that those square corners belonged to the children, not the parent!

- Step Four: Added the icons and buttons to the cards. Realised
that my headerColor variable is poorly named, because I'm using it for my buttons too, but that's not a massive issue as this is a personal challenge, but will bear in mind for future.

Started to realise the problem I might have with using flex - the buttons aren't lining up with each other because their vertical positioning depends on the amount of text in each card, which of course varies.

I could go back and change the cards to grid at this point, but I'm going to try and persevere with flex. At the back of my mind I know I've had a similar problem before which I solved with the use of an empty div to maintain the spacing, so I don't think I'm painting myself into a corner.

- Step Five: Sizing. Tweaking the element sizing before I get stuck into the alignment issue as I might need to use rems as a spacing unit if I get stuck. Style guide says 15px so I set it to that and nothing changes.

Weird. Then I realised I cancelled sass --watch while I was committing changes just before, so I recompile the css and turn it back on. Immediately messed up a bunch of properties that I've already set using rem, like padding and border radius. Oops.

- Step Six: Trying to fix the button alignment. I realised I needed to keep the titles and icons aligned as well (this is why grid might have been better).

Eventually I found that grouping the content in a 'card-content' container did the trick - because now 'card-content' acts as a single flex item, rather than each element (img, h2, p) acting as separate flex items. space-between forces the now-two elements to the edge of the card (minus padding). No empty divs
required and I'm pretty happy with how it looks!

(Checking the design I notice the cards should have a small amount of drop-shadow, but I didn't like how this looked so I removed it. Sorry designer...)

- Step Seven: part of the challenge is to change the state of the design according to the user's viewport (ie go vertical for mobile).

I didn't want to break my working design, so I started work on my mobile version in a branch.

To make the design mobile first, I put my desktop-specific properties (container width and height, card-wrapper width and height, card grid-row) inside a min-width media query and removed them from the main design. At this point I also decided to use % for the padding rather than rems, so that the card stayed in proportion on more viewports, and remove a little from the top and bottom in mobile and tablet view so the content fitted better. I then tinkered with the width of the mobile design until I was happy with it.

- Step Eight: My hover effects are also going in a media query.  This may seem a bit odd but is there any point adding hover effects to the base design when mobile users can't use them? Better to put them in a media query for desktop users IMO.


### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- [React](https://reactjs.org/) - JS library
- [Next.js](https://nextjs.org/) - React framework
- [Styled Components](https://styled-components.com/) - For styles

**Note: These are just examples. Delete this note and replace the list above with your own choices**

### What I learned

Use this section to recap over some of your major learnings while working through this project. Writing these out and providing code samples of areas you want to highlight is a great way to reinforce your own knowledge.

To see how you can add code snippets, see below:

```html
<h1>Some HTML code I'm proud of</h1>
```
```css
.proud-of-this-css {
  color: papayawhip;
}
```
```js
const proudOfThisFunc = () => {
  console.log('🎉')
}
```

If you want more help with writing markdown, we'd recommend checking out [The Markdown Guide](https://www.markdownguide.org/) to learn more.

**Note: Delete this note and the content within this section and replace with your own learnings.**

### Continued development

Use this section to outline areas that you want to continue focusing on in future projects. These could be concepts you're still not completely comfortable with or techniques you found useful that you want to refine and perfect.

**Note: Delete this note and the content within this section and replace with your own plans for continued development.**

### Useful resources

- [Example resource 1](https://www.example.com) - This helped me for XYZ reason. I really liked this pattern and will use it going forward.
- [Example resource 2](https://www.example.com) - This is an amazing article which helped me finally understand XYZ. I'd recommend it to anyone still learning this concept.

**Note: Delete this note and replace the list above with resources that helped you during the challenge. These could come in handy for anyone viewing your solution or for yourself when you look back on this project in the future.**

## Author

- Website - [Add your name here](https://www.your-site.com)
- Frontend Mentor - [@yourusername](https://www.frontendmentor.io/profile/yourusername)
- Twitter - [@yourusername](https://www.twitter.com/yourusername)

**Note: Delete this note and add/remove/edit lines above based on what links you'd like to share.**

## Acknowledgments

This is where you can give a hat tip to anyone who helped you out on this project. Perhaps you worked in a team or got some inspiration from someone else's solution. This is the perfect place to give them some credit.

**Note: Delete this note and edit this section's content as necessary. If you completed this challenge by yourself, feel free to delete this section entirely.**
