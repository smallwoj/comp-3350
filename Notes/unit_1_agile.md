# Unit 1: Agile Software Development
## Overview
![img](../img/agile_fig1.png)
- The product we are delivering is software, not documentation or design.
  - Documentation: heavyweight
  - Product on its own: lightweight
- Priority is to deliver useful software
- Emphasis on:
  - Adaptation
  - Quality
  - Simplicity
  - Trust 
  - <ins>Communication</ins>
- A lot less rigorous than waterfall
- Spectrum of different agile processes
- ![img](../img/agile_fig2.png)
- We're not coding like hell
- We're gonna be using...
## Our Agile Process
- Specific for this class
  
![img](../img/agile_fig3.png)
1. Strategic Planning
2. Release
   1. Release Planning
   2. Iterations
      1. Planning
      2. Development
      3. Review
   - Repeat each iteration multiple times
     - For us, 3 iterations
   3. Release Review
- Ends here, but if this was continuous development, continue with another release.
## Strategic Planing
- Produce a written [vision statement](#vision-statement)
### Vision Statement
- Describe the purpose of the project
- Process includes everyone involved in the project
  - Developers
  - Users
  - Customers
  - Managers
  - etc.
- Defines what you're going to do, NOT how
- Brief (paragraph) to long (a few pages)
- Outlines:
  - What is the project going to accomplish?
  - Who are the users of the product?
  - Why is the project valueable to the users?
  - What are the success criteria?
    - Have to be specific, concrete, and quantifiable
  - May contain other things
    - Future directions
    - Metaphor
- This is a document for a general audience, not just developers
  - Terminology can refer to the domain, but nothing from the developers
  - <ins><b>NO TECHNICAL DETAILS</b></ins>
## Metaphor
Ex. `A stack is implemented as a linked list with pointers to nodes ending in null`
- None of those things actually exist
- `null` is a metaphor for 0 is a metaphor for low voltage signal

ex. Auction software
- Ebay
  - Happens over the span of a week or so
- Auction house
  - Happens live over the course of a minute
- Dutch auction
  - Start high, work low
- First price sealed bid
  - Highest bid without knowing other bids
  
These are all based on traditional auctions
- Refer to items and bids

Stock market
- Agents
- Boards

Bazaar
- Merchants
- Stalls
- Haggling

Rummage sale
- Table
- Buyers

Store
- Inventory
- Cart
- Checkout

Ex. A course registration system

Visit to advisor
- Suggested courses

Not required, but important for planning
## User Stories
- Intended to replace the documentation done by analysys in heavyweight software development.
- Describes what the user wants to accomplish
- Ex. `I want to be able to see my grade in a course I've taken.`
- <ins><b>NOT TECHNICAL</b></ins>
- User stories should be written by users with developer participation
  - The <ins>conversation</ins> is as important as the stories themselves
- The language is simple, not technical
- Helpful trick: Start with `As a ____, ...`
  - Ex. `As a student, ...`

![img](../img/agile_fig4.png)
