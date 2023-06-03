+++
author = "joy"
title = "AI automates the boring code"
date = "2023-06-03"
description = "My thoughts on using Copilot at work"
tags = [
    "engineering"
]
draft = false
+++

Recently, I was thinking about how people learn how to code. *Automate the Boring Stuff with Python* is a book frequently recommended to people learning Python. It teaches you the basics of the language and how to do practical tasks. One of the first practical uses I had for writing Python scripts was scraping the used phone marketplace Swappa and emailing myself whenever a new listing was posted.

Here are two true statements about that task.

* It's precisely the kind of task *Automate the Boring Stuff with Python* teaches you to do.
* Copilot can automate 70% of it. 

## AI automates the boring code

In my day job as a full-stack engineer, I would say Copilot only writes 10% of the code I write, and the code it automates is what I call *boring code*. Here are some examples of boring code that Copilot can write.

* The sleep() function in JavaScript
* Import statements for generated types, API wrapper, and UI library [0]
* The boilerplate code to raise an error
* Ruby case statement with conditions already filled out given a [typed enum](https://sorbet.org/docs/tenum)
* Syntax things: for loops, if statements, function definitions
* [Standard library](https://ruby-doc.org/stdlib-2.7.1/) functions, especially useful since I work with dates and times a lot

**Here's another claim: Software engineers don't enjoy writing boring code.**

I recently saw a thread on Twitter claiming an engineer with many years of experience refused to use Copilot because he "really enjoys writing code." There're lots of strange threads on AI Twitter, so I shouldn't be surprised. In any case, I find it hard to believe someone really enjoys looking up syntax and writing basic for loops.

The engineers I know enjoy software engineering because it's about solving problems. Writing code is a way to solve problems.

Solving problems is the fun part.

## An example problem

Here is a real problem anyone who works for a Big Company can relate to that AI cannot solve [1]. Let's say you're doing an internal data model migration.

To give a real example, let's say you're a clothing company that started out selling shirts. Your shirt product is represented in code as the `Shirt` model. The `Shirt` model has properties on it, like `is_short_sleeve`, `is_long_sleeve`, `is_cropped`, and `discount_rate` [2]. 

However, now you want to expand your business, so you decide to clean up this code. You create a new model `Product` for the next phase of your business, and you need to write a migration.

* **Software solves business problems.** You're in this situation because your code made assumptions about the business that no longer hold true. You're remedying the situation to enable the business to grow.
* **AI can't write the migration by itself**. The fields on the `Shirt` model don't map 1:1 with the `Product` model. You likely want to represent `is_short_sleeve` and `is_long_sleeve` differently on the new model. You might not want `discount_rate` on the `Product` itself; you could have a separate `Promotion` model that defines the products included in the promotion.

## AI *helps* solve problems

In the example above, thinking about how you're going to represent products for the next phase of your business, and how you're going to migrate from `Shirt` to `Product` is the heavy lifting. You might bounce ideas off ChatGPT, but ultimately it's up to you to determine the right solution. It's your job to make the decision.

Here's a list of tasks I haven't automated at my job.

* **Translating Figma designs to data flow**. Often the designs are complex, involving many moving parts and separate API calls. If it were obvious where the data should be fetched, frontend would be much simpler. Instead, you often end up with very complex frontend code because its not componentized properly.
* **Technical design**. There's never one right answer. For any given problem, there might be 3 solutions I come up with, all with different pros and cons.
* **Making decisions**. Once you've drafted the options, you have to pick one.
* **Code review**. I can only point out potential bugs because I understand enough about the data models and interactions among them. Most things caught in code review aren't syntax issues; the build system would have already caught syntax issues early.
* **Reasoning about the system**. Software engineers all know how to write code, so writing code is never the hard part. The hard part is knowing what code to write. Reasoning about all the ways the system can break is the challenge.

There are more, but these are the ones that immediately come to mind. My job is mostly made up of these tasks that I can't automate. I'm not opposed to using AI to help me automate them, but I've found so far the tools I've used aren't sufficient for them. One way of interpreting this blog post is that AI is far from automating the job of a software engineer. Another way is seeing it as a list of problems that would be exciting to solve.

---

[0] At the Big Company I work for, there're very specific ways of doing certain things, but Copilot can more or less infer based on the files I 
have open in my editor, even though we're not using public libraries.

[1] If you don't find it relatable, I'm surprised and also curious to hear about your experience.

[2] You might ask, how did it make sense at the time to keep adding these properties to the model? There are a couple plausible explanations. 1) Your shirt company was trying to move fast, and you ended up in this situation. 2) It was your developer's first project, and they weren't experienced enough to know better. In any case, it doesn't help to dwell on why someone else wrote the code a certain way but focus on what you're gonna do about and prevent it from happening in the future.