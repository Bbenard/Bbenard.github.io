---
layout: post
title: Code simplicity
---
#Code Simplicity

Essentially, I know exactly how generic my code needs to be by noticing that I’m tempted to cut and paste some code, and then instead of cutting and pasting it, designing a generic solution that meets just those two specific needs. I do this as soon as I’m tempted to have two implementations of something.

For example, let’s say I was designing an audio decoder, and at first I only supported WAV files. Then I wanted to add an MP3 parser to the code. There would definitely be common parts to the WAV and MP3 parsing code, and instead of copying and pasting any of it, I would immediately make a superclass or utility library that did only what I needed for those two implementations.

The key aspect of this is that I did it right away—I didn’t allow there to be two competing implementations; I immediately made one generic solution. The next important aspect of this is that I didn’t make it too generic—the solution only supports WAV and MP3 and doesn’t expect other formats in any way.

Another part of this rule is that a developer should ideally never have to modify one part of the code in a similar or identical way to how they just modified a different part of it. They should not have to “remember” to update Class A when they update Class B. They should not have to know that if Constant X changes, you have to update File Y. In other words, it’s not just two implementations that are bad, but also two locations. It isn’t always possible to implement systems this way, but it’s something to strive for.

If you find yourself in a situation where you have to have two locations for something, make sure that the system fails loudly and visibly when they are not “in sync.” Compilation should fail, a test that always gets run should fail, etc. It should be impossible to let them get out of sync.

And of course, the simplest part of this rule is the classic “Don’t Repeat Yourself” principle—don’t have two constants that represent the same exact thing, don’t have two functions that do the same exact thing, etc.

There are likely other ways that this rule applies. The general idea is that when you want to have two implementations of a single concept, you should somehow make that into a single implementation instead.

When refactoring, this rule helps find things that could be improved and gives some guidance on how to go about it. When you see duplicate logic in the system, you should attempt to combine those two locations into one. Then if there is another location, combine that one into the new generic system, and proceed in that manner. That is, if there are many different implementations that need to be combined into one, you can do incremental refactoring by combining two implementations at a time, as long as combining them does actually make the system simpler (easier to understand and maintain). Sometimes you have to figure out the best order in which to combine them to make this most efficient, but if you can’t figure that out, don’t worry about it—just combine two at a time and usually you’ll wind up with a single good solution to all the problems.

It’s also important not to combine things when they shouldn’t be combined. There are times when combining two implementations into one would cause more complexity for the system as a whole or violate the Single Responsibility Principle. For example, if your system’s representation of a Car and a Person have some slightly similar code, don’t solve this “problem” by combining them into a single CarPerson class. That’s not likely to decrease complexity, because a CarPerson is actually two different things and should be represented by two separate classes.

This isn’t a hard and fast law of the universe—it’s a more of a strong guideline that I use for making judgments about design as I develop incrementally. However, it’s quite useful in refactoring a legacy system, developing a new system, and just generally improving code simplicity.

