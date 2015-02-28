---
layout: post
title: "The current meta"
description: "The current meta-rules in coding"
category: "programming"
tags: ["meta-coding rules", "software engineering"]
---
{% include JB/setup %}

The meta-coding rules is a set of basic guides how to ease your life when programming and usually changes every 12 months or so. Don't think of this as a universal pill, but as a temporary list of good advices. Here are the five most important:<!-- read more -->

1. Write tests for functions which are easily testable.
2. Avoid "global state" in your code.
3. The more complicated code should rely on the well-tested code.
4. Write modules, which could be re-written later.
5. Use static typed languages or proper static analysis tools for the dynamic typed languages.

Rule #1 is easily done if you follow rule #2. I suppose I have read a few books about functional programming languages (Scala, Elixir) this summer and the concept of ["pure functions"]( http://en.wikipedia.org/wiki/Pure_function) has stuck in my mind. Pure functions don't interact with global state and have very predictable behavior – every time you call such function with Input' you are granted to receive Output' in return. The concept is so simple yet so powerful that you can mask their implementation by expressing those functions as "look-up table" which key is the Input' and the value is Output'.

Rule #3 is for all you lazy software developers out there. This is a bottom-up approach which relies on Rules #1 and #2 being well followed. The "more complicated" functions usually have state or interact with another systems and testing them might require fixtures or mocks. This is in any way much harder and requires more efforts than testing pure functions, but as long as you can build these complex functionality on top of the well tested code blocks you should be good. Well, this is not a replacement for proper integration or functional tests, but it is ok solution for the lazy folks, right?!

Rule #4 is the outcome of revelation I received after almost 10 years of writing code – **your code sucks**. And it will always suck as long as you continue changing it. So instead of building cathedrals, it is much smarter to build small prototypes which could end up in the garbage without hurting anyone's feelings. The key is to be free to re-write them from scratch whenever you feel like they are unbearable anymore. Also, no one will ever tell you to write non-modular code, so you are safe following this rule 😋.

Rule #5 is all about unit tests again. The problem with dynamic typed languages is that one small typo somewhere could break everything. This is why you have to "exercise" your code with tests. I think this shifts the main reason you want to test your code in a very mediocre fields. WTF is this - medieval times? Can't we have a smart spell checker? The static typed languages can liberate you from this burden in return of a little bit more boilerplate (defining your types, etc). Some languages like Scala even have [type inference](http://en.wikipedia.org/wiki/Type_inference) for less boilerplate and non-medieval coding experience.

![JavaScript good parts vs bad parts]({{ site.url }}/assets/images/javascript_good_and_bad_parts.jpg)

I think rule #5 should relate to every person who uses JavaScript since most of that language is "bad parts" and for the next project I will definitely use TypeScript or EcmaScript 6/7 plus EcmaScript 5 transpiler with some smart static analysis tool to check for potential trivial bugs.

**What is your "meta for 2015" (hopefully I will coin this term 😅)?**

