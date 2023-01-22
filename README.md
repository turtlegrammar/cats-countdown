This is a math game I made for a friend based on the British game show 
[8 Out of 10 Cats Does Countdown](https://en.wikipedia.org/wiki/8_Out_of_10_Cats_Does_Countdown).

It's live at https://rachelwantsacat.com/ .

My goal was to implement this game as simply as possible, using a single html file and no frameworks.

Given a set of 6 numbers, like:

4 8 1 3 50 75

and a target number like 660, you need to find an equation that uses each of the above numbers at most once to create the target.

Where it gets interesting is determining the difficulty and novelty of each target. 
I group targets into 5 difficulty levels, and compute the difficulty of a target by looking at how nested the 
simplest equation that creates it is and the number of terms used in the equation.
Difficulty is quadratic with respect to nesting and linear with respect to terms. And I compute the interest-level/novetly of a target by looking
at the number of unique equations that create the target. By unique, I mean that (2 + 1) * 3 is the same as 3 * (1 + 2).

Computing the difficulty and uniqueness requires efficiently deduplicating equations and generating all possible equations given a set of targets.

It was surprisingly complex!
