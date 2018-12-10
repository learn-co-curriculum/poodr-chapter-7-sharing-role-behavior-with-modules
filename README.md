# POODR - Chapter 7: Sharing Role Behavior with Modules

"This chapter explores an alternative that uses the techniques of inheritance to share a role." - pg 141

## 7.1 Understanding Roles

They tend to come in pairs, like `Preparer` and `Prepareable`
- Where are some places that we use this in ironboard?

Objectes acting as the `Preparer` is only calling the methods on `Prepareable`, but doesn't need any other specific code?

We again seem to be looking at code that would need to check class (`Bicycle`, `Mechanic`, `Vehicle`). This is a red flag that all of these classes instead could implemetn a similar method (in this case, `lead_days`) - Letting Objects Speak for Themselves.

Writing a `Schedule` module and including it in `Schedualable` classes allows us to give the same behaviour (duck typing?) to multiple classes.

`Scheduable` is using the template patern so that each individual scheduable item can override it's module methods (`lead_days`)

Deciding between modules and inheritence:
"**This _is-a_ versus _behaves-like-a_** difference definitely matters, and each choice has distinct consequences. However, the coding techniques for these two things are very similar and this similarity exists because both techniques rely on automatic message delegation." - pg 153

Weird? "...the methods of the last included module are encountered first in the lookup path" - pg 156

Warning! "You can write code that is impossible to understand, debug, or extend." - pg 158 Using modules can be powerful, but with great power comes great responsibility (yoda probably said this). 

## 7.2 Writing Inherirable Code

Recognizing antipaterns:
- Code that switches on things like `type` or `category`
- Sending objects checks to determine what message to send

Code in a superclass or modules should apply to _all_ subclasses.

Liskove Substitution Principle - Honoring the contract of methods, inputs, and return values. Methods from a superclass may be overwritten, but the input types and output types should remain the same. 

Avoid using `super` in favour of hook messages

Avoid deep hierarchies

<p class='util--hide'>View <a href='https://learn.co/lessons/poodr-chapter-7-sharing-role-behavior-with-modules'>POODR Chapter 7: Sharing Role Behavior with Modules</a> on Learn.co and start learning to code for free.</p>
