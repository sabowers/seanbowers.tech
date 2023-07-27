---
title: "How to Make a Subnetting Cheat Sheet"
date: 2023-07-27T15:08:50-07:00
draft: false
authors: [Sean Bowers]
description: "The Joys of Subnetting: Part Two"

tags: [subnet, ipv4, cidr, networking, TCP/IP]
categories: []
series: [The Joys Of Subnetting]

toc:
  enable: true
math:
  enable: false
lightgallery: false
license: ""
---

# How to Make a Subnetting Cheat Sheet  

1. First, write out the decimal representation of each bit of a single 8bit byte.  
| 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|-----|----|----|----|---|---|---|---|

2. Next, we want to subtract the bit decimal value from 256. 
| 256  | 256 | 256 | 256 | 256 | 256 | 256 | 256 |
|------|-----|-----|-----|-----|-----|-----|-----|
| -128 | -64 | -32 | -16 | -8  | -4  | -2  | -1  |
| 128  | 192 | 224 | 240 | 248 | 252 | 254 | 255 |

3. This gives us our "magic number," as some people call it, as well as the remaining bits of our network from the default subnet mask. From here, we can first get rid of the unnecessary 256s. Then we 
input our subnet CIDR notations, starting with the highest (/32) going right to left, picking back up on the right column when we run out of room, until we reach /1. 
| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
|-----|-----|-----|-----|-----|-----|-----|-----|
| 128 | 192 | 224 | 240 | 248 | 252 | 254 | 255 |
| /25 | /26 | /27 | /28 | /29 | /30 | /31 | /32 |
| /17 | /18 | /19 | /20 | /21 | /22 | /23 | /24 |
| /9  | /10 | /11 | /12 | /13 | /14 | /15 | /16 |
| /1  | /2  | /3  | /4  | /5  | /6  | /7  | /8  |

4. And here we have our subnetting cheat sheet. It might not make sense to you yet, so let's try to first put it into context.
| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   | "Magic Number" |
|-----|-----|-----|-----|-----|-----|-----|-----|----------------|
| 128 | 192 | 224 | 240 | 248 | 252 | 254 | 255 | Network Bits   |
| /25 | /26 | /27 | /28 | /29 | /30 | /31 | /32 | Fourth Octet   |
| /17 | /18 | /19 | /20 | /21 | /22 | /23 | /24 | Third Octet    |
| /9  | /10 | /11 | /12 | /13 | /14 | /15 | /16 | Second Octet   |
| /1  | /2  | /3  | /4  | /5  | /6  | /7  | /8  | First Octet    |

Now we begin to get a clearer picture. The first line, which is commonly known as the magic number, is going to act as a range of host IPs (this will make more sense later). The second line tells us how many more network bits are in our subnet from our default subnet mask according to the coordinating CIDR value. And then each subsequent line represents all of our CIDR notation possibilities and which octet of the byte we will be working with. 

I was originally taught the "magic number" method, via the adoption of this cheat sheet, but it wasn't until I was taught **how** to make the cheat sheet did any of it begin to be clearer to me. With learning how to write this cheat sheet through merely understanding bits and bytes and the formula, you will no longer need to rely on rote memorization and guessing. In the next few blog posts, we will go over how to use the cheat sheet, along with some examples to get more intimate with it. My hope is that this can become a working part of your everyday networking, as opposed to a daunting task that has to be overcome. Often times when bored, or needing to keep my hands busy, I just make up random IP addresses and subnets just as a fun puzzle. Then I sometimes check my work with a subnetting app or website. I hope you find as much joy in this as I have. 
