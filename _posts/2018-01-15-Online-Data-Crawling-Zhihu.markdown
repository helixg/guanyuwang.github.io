---
layout: post
title:  Online Data Crawling:Zhihu
date:   2018-01-15 23:42:09.000000000 +0800
comments: true
---

> Data in the 21st Century is like Oil in the 18th Century: an immensely, untapped valuable asset.
> ——Wired.com

To analysis the online sciety, we must acquire enough raw data. The best way is asking the owner of the dataset. If that is impossible, we may need to craw them bare-handed!

## What is Zhihu 
Zhihu is a Chinese question-and-answer website where questions are created, answered, edited and organized by the community of its users. Its [website](zhihu.com), was launched on January 26, 2011. The number of registered users of Zhihu had exceeded 100 million by the end of 2017 with 25 million DAU(daily active user).

How to Get the Data

The Zhihu developed an unpublished API allowing users  to crawl the data. A anonymous user named @7sDream found it few months ago. By using this API, I can crawl raw data from Zhihu.com.

Excited!

## Project Description

1. Login and locate the target data
1. Crawl the raw data 
1. Download the data

## "Meat"
### Step 1
After several importing procedure, let's login!

```
client = ZhihuClient()
client.login_in_terminal('********.com', '*******') 
```
I hided my User ID and password.We need to tpye the captcha...

```
Need for a captcha, getting it......
Please open /Users/apple/Desktop/demo/captcha.gif for captcha
captcha: 6hn8
Login success.
```
Done!


Take [如何看待范美忠？](https://www.zhihu.com/question/20121142) as an example. The question ID is 20121142.

In this mission, I want to get all the answers in this question. The data should contain the following few variables.
The author name; the answer content; the timestmp and the voting status of the answer.

### Step 2

After typing few lines of simple codes
.... Done!

Show a few examples below:

```[{'No.': 1,
  'author': '范臻',
  'author_id': '599f7ab18e9a2b25d748fecfeada4620',
  'comment_num': 303,
  'content': '<p>我不知道你们怎么看待，反正我不喜欢作为老师的他。</p><p>08年地震的时候，我高三，在灵宝上学。</p><p>那天下午两点左右，我们一班人从宿舍来到教室，下午的第一堂是政治课，政治老师，是一名年轻...</b></p>',
  'time': 1431663578,
  'vote': 1631},
 {'No.': 2,
  'author': '王星鈦',
  'author_id': '4907d096932d3a393df378dfaae34c45',
  'comment_num': 0,
  'content': '不以道德来强求别人，不代表有道德就是错的了，更不是要把缺乏道德的人没有勇气的人捧为反道德反传统的英雄甚至是自由的象征。自由从来都是有勇气的人争取来的，不是逃跑逃来的、下跪跪来的。 '
```

I save the data in a Python row. This is not the end because the row just remain in the RAM when the computer still on. Thus I need to save the data to my Disc.

### Step 3 
Firstly, I need to convert the row to a Pandas DataFrame. 
`df1 = pd.DataFrame(rows1)`

Double check

`df`
![](https://ws1.sinaimg.cn/large/006tKfTcgy1ft575m57m5j31jc0sw15b.jpg)

Seemingly no mistake. Let's save it to the disc.
`df1.to_csv('./zhihu_demo',encoding='utf-8',index=False)`

Mission accomplish!

No matter which kind of research do you want to take on. No matter how you want to analysis them(topic modeling; word embedding etc),data,always plays a vital role in your project.




