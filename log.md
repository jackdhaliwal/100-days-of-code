# 100 Days Of Code - Log

Day "31": August 22nd, 2017 Tuesday, 9:04PM

Today's Progress/thoughts: 
(Post from yesterday evening) - Yesterday I started the Fall semester at school and have commited to 17 units (4 classes). Although this means I'll ostensibly be learning a lot in the classroom, I won't be able to commit as much time to DS/Algo/Side projects for the next few months. I will however still plan to commit at least some sort of code to github at least every 1-2 days. Whether this means simply adding to this log incrementally, or knocking away at HoopTime/finally getting it into production, or starting a new app...that's what weekends will be!

Moving on, I worked on Leetcode 155/CTCI 3.2 Stack Min where we're asked to Get the minimum element from a stack in O(1) (Constant) time.
I learned that we can achieve this by using two stacks, one for the elements that will be pushed to it, and another to keep track of the minimums. We use the push, pop, and min operators. It was pretty straight forward, but I feel a bit more empowered by learning how to do it.



Link(s) to work: http://image-store.slidesharecdn.com/1d408b6d-fcf9-4f47-84e1-6cd4b3123d2e-original.png


Day "30": August 15th, 2017 Tuesday, 10:00PM

Today's Progress/thoughts: 
Worked through "Single Number" on LeetCode this evening. We are asked: Given an array of integers, every element appears twice except for one. Find that single one.

Note:
Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?



Approach: 
Although this problem looked intimidating at first, after gaining a basic understanding of XOR in Java, I was able to understand that we could use it to return all like pairs of elements along with the single one that we are trying to find.
- We traverse through the array via a for loop and store the the result of each pair of elements (and the single one) in the result variable: result^=nums[i];
- When using XOR, it will return false (0) any time both A & B values are the same. Ex: 0^0 == 0, 1^1 == 0, false^false==false.
- A illustration of our function looks like the following: 
N1 ^ N1 ^ N2 ^ N2 ...Nx ^ Nx ^N
= (N1^N1) ^ (N2^N2) ... (Nx^Nx)^N
= 0^0 ^ 0^0 ... 0^0 ^N
= N (our single element)


..all with no extra memory use and in O(n) or linear time kinda cool!


Link(s) to work: http://image-store.slidesharecdn.com/2c63c75a-a94e-4398-aa37-0e20ab7d1144-original.png

Day "29": August 13th, 2017 Sunday, 10:00PM

Today's Progress/thoughts: 
Finally back to CTCI. In 2.6 - Palindromes, we are asked: Given a linked list, write a function to determine whether the list is a plalindrome (same forward and same backwards).
Ex: 1->2->3
Questions: 
- what type of list? 
- 
Approach: There are a couple of ways to approach this problem:
- Reverse linked list, and then compare. (involves copying entire linked list which seems kind of uncecessary. You could split list and half and then reverse only first half - KIND OF COMPLICATED)  
- Recursion?
- Iterative appoach (one case for odd, one for even!!). 

Iterative: Store values that we've visited thus far and compare them once we get to second half of list using Stack. 
- Assuming we don't know size of list. If we do, just iterate through first half of list with for loop and push each element onto stack. 
- if we don't know size, use fast runner/slow runner (pointers). With while loop, push data from slow runner onto stack. When fast runner reaches end of list, or past end (even), slow runner will be at middle. 
- stack should have all elements in first half of list
- Now iterate through list and at each iteration, compare node to top of the stack. If we complete iteration and don't find difference, the linked list is a palindrome. 




Link(s) to work: http://image-store.slidesharecdn.com/e13ab8a5-39c7-4c0f-b588-54c18e464658-original.jpeg 


August 6th, 2017 Sunday, 12:15PM

