---
layout: post
title: "Algorithms are Recipes for Getting Things Done"
date: 2013-04-14 20:41
comments: true
categories: [business, programming]
---

Since I started reading and taking a course about [algorithms](http://en.wikipedia.org/wiki/Algorithm), I've come to understand that they are much more than just complicated math formulas that Google uses to crawl the web and rank my search results. Algorithms look intimidating when written out in programming code--or worse, mathematical notation--but their definition and purpose are simple. An algorithm is just a finite, repeatable list of steps to solve a problem. 

In other words, an algorithm is *a recipe for getting sh\*t done.*

To illustrate this point, I'll provide a classic example of a use case for an algorithm: sorting a list. Imagine you're playing Scrabble and you want to sort your tiles so that you can find the ones you want to use more quickly.

OK, but how do you sort your tiles? 

"Easy," you might think, "just put them in alphabetical order from left to right."

But how would you explain, step-by-step, what you are actually doing when you sort them? Can you break it down into a list of instructions?

The way you would instinctively sort your tiles, if broken down like a recipe, might look like this: 

+ Scan your rack of tiles from left to right, looking for the letter closest to beginning of the alphabet
+ When you find it, swap it with the leftmost tile.
+ Repeat steps one and two with the rest of the tiles on the rack that are not sorted yet.

And you would have found a correct sorting algorithm, which you could test out like this:

	SCRABBLE <= unsorted
	A CRSBBLE <= 'A' is the lowest letter, so swap it with the first letter 'S'
	AB RSCBLE <= 'B' is the next lowest letter, so swap it with the second letter 'C'
	ABB SCRLE <= 'B' is the next lowest letter (again), so swap it with the next letter 'R'
	ABBC SRLE <= and so on...
	ABBCE RLS
	ABBCEL RS <= (hey, these two are already in order)
	ABBCELRS <= and now it's sorted.

This is what computer scientists call a ["selection sort."](http://en.wikipedia.org/wiki/Selection_sort) They would also call it a "naive" or "brute-force" algorithm, because as it turns out, it's a very inefficient way to sort a list. Since for each letter in the list, you have to scan through all the other letters to see which is lowest, that means that if your list has *n* letters, you have to make on the order of *n*<sup>2</sup> comparisons in order to completely sort the list. So as the size of the list you need to sort grows, the amount of time it will take to sort the list grows *quadratically* (proportional to the square of the number of items in the list). Not a big deal when sorting Scrabble tiles, but what if you're in a position where you need to sort a list with a million entries? Maybe you work at a phone book company in a city with a million residents. A White Pages with the people's surnames in unsorted order wouldn't be very useful, would it?

Now, you should probably use a computer to do this job, as there's no way you could possibly sort a list of a million names manually in one lifetime. Computers can make comparisons very quickly--let's say yours takes just a millisecond to compare two letters and put them in order. But with a million-squared comparisons to do, sorting the entire list would still take the computer almost 32 years!

Clearly, if you actually have an unsorted list that's a million entries long, and that phone book is supposed to get printed next Monday, you need to do something drastic in order to get it sorted faster.

There are three ways you could achieve that:

1. Get a faster computer that can do each comparison in less than a millisecond
2. Get more computers and divide the task among them
3. Find a faster sorting algorithm that makes fewer comparisons for each item in the list.

If you actually try the first two of these methods, you will find out that you quickly run in to a wall. Getting a faster computer helps, but you probably cannot afford a computer that is 10x faster than yours--those are called "supercomputers" and they cost millions of dollars. And even that 10x faster computer would still take over 3 years to get the job done.

The second option would be equivalent to chopping up the unsorted list into many smaller lists, using a separate computer to sort each sub-list, and then merging the sorted sub-lists back together into one sorted list. This would certainly be cheaper than buying one supercomputer, but you still have to buy many normal computers, and then figure out how to do the splitting and merging.

So, that leaves #3--get a better algorithm. And as it turns out, mathematicians and computer scientists have come up with [a lot of better sorting algorithms](http://en.wikipedia.org/wiki/Sorting_algorithm#Comparison_of_algorithms) over the years, and are still working on coming up with new ones. They are not all equally good, and they each have strengths and weaknesses, but the best algorithms among these could get those million phone book entries sorted in a matter of just a few *hours* on a normal computer. Still a long time to wait if you're in a hurry, but much better than waiting *years* for a lesser algorithm to finish running. And best of all, these efficient algorithms are free! It doesn't cost anything to use a better algorithm--at least one that has already been discovered.

Now the reason I bring up this sorting example is not because sorting Scrabble tiles or the White Pages is particularly interesting, but because *an algorithm is just a formula for solving a problem.* So whenever there is a large amount of work or a complex problem to be solved and it doesn't look like you'll be able to get it done in time, you still have only the 3 fundamental approaches above to choose from, to improve your outlook:

1. Work harder/faster/longer (aka caffeine, Adderall and/or just staying really late)
2. Get others to help you (aka division of labor)
3. Use a more efficient process  

You can probably see where I'm going with this now, but #3 is always the right answer, until your process is so efficient that it can't be optimized any further, then you can start looking at options 1 and 2. This is what "work smarter, not harder" really means.

Companies have a problem to solve, and that problem is always some variation on taking money and turning it into more money, aka "adding value." When the amount of sales increases, the company needs to provide service to all of those customers. But how much additional help does the company need to hire in order to handle each additional customer? In other words, how well does the company's business model *scale?* 

A "business model" can be thought of in an abstract way as just a type of algorithm for solving a business problem. Many businesses will push their workers to work harder and longer hours in order to handle an increased volume of work. Others will hire more workers so that each worker continues doing about the same amount of work, and the company steadly grows in size (hopefully). Most companies use some combination of these two strategies, and they both have a cost. But the company that chooses to make the business model itself more efficient, by removing unnecessary steps from its work processes, will be the most able to scale. 

This is also a major reason why businesses fail. If your company's business "algorithm" is an inefficient one, its profitability will deteriorate with size as the rate of cost growth is faster than the rate of revenue growth. And when companies are faced with financial losses they launch "cost cutting" initiatives such as mass layoffs and reduced spending on sales (particularly advertising and entertainment expenses), but because these measures also reduce the ability to attract and process new business, what these really amount to is scaling down the company's operations--it may reduce losses, but at the cost of growth, giving up market share to competitors and perhaps permanently stunting the business's future growth prospects. The alternative way to cut costs--without affecting the revenue stream or throughput capacity of the business--is to improve the algorithm. Don't scale down your business by laying off workers and cutting back sales expenses--just improve productivity by finding clever ways to reduce the amount of steps or sub-tasks each individual worker needs to take in order to get a task done. This isn't always possible in the real world, and it may be too little, too late for a company with a very unhealthy balance sheet, but it's still the right philosophy to approach the problem from the manager's perspective.

And although managers have to deal with real-world complexity and manage business processes that are a lot more complicated than a simple sorting algorithm, the nice thing is that people, unlike math formulas, will *tell* you what's slowing them down. They know, you just have to ask them. (This is a topic for another post, but almost all people actually *like* working and *want* to be good at their jobs. It's dealing with office politics and time-wasting red tape that they hate.) And taking their advice is usually cheap and can even be free--things like "stop making us waste hours in pointless meetings" or "stop making us put together those daily status reports you never read."

Now, the benefits of thinking algorithmically do not only apply to the workplace. You can also use this in your personal life to make yourself more productive. Cutting out a few unnecessary steps from your routine can save you perhaps a few minutes a day, which will add up to years over your lifetime.  Don't stay late at the office unless it's an emergency or you actually get overtime pay. If you need to stay late on a regular basis, you are working inefficiently and you need to examine your work process to eliminate time-wasters. Invest in quality labor-saving appliances that reduce the time you need to spend on household chores, freeing you up to either do more income-generating work or spend quality time with family and friends or on hobbies that you enjoy. Before you start working on something, stop and take a moment to think of the most effective way to get the task done. Efficient algorithms are sometimes counter-intuitive, and can take a little stroke of genius to come up with on your own, but for any sizeable job, a plan that you put some algorithmic thought into will beat out the "brute force" method handily.