# Holiday Card - An Intro to CSS Animations

These are the project files for a simple holiday card that you can share with friends and family. The design is very simple, so we'll be adding some animations to make things more interesting.

Check out a preview of what we'll be making here: [HWI Holiday Card](https://hello-world-initiative.github.io/code-along-december-2019/). Note that this page has not been optimized for mobile, so we recommend viewing it on a larger screen.

## Getting started

If you have `git` installed, you can clone this project using one of the URLs above:

```
git clone https://github.com/hello-world-initiative/code-along-december-2019.git

- or -

git clone git@github.com:hello-world-initiative/code-along-december-2019.git    # if you have SSH keys
```

If you don't have `git` installed, if you're using Windows and don't have `git-bash`, or you're not comfortable with `git` yet, you can download the files by clicking **Clone or Download** above, then choosing **Download ZIP**. Make sure you unzip the archive you download - your computer will probably have software that will let you do this.

There are two CSS files we'll be using: `animations-starter.css` and `styles-final.css` in the CSS folder.

To illustrate how the site will look when it's done, I'm linking the final version in the HTML. To see the "finished" site, you can find the `index.html` file in your file browser (explorer on Windows, finder on Mac) and open it in your web browser.

Once you have a look around, go back to your text editor, open up the HTML file, and change this line:

```
<link rel="stylesheet" href="css/animations-final.css" />
```

Change the name of the CSS file from `animations-final.css` to `animations-starter.css`. If you refresh the page in your browser, you'll notice that nothing moves and some of the styles are gone.

## CSS Animation Basics

The first thing to understand is that CSS animations are just styles that change over time. There's nothing "special" about animation - if you can write some basic CSS, you can make your pages move without much extra work.

For example, to animate a ball being thrown, you would need to change the position-related properties on whatever element you're using to represent a ball. To follow along with that same example, the ball might start at `left: 0;` (all the way to the left) and end at `left: 100%;` (all the way to the right).

Why `left: 100%` and not `right: 0`? A key point to know is that when you're animating, you can only change the values of the same property. To again use the same example, you might think of the animation as a change in the ball's position, but what causes the animation is a change in the value of a single property - `left`.

Animations aren't just about moving things though. You can also use animations to change colors, fade elements in and out of view, and even add some neat interactive aspects to your site by using state selectors like `:hover`.

Aside from basic CSS knowledge and a bit of creativity, all you need to know to start animating is two simple concepts: keyframes, and a few `animation` properties. I'll give a brief overview below.

### Keyframes

If you're wondering what the `@keyframes` sections in this style sheet are, I don't blame you! The syntax looks a bit weird for CSS, but it's not too complicated when you get the hang of it. To start, you can think of the keyframes as the basic "rules" for your animation.

Keyframes is a way to define the different changes your element goes through over time in an animation. If you know a little about animation, you probably already know what "frames" are - they're the individual images that, when changed slightly and put together, give the illusion of motion (or other change). In CSS, keyframes are just that - the _key_ (most significant) _frames_ in your animation.

There are two ways to use keyframes. The first is this:

```
@keyframes yourAnimationName {
  from {
    property: value;
  }

  to {
    property: new value;
  }
}
```

The `@keyframes` keyword declares a new set of keyframes, and `yourAnimationName` is the name of your animation. The name can be anything you like - it's just a way to reference your animation later on when you want to use it.

When this animation executes on an element, that element starts with the styles in the `from` block and ends with the styles in the `to` block. Depending on the values in your animation properties (more on this later), it can transition from the beginning to end state in a number of ways.

The second way allows a bit more control over how the animation plays out:

```
@keyframes yourAnimationName {
  0% {
    property: value;
  }

  50% {
    property: new value;
  }

  ...

  100% {
    property: another value;
  }
}
```

Using this method, you can set various intermediate states on your element as the animation progresses. The animation properties still have an effect, but this allows you to apply more different styles as it goes. Each block represents the state of your element at a certain percentage of the animation's total progress. For example, if you're creating an animation that will last 10 seconds (we'll talk more about how to set this), then you can have a certain style take effect after 3 seconds by using a `30%` block.

For example, if you wanted to move an element from one side of the screen to the other in a straight line, the first method would likely make your life much simpler. However, if you wanted to change the color of text from red to green to blue to yellow (and any other colors you might want), the second method would be the way to achieve this effect.

### Animation Properties

To animate an element, you can use the 'animation' property, which is a shorthand way to animate everything with only one line. Since we're learning (and to make more interesting effects), we won't use the shortcut. Instead, we'll use the following longhand properties:

- **animation-name**: The name of the animation you want to use for the element - the name is what you set in your keyframes declaration
- **animation-duration**: How long the animation takes to complete one cycle (in seconds)
- **animation-timing-function**: The [timing function](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function) the animation uses as it progresses
- **animation-delay**: The amount of time that must pass before the animation starts
- **animation-iteration-count**: How many times the animation will complete
- **animation-direction**: The "direction" in which the animation plays, i.e. start to finish (normal), or in reverse (reverse)
- **animation-fill-mode**: The fill mode allows you to set whether or not the styles in an animation remain after the animation finishes its cycle

There are other possible properties that we won't be using, but you can read about them [here](https://developer.mozilla.org/en-US/docs/Web/CSS/animation).