Today's Progress/thoughts: 
Wrote up a detailed blog post about my (and my team's experience) from AngelHack, last weekend. Please check it out:
https://medium.com/@jackdhaliwal/my-first-hackathon-team-my-circle-c2758852ee64

Additionally, I've decided to dive into DS/Algorithims studying a bit more this month as I can definitely use more practice. I worked on 2.3 in CTCI today (Delete Middle Node) which I found to be relatively simple. I used my notebook to write out the approach/logic/code this time and I focused on trying to understand the java code as best as possible. 
We are asked: Implement algorithim to delete a node in the middle (any node but the middle or first) of a singly linked list, give only access to that node.

Approach: In a singly linked list, we know that we have access to the data of the current node, the id of the current node, and the next pointer of the current node which gives us access to the next node and the node after that etc.In regard to deleting a node from a linked list, we can point the next pointer of the previous node to the node after the current to break the link between the previous and the current node/establish the link between the previous and the next. This would effectively delete the current node in a linked list, and we can use this approach as a guide for our problem.

- To delete our "middle node" in this problem, we:
1. Check to see if we're at the tail or the next node is at the tail by checking to see if both nodes are null.
2. Copy the id from the next to the current node.
2a. Copy data from the next to the current.
3. point next pointer of current node to the the node we just deleted's next. (get rid of connection and connect previous to next.next.


Link(s) to work: http://image-store.slidesharecdn.com/fc4ea167-8791-4516-9dc0-420b083c7ff5-original.jpeg

Day "28": August 1st, 2017 Monday, 9:35PM

Today's Progress/thoughts: 
Took some time away for the Angel Hack Hackathon this past weekend, but I'm back at it! Skipped 2.1 in Linked lists (CTCI), as I couldn't wrap my head around the solution, but plan to come back. For now, I worked through the solution of 2.2 (Implement algorithim to find kth to last element of a singly linked list). 
-Used the iterative approach 
-Two pointers to keep track of current and follower nodes.
- Place them k nodes apart by putting p2 at beginning and moving p1 k nodes til we hit null.
- p2 would follow in sync and then Length(at which place p1 hits null) - k (position of p2 node) will give us the output that we want. 

Excited and am working on a blog post for this past weekend. Amazing experience. Coming soon!


Link(s) to work: http://image-store.slidesharecdn.com/1fe66fe1-5c18-4be4-a8e0-286a9050d5e8-original.jpeg

Day "27": July 25th, 2017 Tues, 12:04AM

Today's Progress/thoughts: 
Finished 1.9 - String Rotation in CTCI today. I wrote out a solution on the whiteboard and followed an example online to make sure the logic stuck. Surprisingly simple algorithim. 

Question: We have a function "isSubstring" which checks whether a string is substring of another. Given two strings s1 and s2, write code to check if s2 is a rotation of s1 using only one call to "isSubstring".

Example of substrings: - Original: "waterbottle"
                       - Candidate for substring: "erbottle"

Approach: - ensure lengths are the same
          - ensure both are > 0
          - assign a new variable to (s1 + s1)
          - make one call to isSubstring
Solution: To check if one string (s2) is a rotation of another (s1), I learned that we can take the original, in this case s1.. and concatonate it to itself, assign this to a new variable (newS1=s1+s1), and then pass in the new variable along with the second string in our one function call.

Ex: isSubstring(newS1,s2)

We can then try and newS1.find(s2) [try to find the second string in the new concatonation of the original] and if it is found, it's a rotation! 
Ex: s1= waterbottle
    s2= erbottle
    newS1=waterbottlewaterbottle
    s2 is a rotation of s1! 


Link(s) to work: 

Day "26": July 23rd, 2017 Sunday, 7:23PM

Today's Progress/thoughts: 
Finished reading/whiteboarding 1.8 in CTCI (Zero Matrix). We're asked: Write and algorithim such that if an element in an MxN matrix is 0, its entire row and column are set to zero. I used byte by byte's video, and the actual code from the book to help me roughly understand the problem/approach.

Questions:- modify in place, or return a new array?
          - Will this be a single atomic solution?
          - dimensions of matrix (answered in question)
Assuming that the approach will modify the matrix in place (void function, nothing returned), that it is in fact a single atomic solution where we compute the cell modifications first before editing, and assume that this is an MxN matrix.

Possible approaches: - we could create a new matrix but it will not be very efficient.
                     - we could use bit vector instead of bool array, check if first row and column have any zeros by using two variables and setting them to false initially. 
                     
Solution: Using the second approach: 
          - We set both variables to true if first row or first column have a zero.  
          - We continue by iterating through the rest of the matrix, setting matrix [i][0] and matrix [0][j] to zero whenever there is a zero in matrix [i][j].
          - We then iterate through rest of matrix, null row i if there's a zero in matrix [i] [0].
          - Similarly, we nullify column j if there's a zero in matrix [0][j].
          - Finally, we nullify the first row and first column if necessary. 
          
 This one was rough for me, but I'm confident with a bit more whiteboard practice, I can wrap my head around it completely. 

Link(s) to work: https://shmedium.herokuapp.com/pages/about

Day "25" was deleted some how, but here is the linkedin post: https://www.linkedin.com/feed/update/urn:li:activity:6294312961506971648

Day "24": July 18th, 2017 Tuesday, 11:52PM

Today's Progress/thoughts: 
- Removed extra/unneccessary sign-in flash messages that devise was throwing out to users. Hoping to setup the mailer for "forgot password" feature

- Also finished 1.6 (String Compression) in CTCI. This was the first problem that I worked with and semi understood with a solution in Java. I followed along with the solution here: https://www.youtube.com/watch?v=XMKMgzU1uiw. The question asks to write a method that performs basic string compression using counts of repeated characters. (Ex: aabbcddd = a2b2c1d3) The assumption is that the string only has uppercase and lowercase chars and and that if the compressed string is longer than the original string, simply return the original string. 
# Approach: Start with an empty string which will eventually be our compressed string. We then need a counter variable to keep track of the characters we count. Next a forloop that will go through the string and have two cases:

1st case - if current char == next char, keep counting
2nd case - if current char != next char, append current char to new output string and add sum.
Then, we reset the sum or counter to 1. 
Next, we append whatever is left at the end of the original string to the new output string. Finally, the question asks us to consider that if the new output string is longer than the original string, go ahead and return the orignal string. Code for this:
return out.length() <s.length () ? out : s;

Lastly, I was confused because CTCI talked about StringBuilder (Java), which are string-like objects, but can be modified.Did not know this before today, kind of cool. 



Link(s) to work: https://www.linkedin.com/feed/update/urn:li:activity:6293341066783531008


Day "23": July 17th, 2017 Monday, 10:39PM

Today's Progress/thoughts: 
- Added necessary files to make SHMEDIUM (my portfolio portal) heroku ready (a basic version)
- Cleaned up readme/about pages
- ***Pushed SHMEDIUM into production***
- Need to continue working on devise routing/views/configuration


Link(s) to work: https://shmedium.herokuapp.com/pages/about

Day "22": July 16th, 2017 Sunday, 11:00AM

Today's Progress/thoughts: Worked through 1.5 (one away) solution in CTCI. Explanation. We're given two strings and are asked to write a function to check if they are one away or (one edit) from each other. We approach the problem in the following way: there are only three types of edits  that can be done on strings (inserting char/removing char (inverse of insert) and replacing a char). 

The brute force solution as discussed in the solutions chapter describes checking all possible strings that are one edit away by testing removal,insertion, replacement of each character respectively and comparing. This however would be too slow and so another approach is more sensible.

We can develop a check (function) for replacement, and another for insertion/deletion. Instead of checking the strings directly for the edits, this can be determined by comparing lengths. For example, if the lengths are the same, call the replaceedit function. Else, we call the insertion/deletion function. This approach which I whiteboarded is O(n) where n represents the length of the shorter string. (If strings are same length (or +/- one char, runtime will not change. If strings are very different lengths, then algo will terminate in O(1) time. One really long string will not extend runtime. Both long strings would. 

There is an alternate approach of combining both checks into one, where we're able to check for replacement edit/insertion/deletion which would be more compact and would follow the DRY principle but personally, I found seperating the checks in multiple methods a bit more clear/maintainable for the next programmer who may have to work on the code. 


Link(s) to work: http://image-store.slidesharecdn.com/730fff69-b5ab-4805-a160-49d1bfea7f2f-original.jpeg

Day "21": July 15th, 2017 Saturday, 5:45PM

Today's Progress: Spent a few hours finally deploying the test version of the HoopTime app to production! 


Thoughts: Next I'll be moving onto pushing the official version of HoopTime to production via Heroku.On to CTCI for the night. TG Summer Semester is over! 

Link(s) to work: https://fast-stream-14431.herokuapp.com

### Day "20": July 10th, 2017 Sunday, 9:54AM

Today's Progress: After failing to deploy hooptime into production via Heroku last night, I decided to take a step back and build a toy app following a scotch.io tutorial found here: https://scotch.io/tutorials/how-to-deploy-a-node-js-app-to-heroku. Even deploying this simple app built within half an hour proved to be more challenging than I thought. Apparently, Heroku requires you to additionally specify your node version in your package.json. Once I did this, we were good to go.

From this, I got a better feel for what type of info is included in say a package.json file or Procfile, which Heroku definitely wants setup correctly. I was able to successfully deploy the toy app into production fairly quickly, and after a little gym time, will dive back into deployment of hooptime. 

Thoughts: I'm glad that my summer course is coming to an end and I can jump back into more coding/building/practicing.

Link(s) to work: https://pbs.twimg.com/media/DETx3FfUAAAcDQS.jpg


### Day "19": July 9th, 2017 Satuday, 1:15AM

Decided to take a break from db setup and work on getting something deployed into production via heroku. After two hours of debugging, still having trouble getting hooptime running in production. More work in the morning. 

### Day "18": July 5th, 2017 Wednesday, 11:39PM

Today's Progress: An hour of reading through how to hookup MongoDB/ExpressJS to HoopTime! I've got mongodb/expressjs/mongoose installed locally and created a simple user model following a scotch.io guide: https://scotch.io/tutorials/using-mongoosejs-in-node-js-and-mongodb-applications



Thoughts: Need to a bit more reading, and a lot more coding. I'm happy that even the 30 minutes that I spent tonight getting the backend somewhat connected, was progress. It's almost like a weight has been lifted from my shoulders because even in between CTCI problems the last few days, I've been craving some time with my app!


### Day "17": July 4th, 2017 Tuesday, 1:49PM

Today's Progress: 1.2/1.3 whiteboarding via Solutions Careerup Repo on github.

Thoughts: I had a few hours this morning to work through the solutions of 1.2 and 1.3 in CTCI Chapter 1. 1.2 asked: given two strings, write a method that checks if one string is a permutation of the other. I was able to walk through the solution from Careerup's c++ solution repo and use the following approach: find the length of both strings, compare these lengths (if lengths differ, they cannot be permutations of each other). Next, sort the strings from beginning to end, and compare these now sorted strings. From there I was able to successfully determine if the given strings were permutations of each other.

1.3 focused on URLifying a given string, (adding %20 to any spaces within the string). The solution that I found (and am still trying to grasp fully) was to use two passes as CTCI noted. The first pass to count the number of spaces. Before the second pass, triple the number of spaces so we can compute how many chars we will have in final string. In the second pass, edit the actual string from end to beginning because according to CTCI, with string manipulation problems, the extra buffer at end allows us to change chars without worrying what we're overwriting. (still trying to understand this fully). Time to July 4th, hard. Cheers.

Link(s) to work: https://repl.it/JLMF/9  (1.2)
                 https://repl.it/JN2l/5  (1.3)
                 https://pbs.twimg.com/media/DD61_UnVoAAZpk7.jpg
                 https://pbs.twimg.com/media/DD61_UqVYAE0nvB.jpg


### Day "16": July 2nd, 2017 Sunday, 4:46PM

Today's Progress: Started working on solutions in CTCI. 

Thoughts: Two trig exams down, one more to go and I have the grade that I want in the class so far. Two more weeks and the class is over and I can focus fully on working through CTCI solutions, and taking a stab at leetcode along with continuing to add features to HoopTime, the portfolio portal, and pushing both into production. I plan to go through 1 solution a day. Going through the first one in Arrays and Strings, and finding a solution that I somewhat understood took about 1.5 hours. I'll have to find a way to be more efficient but I think whiteboarding the solutions is going to be necessary prep. 

**Link(s) to work** 
https://repl.it/JKwe/3
https://pbs.twimg.com/media/DDxKRf0VoAA4FXb.jpg
https://pbs.twimg.com/media/DDxKRr4VoAA8zx-.jpg



### Day "15": June 26th, 2017 Monday, 9:50PM

Today's Progress: Took a break from HoopTime/the portfolio portal push to production to make a c++ tutorial on functions.

Thoughts: Trig exam tomorrow, but needed to do something related to programming to keep my sanity. I've been meaning to make a new c++ tutorial just to kind of gauge if I've grown in terms of confidence when speaking about this stuff, and compared to my older videos, I can definitely say that I feel more comfortable with the concepts, syntax, what is going on in general. There is always room for improvement, but it feels good to publish some content nonetheless :)

**Link(s) to work** 
https://youtu.be/qA23ow_1m54?list=PL8ud3mY4a0w1e3kXqk_uTj4J2skl_jguO


### Day "14": June 24th, 2017 Saturday, 9:50PM

Today's Progress: Desperately trying to push my rails driven portfolio portal site into production. 2 days in playing with procfile, package.json files, resetting buildpacks but Heroku still hates me. 

Thoughts: One exam down and 2 more to go (at least). I'd like to work on getting my portfolio's main portal into production as Summer '18 applications are now approaching the less than 3 month mark. I then am hoping to add some more park data/features to HoopTime and put it into production as well. My goal after this class is over in two weeks will be at least a few pages of CTCI and a LeetCode problem per day, and working on one more smaller app in a different language (likely React). 


### Day "13": June 19th, 2017 Monday, 9:50PM

Today's Progress: Added to local dummy authentication. Cleaned up routes. 

Thoughts: Just got done with the first quiz for my summer trig class. Hoping to add to/finish the authentication feature by the end of the week. 

### Day "12": June 5th, 2017 Monday, 10:49PM

Today's Progress: Beginning authenticatio following example from: http://jasonwatmore.com/post/2015/03/10/angularjs-user-registration-and-login-example-tutorial#authenticationservice

Thoughts: It was also the first day of trig so although I have to focus on that class over the next 6 weeks, I'm going to try and commit about an hour of my evening to completing this authentication project. Wish me luck! 


### Day "11": May 31, 2017 Wednesday, 11:54PM

Today's Progress: Added data to two more parks/finished Lecture 4 of MIT 6.006 Intro to Algorithims - Heaps and Heap Sort

Thoughts: I'm focusing on adding as much Park data before I move onto user log-in/log-out so that users can eventually "check in" to parks and I can find a way to keep check in data/rank users.

### Day "10": May 27, 2017 Saturday, 4:35PM

Today's Progress: Used Angular Seed app as bootstrap for HoopTime

Thoughts: The best way to learn a particular framework/language in my opinion is to create. That being said, I've mocked up how I want the park/court data to display, gone ahead and cleaned up some initial structure, json data to reflect a few parks in elk grove, and added a custom filter (runRating) which rates how "good games" are at given park. More data seeding later. 



### Day "9": May 22, 2017 Monday, 4:44PM

Today's Progress: Refined Shmedium to be central hub for all of my portfolio-related content. (Blog, projects, tutorials,etc)

Thoughts: It's been a few months since I've touched this. Although I have been coding (mainly in C/C++) for school, I haven't been able to play/contribute to my portfolio project. I am planning to use the summer to continue writing, making tutorials, learn angular, participate in meetups, take a summer class.. so this should keep me busy but I am hoping to add a bit more content to the rails-driven site through out the summer months.



### Day 8: February 5, 2017 Monday, 10:50PM

**Today's Progress**: 3 Video walkthroughs on Loops/Loop Patterns in C++ 

**Thoughts**: Had some tough assignments this weekend that I wrapped up this morning along with some great help with my fellow classmates/resources online. C/C++ is challenging, but it's fun. Must. Keep Going.


**Link(s) to work**
1. https://youtu.be/ZhspmEPshks
2. https://youtu.be/CmRMc1yo0dk
3. https://youtu.be/BKeH2Yl_EcI

### Day 7: January 31, Monday, 9:36PM

**Today's Progress**: Part 2 of Video # 1 complete. 

**Thoughts**: Refresher on Geometery, starting to the climb the mountain of C/C++. My legs already hurt. 


**Link(s) to work**
1. https://youtu.be/fRG-4iJ6XOs


### Day 6: January 29, Monday, 10:00PM

**Today's Progress**: Finished first C/C++ Assignment for class. Created video tutorial part 1.

**Thoughts**: Part 2 soon.

**Link(s) to work**
1. https://www.youtube.com/watch?v=JcAPAmIStOU

### Day 5: January 23, Monday, 10:40PM

**Today's Progress**: Full speed ahead with my C Programming class. Taking a break from rails til the weekend most likely, as I want to commit fully to mastering C as much as possible..(I am paying for the class after all). Learned about Operators, If/Else statement, proper structure of a C program, and setup Code Blocks as my IDE for C.

**Thoughts**: Busy week ahead. Whatever it takes!

**Link(s) to work**
1. https://twitter.com/jdhaliwal24/status/823782264278425600



### Day 4: January 21, Saturday 1:02AM

**Today's Progress**: Decided to switch gears and add a very basic Twitter feed utilizing Twitter Gem. Got a refreshed on environment variables and the importance of keeping those local/using figaro to hide them. Also had some fun reading through the Twitter Gem docs/watching some vids on how to get the feed setup correctly.

**Thoughts**: I've realized that I simply want SHMEDIUM to be an app where I upload my blogs and share them. I still have a lot of refining to do, and that's fine..but it's coming along quite nicely. Another epiphany I've had is that most of my side projects will be put off until the weekends or on evenings when I'm not in class. It's the only way (at this point) that I feel like I'll get the grades that I want in all of my classes this semester, and I have to be honest with myself. Building this app is something I WANT to do. I don't want to stress myself out and not finish it. So one day at a time from now on. Coding remains fun :)

**Link(s) to work**
1. https://twitter.com/jdhaliwal24/status/822732934364827648


### Day 3: January 16, Sunday 1:30AM

**Today's Progress**: Watched a bunch of football but I was feeling anxious to make use of Facebook API to authenticate with the SHMEDIUM app. Success! We can now authenticate with facebook credentials. It was a challenge, but I am glad I kept cracking through docs/google/stackoverflow to not only copy/paste code while pulling my hair out..but to learn a bit more about what was happening in my controller..user model..with Devise/Omniauth, and how facebook setup for third-party website logins, isn't as simple as it seems. Good challenge. 

**Thoughts**: My C++ class is around the corner, and so I'm going to try to put a few more hours in to clean up some routes/views and overall logic with SHMEDIUM tomorrow, as I'll be limited with outside of class coding..real soon.

**Link(s) to work**
1. https://twitter.com/jdhaliwal24/status/820928201316659201

### Day 3: January 14, Friday 4:20PM :)

**Today's Progress**: Pulled up a chair at starbucks for a few hours to read some docs/blog posts on the twitter ruby gem and create a very basic twitter bot that retweets hashtags and can send out tweets.

**Thoughts**: I should have built this sooner! It was a good ruby syntax refresher and now I can finally say I've built (a basic) Twitter bot. Back to SHMEDIUM app refinement and some C++ studying before my class starts next week. 

**Link(s) to work**
1. https://twitter.com/jdhaliwal24/status/820062714890358784

### Day 2: January 13, Thursday 3:00AM

**Today's Progress**: Spent 3 hours integrating User Authentication system via Devise, Omniauth. 95% complete barring a few errors which I will address later this morning. 

**Thoughts**: Proud that I stuck through it. 8 months ago when I was hacking my way through michael hartl's tutorial, I was so very lost. Now, with a few tutorials, meetups, stackoverflow questions and a lot of reading...I'm coming along just fine. Loving it.  

**Link(s) to work**
1. https://twitter.com/jdhaliwal24/status/819868165014310912


### Day 1: January 12, Thursday

**Today's Progress**: Spent about 5 hours working on front-end features on new blog app project. Cleaned up bootstrap styling, fixed some routing, controller logic, and integrated this really cool gem called medium-editor which made implementing a text editor pretty painless.

**Thoughts**: It took MUCH longer than expected to get the front-end structure to behave the way I wanted it to, but I am somewhat satisifed with the fact that I can say after a few hours, the app is responsive. More work on routing/styling tomorrow. 

**Link(s) to work**
1. https://twitter.com/jdhaliwal24/status/819735989941698561




