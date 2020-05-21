JavaScript Rock Dodger
---
## My Features

After completing the final lab, I decided to continue working on it to add more
features. As a basic game it was...lacking. I wanted to addmore features that a
game like this would have. Plus, I wanted to keep tinkering and learning more JavaScript!

_Successfully implemented features:_
1. Rocks Dodged Counter: Displays the running total number of rocks successfully
   dodged. Total is also included in the final "You Lose!"
   alert at the end of the game (grammatically correct when only 1 rock was dodged).
2. Change Dodger Color: On clicking the dodger and pressing the up- or down-arrow
   keys, the dodger cycles through 10 colors, including the tricky "black"
   option. Clicking or pressing the up-arrow cycles forward through the colors,
   while pressing the down-arrow cycles the opposite direction through the list.

_In-progress features:_
--Increase Difficulty: Currently, the falling speeds of the rocks rocks increases
  automatically every 20 seconds. I'd also like the frequency of rock production
  to increase to more than 1 rock/second (either 2+ rocks at the same time, or
  more frequently, or both). Or maybe instead?

_Future features:_
1. Powerups: Every 30 seconds, a Powerup falls in addition to a rock. Powerups
   will be represented by different icons. Not all will be helpful!
     a) Slowdown: reduce speed/frequency of rocks
     b) Speedup: increase speed/frequency of rocks
     c) Dodger size: reduce or increase size of the dodger
     d) Mario Star: invicible dodger for 10 seconds
2. High Score List: Displayed after you lose, shows recent games in order. Maybe
   even asks for your initials/name, old-school arcade style? (Save even if you
   reload the page?)
3. Animated Backdrop: Before initial press of "Start", show an animation of the
   game being played in the background (rocks falling, dodger moving).

## Objectives

1. Use JavaScript to build a rock-dodging game
2. Explain how `window.requestAnimationFrame()` is used to animate movement on a page
3. Explain how to use `setInterval()`
4. Show off your JavaScript know-how

## Instructions

You did it — you've made it to the end of the introductory JavaScript
curriculum. You've learned how to write JavaScript and how to use JavaScript to
manipulate the DOM. Now, only this lab stands between you and ~~freedom~~ the
end of this course!

So that we don't catch you off-guard, know that this project is meant to be
difficult. We're really testing the limits of what we've learned so far. But
know that we've solved the lab using only things that we've taught — well,
mostly. There are two things (which we've partially implemented for you) that
you should know about.

#### `window.requestAnimationFrame()`

This function tells the browser that we want to animate some change on the page.
We'll use it in this lab for animating the movement of rocks and the dodger.

We can use [`window.requestAnimationFrame()`][requestAnimation] by passing it a
callback that contains our animation:

``` javascript
function move(el) {
  var top = 0

  function step() {
    el.style.top = `${top += 2}px`

    if (top < 200) {
      window.requestAnimationFrame(step)
    }
  }

  window.requestAnimationFrame(step)
}
```

If we call `move(el)` with a valid DOM element, `window.requestAnimationFrame()`
will be called with the function `step`, which moves the `el` down the page in
two-pixel increments until it's been moved 200 pixels. Pretty easy, right?

(Note that we can pass `step` to `window.requestAnimationFrame()` _inside_ of
`step`. This is a nifty feature of JavaScript (and other languages) called
[_recursion_](https://en.wikipedia.org/wiki/Recursion_(computer_science)). Don't
worry if this concept makes your head spin a bit — that feeling is normal. For
now, know that we can use `window.requestAnimationFrame()` as demonstrated
above.)

#### `setInterval()`

[`setInterval()`][setInterval]
takes two arguments: a callback, and an interval in milliseconds. We can use it
like so:

``` javascript
function sayHello() {
  console.log('hello')
}

const myInterval = setInterval(sayHello, 1000)
```

The above will print `'hello'` to console once every second.

Note that `setInterval()` returns a reference to the interval. We can stop the
interval from executing by calling `clearInterval(myInterval)`.

#### Getting Started

Open up `index.html` in your browser. You should see a black 400-by-400px box
with a white square at the bottom. That square is the dodger — it can only move
left and right.

Well, it _should_ be able to move only left and right — we'll need to implement
that functionality!

Now open `index.js`. You'll see that we've defined a few functions for you, but
we've left much of the file blank.

We've left enough comments to get you started, though, and we've defined all of
the HTML and CSS that you'll need so that you can just focus on the JavaScript!

Remember to reload the page after updating and saving the file. You've got this!

Good luck!

## Resources

- [window.requestAnimationFrame()](https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame)
- [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers/setInterval)

<p class='util--hide'>View <a href='https://learn.co/lessons/javascript-rock-dodger'>Rock Dodger</a> on Learn.co and start learning to code for free.</p>

[requestAnimation]: https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame
[setInterval]: https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers/setInterval
