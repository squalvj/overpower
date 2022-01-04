---
title: "Eloquent of Emotion in Writing"
date: 2022-01-04T17:19:07+07:00
description: 'Clean code is not a rule, but let it guide you and thy shall show the path to better quality.'
image: images/coding.jpg
draft: false
---

# Thinking Fast and Slow

I've read the book by Daniel Kahneman "Thinking Fast and Slow" it is quite extraordinary book. It basically tell how human brain works, and it also mention how our brain works.
So the author grouping our way to think into 2 system, **System 1** and **System 2**.

## System 1
So System 1 is the fastest system from our brain that capable to determine or judge outside the box, for example when you see creature in the sky that flap their wing, well System 1 tells us that is a bird, when we see such a simple calculation "1 + 1 = ?" well, even when you read this, you unintentional calculate that word in your brain resulting "2" of course without you even thinking anymore, so system 1 is great and it fast, but actually system 1 has a flaw which is prone to wrong, because when we faced something uncertain, system 1 always jump and say "hey come on she is going to leave you alone" and it affect our emotion, worry not, there is a saviour from this which is **System 2**.

## System 2

**System 2** is the thinker one, it has precision judgement, has high accuracy in terms of judging something, but it is lazy and require more effort than **System 1**. Like when you driving, calculating "654 x 889" and other operation that require your focus. 
**System 2** is great but sometimes our brain is too lazy to use the **System 2** because require more focus and gotta pause and questioning **System 1** decision, but we can actually train it to be more optimal by always passing our **System 1** judgement to **System 2**.

Yeah basically just how our brain works whatsoever.

In my days of a Javascript coder, i've seen myself and many people actually using their System 1 to write a code.
Writing is beautiful, especially write a code, it require emotion you kno.. gotta express your best feeling into it, apart from those System 1 or System 2, it also require emotion to write a good one.

# Code Quality
So what is code quality ? regardless all those unit testing you wrote, all those fancy library you integrate, all those advance looping using "while" you wrote, For me.. Code quality is simply as "You write a code that makes other people understand" thats it, im not asking any other else, i always put my lowest expectation on any project in terms on Writing style IMHO.
Writing code require emotion believe me or not, when you angry and write code, probably your writing is not as good as when you feel good.

I've seen something like this

```javascript
  function checkIsShittyAndroid(i){
    return collectionShitty.includes(i)
  }
```

Well i dont need to explain whats wrong with this apart the name of the function. Naming *variable*, *function* have to be short and meaningful so other people can reuse the function and grasp what the purpose of the function or variable, and what is "i" mean ? index ? id ?

As a Professional Programmer, we have ethic and responsible to deliver a good quality code regardless of how fucked our emotion is, lose the bad vibe while writing is a must.

# The Shapeshifter
```javascript
let product

if (props.id) {
  product = props.product
} else {
  product = null
}
// ...
// ...
//next 50 line of code
product = foo
return product
```
I known Javasript for more than 5 years frontend or node js, javascript has *Garbage Collector* which you dont need to manage how the memory allocation things work, everytime interpreted engine run and see closing scope in 1 *lexical scope*, all variable memory address inside it will be released and collected by the *Garbage Collector*, which is why mutation is a great **Sin** in javascript, always avoid mutation if possible, it is hard to read when a variable get mutated because we dont know where the variable might be reassign AGAIN!, and also stop using ```else``` and give the default value when first initiated, but as a Professional developer, we dont need to yell at this particular person whom wrote something like this, lets try to make it more readable

```javascript
let product = null //if it really necessary to mutate

if (props.id)
  product = props.product

if (bar)
  product = foo
  
return product
```

Let other people read beautiful code that you wrote full of passion and emotion, no need the else to reduce complexity.

# Passing the Ball
```javascript
  // As per Bob said last week
  if (props.id && foo)
    product = bar
```
Sometimes other person weren't able to understand our stand point, no matter how many times you argue it just won't happen, so you put your emotion into the code to tell how angry you are about their decision, and this happen.

Taking ownership of the project is a must have attitude, and comment on code should explain about the logic itself, not throwing your responsibility to someone else, i get it sometimes it is tough when dealing with code & other person at the same time but in this case, communication is the key of tackle this kind of obstacle, asking is the best shortcut you could ever had if you dont know, if the person you ask dont know the answer, well there is more fish in the sea, you got me right (goooogle?).

# The Unwanted Child
```javascript
  // if (props.me === null)
  //   product = null
  // const baz = 123

  if (foo === bar)
    product = foobar

  return product
```

The commented line, i know when we feel uncertain, we just comment some snippets to use is later, and just re-comment it.. easy!.

But something like this is always get carried over in the future and totally everyone forgot about it to even re-comment or remove it which cause your code decorated by unpleasent nonsense comment of some code. It takes confidence to write good one, remove all unecessary variable, function or even nonsense comment from your code, so the reader will not raise a question "why they left here ?", embrace the confidence to discard something like this put your emotion to tell the machine what you really want, dont be uncertain, you use version control right ? let the git gud you if you want to see previous version

# The Mocking Bird
```
git commit -m "update"

or

git commit -m "remove stupid auth login"
```

I've seen this ugly emotion many times, meaningless commit message or even trash talk other people logic.

We might see so many unacceptable logic that has been written on **Legacy** project, and we might think like "Why this person wrote this way", so dumb. 

Actually in Software Development, this things happen, tight timeline and technical difficulties can cause a person to ignore Beauty of Code, this is the thing that we should keep in mind because we weren't stand in this particular person shoe.

There is no need to pile on something like this, you can just take it and forget it.. or even better you tell them if its wrong to write a shitty logic.

Always straight-forward to write commit message, because when it get squashed you can see the beauty of it and very easy to cherry pick or revert on some particular commit (you would thank me later when you have to revert on production code).

## Last remark
Emotion can affect how a person write a code, even when i look my old code, and realize how awful Programmer i am, but its never too late to patch our crap attitude to be better person, since our emotion is always pull the trigger, your logic brain could make a better communication before our emotion pull it.

Remember:
> Clean code is not a rule, but let it guide you and thy shall show the path to better quality.