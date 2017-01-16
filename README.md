# Page Transitions
A jquery component for adding all-sexy-like page transitions to your site's navigation.

The component works by delaying site exit, then adding an ```is-exiting``` class to trigger a css exit transitions/animations. Then on page load, we add an ```is-loading``` class that swaps with an ```is-loaded``` class after a defined duration, which we use to trigger our css entrance transitions/animations.

Your CSS animations or transitions can range from simple fade out and ins, to nifty menu interactions, to sliding panels and preloaders for a poor mans ajax-like effect.



### As Seen On (variations)

- [Formidable](https://formidable.com/)
- [Urban Influence](http://urbaninfluence.com/)
- [Ligaya Scaff](http://ligayascaff.com/)
- [Ink & Volt](https://ink-and-volt.com/)
- [Inrix](http://inrix.com/)
- [Vrge](http://vrge.com/)
- [DNA Seattle](http://dnaseattle.com)


### No Trans

To stop link from triggering the exit animation, use the ```no-trans``` class. You can also add ```no-trans``` to the body to stop all page links from transitioning. 



### ```is-loading``` and ```is-loaded```

Obvioulsy, you could simply use an ```is-loading``` class. However, I've found transitions to perform better than  keyframes, so, I like to use ```is-loading``` to set up transitions, and ```is-loaded``` create their final state. The following example would fade an element in and up:

```scss
//-----------------------------------
// is-loading setup
//-----------------------------------
.is-loading{
  .el{
    opacity: 0;
    transform: translate3d(0,140%,0);
    overflow-y:hidden;
  }
}
//-----------------------------------
// is-loaded final transition
//-----------------------------------
.is-loaded{
  .el{
    opacity: 1;
    transform: translate3d(0,0,0);
    transition: opactiy 0.8s ease, transform 1s ease;
  }
}
```

Additionally, if you instead opt for css keyframe animations, it's best to apply them to the is-loading class so that they are removed after an interval. This prevents some wierd WebKit stuff that can pop up.

### Simple Use

Here's just a super simple fade out and in useage:

```scss
//-----------------------------------
// Fade In and Out Keyframes
//-----------------------------------
@keyframes fade-in {
  0%   { opacity: 0; }
  100% { opacity: 1; }
}
@keyframes fade-in {
  0%   { opacity: 0; }
  100% { opacity: 1; }
}

//-----------------------------------
// is Exiting
//-----------------------------------
.is-exiting{
  animation: fade-out 0.8s ease;
}

//-----------------------------------
// Is Loading
//-----------------------------------
.is-loading{
  animation: fade-in 0.8s ease;
}
```
