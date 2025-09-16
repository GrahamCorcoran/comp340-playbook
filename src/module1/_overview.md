# Systems Analysis

> Systems Analysis is about *understanding the problem* before building a solution.

When developing software, it's tempting to jump in and start building things straight away. When writing small programs like a calculator, simple game, or basic script to automate a task, you've probably done just that! Opened an editor, started typing, and figured things out as you went along.

In general that works quite well and is very efficient when:

- the program is small
- only you are using it
- the "requirements" live in your own head

But when software grows, with mroe features, data, users, or developers working on it, the cost associated with just jumping in starts to go way up. If you don't understand the problem you're solving, you risk building the wrong thing, creating confusion, or missing requirements entirely.

Systems Analysis gives us a toolkit to slow down *just enough* to ask the right questions about what the system should do, capture the answer to those questions, and make sure everyone working on the problem understands the problem the same way.

Think of housing: if we're building a house for a client and decide on a nice, space-efficient 2-bedroom apartment but then discover on moving-day we have a family of 12 moving in, we can have the best apartment in the world but we've fundamentally not solved the problem.

```admonish info title="The XY Problem"
Suppose a friend knows you’re a developer, and they ask how to build a web-scraping bot that can navigate a site, follow links, search for keywords, and download files. Based on that request, you might reach for a library like [Scrapy](https://www.scrapy.org/) in Python and start coding.

A few days later, when you ask which site they want scraped, your friend explains they just need a CSV of updated pricing from a local store. Looking at the site, you realize it has an API - so a single request could have downloaded the CSV in five minutes.  

This is the [XY Problem](https://xyproblem.info/): you solved for “Y,” but what was really needed was “X.” Systems Analysis helps us uncover X before we waste time on Y.
```

## Target Canada

[Target](https://corporate.target.com/about) is the seventh-largest retailer in the United States, and has 1,989 stores across the country<sup>[1](https://corporate.target.com/about/locations)</sup>. Many U.S.-based companies find success tapping into the Canadian market, as many of our spending habits are similar, and culturally we borrow a lot from the U.S. As of July 2025, Costco has 626 warehouses in the U.S., and 110 in Canada<sup>[2](https://investor.costco.com/news/news-details/2025/Costco-Wholesale-Corporation-Reports-July-Sales-Results/default.aspx)</sup> - which means Canada actually has *almost twice as many Costco locations per capita* as the country where it originated! Given that context, Target's Canadian expansion in 2013 looked like a safe bet.

However some of you may remember the brief time Target was in Canada. The experience was lacklustre, and despite a lot of initial excitement, the brand closed all 133 stores they had opened in *fewer than two years* of operation.

```admonish info title="Want to read more about the Target Canada expansion?"
The Target Canada expansion has already been studied and will likely be talked about for a long time in Business classes. The full details of the failure go beyond the scope of this course, but if you'd like to read more you can see an article from [Harvard Business Review](https://hbr.org/2015/01/why-targets-canadian-expansion-failed), and there's [a blog](https://www.henricodolfing.com/2019/09/case-study-target-canada-failure.html) by Henrico Dolfing which contains a good summary of events.
```

### The Problems

Target Canada’s troubles were multi-faceted, touching everything from supply chains to customer expectations. At the heart of it all was an overly aggressive expansion strategy: instead of piloting a handful of stores and scaling gradually, Target tried to open more than 100 locations across the country in less than two years. This left little time to adapt U.S. practices to the Canadian market, test systems thoroughly, or resolve early warning signs before they cascaded into larger failures.

### Software Problems, Too!
Target's problems went beyond business decisions and supply chain problems. There were serious software and data problems, too. Canada was Target's first attempt at international expansion, and they over-relied on our similarities and assumed there would be less internationalization headaches than there were. As part of the rollout, Target developed new software to handle the changes, but this software was riddled with probelms.

**Bad Product Data**

The inventory system was often missing data or wrong entirely, resulting in warehouses shipping the wrong quantities of goods, shelves sitting entirely empty of some goods, and back rooms overflowing with others.

**Rushed Systems Integration / Rollout**

Target pushed quickly for rapid expansion, so they integrated with all of their suppliers, warehouses, and stores at once. Early bugs weren't caught until they had already been scaled across the country.

**Slow Feedback Loops**

Store managers and employees were aware of problems immediately, but the system wasn't designed to capture that information quickly.

All of this lead to a series of cascading problems: Target couldn't achieve their core objectives anymore, and so between January 2015 and April 2015, they closed all 133 of their locations.

```admonish example "In-Class Exercise"
What requirements should target have validated first regarding the software requirements differences between the U.S. and Canada?
```