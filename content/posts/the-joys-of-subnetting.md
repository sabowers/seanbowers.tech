---
title: "The Joys of Subnetting"
date: 2023-07-17T22:37:54-07:00
draft: true
---
I have been studying for my CompTIA Network+ certification exam. This is the one of the early career trifecta (A+, Network+, & Security+) that I had been hoping to avoid. I was hoping that I might be able to find a cybersecurity track job without needing the Network+, so I could forego that exam entirely. Now the exam itself may not be a necessary for getting into cybersecurity, however understanding networking in general *is* absolutely necessary. And not only that, my experience of trying to get into IT for the last five years, with a year since getting both my A+ and Security+, Network+ seems to be the most sought after of the three. So I begrudgingly got my exam voucher and began studying. 

Much to my surprise, I am finding the content to be deeply engaging. I am loving the deep dive into the inner workings of IP addressing and how packets of data move from one host to another. Much like the bulk of the Western world, I have also taken much of the internet for granted. I am enthralled how bits turn into frames, frames into packets, packets into segments, segments into sessions, how segments pass through layer 6 to set encoding, encryption, and compression; and finally how that is presented to the end-user on the output side. Why these exams are made to be taken in order makes a lot of sense. Of course, like the contrarian I can be at times, I took them third-first-second. But I kept looking at IPv4 and IPv6 addresses, MAC addresses, and the like and was intimidated. 

However, I that intimidation has since washed away after confidently learning how to manually subnet. I read numerous articles, watched a myriad of videos, only to come away scratching my head each time. I was convinced that I could never learn to do it. And that was when someone suggested (Practical Networking)[https://www.practicalnetworking.net/]. Specifically, I watched his video series, (Subnetting Mastery)[https://www.youtube.com/watch?v=BWZ-MHIhqjM&list=PLIFyRwBY_4bQUE4IB5c4VPRyDoLgOdExE], and it all came together. It stems from the concept of a subnetting "cheat sheet." This cheat sheet framework was not new to me, as I had seen (Professor Messer)[https://www.professormesser.com/] do it, as well as (Jason Dion)[https://www.diontraining.com/home]. Both of these great instructors give cheat sheet examples, but Practical Networking taught me **how** to make the cheat sheet. And in the understanding of how to make the cheat sheet, I began to understand how subnetting works from a mathematical and theoretical standpoint. And the best thing about all of it, unlike many aspects of tech certification exams, is that I don't need to memorize anything. I just have to remember which variable I am using and where, and with some practice, which was greatly enjoyable thanks to the achievement rush I was getting, I can now easily figure out the subnet of a given IP, when coupled with a CIDR suffix, the subnet ID, the broadcast IP, the first and last usable IP on the subnet, the beginning of the next, and the number of addresses available on that subnet.

# How to Make a Subnetting Cheat Sheet  

1. First, write out the decimal representation of each bit of a single 8bit byte.
  - 128     64      32      16      8       4       2       1  

2. Next, we want to subtract the bit decimal value from 256. 
  - 256     256     256     256     256     256     256     256 
    128     64      32      16      8       4       2       1 
    128     192     224     240     248     252     254     255  

3. This gives us our "magic number," as some people call it, as well as the remaining bits of our network from the default subnet mask. From here, we start a third row and write CIDR "slash-networks" from highest (/32) to lowest, from right to left. 
  - 128     64      32      16      8       4       2       1 
    128     192     224     240     248     252     254     255  
    /25     /26     /27     /28     /29     /30     /31     /32  
    /17     /18     /19     /20     /21     /22     /23     /24  
    /9      /10     /11     /12     /13     /14     /15     /16  
    /1      /2      /3      /4      /5      /6      /7      /8  

4. And here we have our subnetting cheat sheet. It might not make sense to you yet, so let's try to first put it into context.
  - "Magic Number":   128     64      32      16      8       4       2       1 
    Network bits  :   128     192     224     240     248     252     254     255 
    Fourth octet  :   /25     /26     /27     /28     /29     /30     /31     /32 
    Third octet   :   /17     /18     /19     /20     /21     /22     /23     /24 
    Second octet  :   /9      /10     /11     /12     /13     /14     /15     /16 
    First octet   :   /1      /2      /3      /4      /5      /6      /7      /8  

Now we begin to get a clearer picture. The first line, which is commonly known as the magic number, is going to act as a range of host IPs (this will make more sense later). The second line tells us how many more network bits are in our subnet from our default subnet mask according to the coordinating CIDR value. And then each subsequent line represents all of our CIDR notation possibilities and which octet of the byte we will be working with. 

I was originally taught the "magic number" method, via the adoption of this cheat sheet, but it wasn't until I was taught **how** to make the cheat sheet did any of it begin to be clearer to me. So let's try to put this cheat sheet to use with some examples. 



Since learning how to subnet using simple math and the drawing up sdfasdgasdg
