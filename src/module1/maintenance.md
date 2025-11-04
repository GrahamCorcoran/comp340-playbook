# Maintenance

> Maintenance is the process of keeping software reliable, secure, and useful *after* it has been deployed.

Once software goes live, the work isn't done. Real users will uncover issues that weren't found during testing, technology will change, and requirements will evolve. Maintenance ensures the system continues to meet its goals long after the initial release. Maintenance consumes the majority of a software system's total cost over its lifetime. The effort to sustain software usually outweighs the effort to build it.

## Value and Negative Value
In the context of Systems Design and Analysis, you can think of the contribution of each feature towards your core objective as value-adds. Picture designing a vacation rental booking service: the ability to book a rental at all is a core requirement and is essential, but the ability to filter based on price is a value-add, it's non-essential but desirable. If you can only spend $100/night, there's no point wading through dozens of listings of $350/night! From a business perspective, giving users this extra feature will likely increase the usability of your site, and make it more likely they spend money.

On the opposite side of the coin is the idea of something with negative value. One type of negative value can be a poorly conceived feature. A "location randomizer" mode in which you place a booking and get booked for a random place might sound great to a very select group of adventurous types, but most people would find that feature irritating at best and dishonest at worst.

More common examples of negative value will be bugs, complexity, confusion, or just general poor usability. Imagine if you had to take a photo and submit your ID for *every* booking because our application chooses not to handle personally identifiable information (PII). That decision to reduce risk by not handling PII has a distinct benefit to the business, reduced cost. However this comes at the expense of a poor user experience.

## Maintenance Types

**Corrective Maintenance:** Fixing bugs, errors, or vulnerabilities that show up in production. Even well-tested systems eventually encounter unexpected problems.

**Adaptive Maintenance:** Updating the system to work in new environments, for example, upgrading to new operating systems, browsers, or hardware platforms.

**Perfective Maintenance:** Improving or extending the system based on user feedback, such as adding new features or streamlining workflows.

**Preventive Maintenance:** Making proactive changes to reduce the chance of future problems, like refactoring code, improving documentation, or addressing technical debt.

## Challenges

Over time, systems accumulate complexity. Legacy code, shifting requirements, and limited resources can all make maintenance difficult. In the worst case, Balancing urgent fixes against long-term improvements is part of the discipline. Maintenance is not just about "fixing what's broken," but about sustaining and evolving software so it remains valuable for years to come.

```admonish example title="Check Your Understanding"
1. Why does maintenance often account for the majority of software costs over time?  
2. What is the difference between *corrective* and *preventive* maintenance?  
3. How does technical debt affect the long-term maintenance of a system?  
```