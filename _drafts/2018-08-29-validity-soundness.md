---
title: Validity & Soundness
published: False # True / False

categories:
  - PHIL103
tags:
  - PHIL103
  - Philosophy
  - Logic
  - Semester 1
  - Lecture Notes

# sidebar: # note: optional, but should include for class notes posts
#  title: # title of nav bar that shows in post
#  nav: # references specific sidebar laid out in _data/navigation.yml
---
This lecture elaborated on the issue of validity, and introduced the concept of soundness. It also introduced sentential logical form, or reducing statements to variable form (i.e. "p" or "q").

## Validity

Remember: validity is a property of arguments - it has nothing to do with standard English definition.

For example, consider this argument.

__Premise 1__: The sun rose today.  
__Premise 2__: The sun rose yesterday.  
__Premise 3 - 1 billion__: The sun has risen every day for the past billion years.  
__Conclusion__: The sun will rise tomorrow.  

This argument is invalid, because there it is conceivable that there could exist a world where the premises are true while the conclusion is not. It doesn't matter that the conclusion is very likely... it is possible that it is not true (while the premises are true), therefore the whole argument is invalid (no matter how convincing it may seem).

Good arguments are valid, but validity is not enough for an argument to be good. You should also look at its soundness.

### True/False Table

| Premises | Conclusion | Valid? |
|--------|-------|--------|
| True   | True   | Yes   |
| True   | False   | __NO__   |
|-----------------------------|
| False   | True   | Yes   |
| False   | False   | Yes   |


## Soundness

An argument is sound if (1) it is valid and (2) it has true premises.
- This means that *sound arguments have true conclusions*. Valid arguments can still have false conclusions, if the premises are false.
- BUT, just because an argument has true premises and true conclusions, doesn't mean it is sound. It has to be a valid argument to be considered sound.

Put another way,

Argument A is sound if and only if both:
 - A is valid
 - All of A’s premises are actually true

However, even sound arguments may not be good arguments. For example, this is a perfectly sound argument (in which the premise entails the conclusion):

__Premise__: Illinois is in the US.  
__Conclusion__: Illinois is in the US.

Valid? Yes. True premises & conclusions? Yes. Sound? Yes.   
Good? ... not so much.

Also of note... pure logicians don't really care if the premises are true or not. So soundness is probably not going to be very important during this course. Truth is simply a property, not a fact.

### The importance of being explicit

In order for an argument to be considered valid by strict logicians, you need to define your terms.

For example,

__Premise__: John is a bachelor.  
__Conclusion__: John is unmarried.

This seems true, but is it valid? Logicians say no. You need to add one more premise to the argument:

__Premise__: John is a bachelor.  
*__Premise__: All bachelors are unmarried.*  
__Conclusion__: John is unmarried.  

## Logical (Sentential) Form

The sentential form of an argument is obtained by replacing each basic (atomic) sentence in the argument with a single (lower case) letter.
	- Basic sentences are sentences that don’t have any other sentence as a part.
	- Look for these words to indicate that the sentence is not atomic: and, but, not, either, or, nor
	- Sentences that are not basic/atomic are called complex/compound/molecular sentences.

The example below is a famous argument first made by Theophrastus (~300 BC), and is called __modus ponens__, "mode that affirms by affirming."
{: .notice--info}

For example:  
  (1f) p  
       If p, then q.  
       :. q.  

In this argument, p and q can stand for any declarative statement.

### Practicing sentential form

(1)  If Tom is in his Freemont home, then he’s in California.
	   Tom is in California.
	   :.  Tom is in his Freemont home.

…

F: Tom is in his Freemont home
C: Tom is in California.

…

(1)	 If F then C
	   C
	   :. F
…

This argument is not valid (and therefore not sound).

### Weirdly valid arguments

(1) 	p.
	    :. q or not q

(1) is valid simply because “q or not q” is a logical truth. It’s impossible for the premise to be true and the conclusion false, since the conclusion is always true.

(2)	p and not p.
	  :. q

(2) is valid because “p and not p” is a logical falsehood. So it’s impossible that both (a) “p and not p” is true and (b) q is false. That’s because (a) is impossible.
