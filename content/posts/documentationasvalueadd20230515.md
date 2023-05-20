+++
author = "joy"
title = "Documentation as a value add"
date = "2023-05-15"
description = "Quick thoughts on documentation"
tags = [
    "engineering"
]
draft = false
+++

These are my quick thoughts after writing... a single page of docs. Grain of salt disclaimer.

## Documentation as a project
Documentation is a never-ending project. The first questions you should ask with any project are: Do I need to do it? What value does it add? Applied to documentation, you can ask:
* Does my tool *need* good documentation?
* What value does good documentation add to my tool?

I don't think the answers to these questions are obvious. There are a lot of tools in our lives we use simply because they're the only option, not because they're easy to use. If you're the only provider of internet payments APIs in the market, maybe you're okay with having subpar documentation, but you can quickly think of a few reasons to improve it:
1. A young upstart might come around with better documentation, leading potential customers to choose them over you.
2. You can reduce go-live time for your customers.
3. You can establish trust with your customers and build relationships that compound over time as you develop new products.

All this is to say I understand why some companies choose not to invest in improving their documentation, but the investment certainly makes sense for some.

## Documentation as code

My employer treats documentation with a similar rigor to code:
1. [Documentation linting rules](https://twitter.com/jhzc_/status/1658270046202781696) catch spelling mistakes, broken links, common language style mistakes (passive voice, confusing words like "once"), missing glossary definitions ("webhook"), and more.
2. We think about the [information architecture](https://blog.hubspot.com/website/information-architecture) of our docs, like you might think of a system design architecture before writing code. 
3. Documentation goes through technical writing review.

## Documentation as a value add

My employer is the first example people point to as an example of investment in documentation paying dividends over time. Having spent a lot of time reading our docs, there are a few things I can't help but notice when I read the docs for other developer-focused projects.

1. Some projects **over-invest in feature docs and under-invest in solution docs**. They describe what x is but not how to use it. People visit your docs with a goal in mind, and your mission is to help them achieve it.
2. Some people **brain dump** when they write docs. Every doc needs a thesis statement to orient its direction. Only include details that advance the user towards that goal.
3. **Why use many word when few word do trick**. Some docs could use editing for brevity. Reading convoluted sentences takes a toil on the tired developer's mind. The easiest example is the words "very" and "really" [0].
4. When **documentation is an after-thought**, it's apparent in the developer experience. If you don't build your product ground up from the perspective of how a developer would use it, you notice when it's hard to document. After all, documenting is just describing to a developer how they use your product.

Recently, I've seen a lot of AI tools to summarize documentation on Twitter. While those tools are no doubt useful, I think there's potential in tools to help *write* documentation. I want to see an AI tool that takes a 20-step brain dump guide and converts it to a 5-step MVP tutorial.

If you want to make documentation a differentiating point for your product, I think it's first and foremost about the content. 

How do you know if the content is valuable? Read it.

AI can help you write and edit, but the ultimate test of your docs is if
1. A human understands them.
2. A human can use your product to build something that generates value.

That is, until AI can replace my job as a developer (I don't think it's there quite yet).

---

[0] I'm allowed to use them on my blog, however, because my personal voice can creep in my blog because it's my blog.