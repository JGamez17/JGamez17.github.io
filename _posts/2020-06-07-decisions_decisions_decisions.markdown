---
layout: post
title:      "Decisions, decisions, decisions …"
date:       2020-06-08 02:27:47 +0000
permalink:  decisions_decisions_decisions
---


## Ruby Conditionals 
In everyday life we make decisions that are a result of certain conditions. For example, if you are cold then you will put on a sweater, if you are sleepy, then you will go to sleep. In programming language our programs will also have to perform tasks if certain conditions are met. These conditions control the flow of our program and play an important role. 
	In Ruby our programs make decisions by using conditionals. Conditionals are keywords such as if, else, and elsif that guide the flow of a program. The keyword if acts as a question and if the answer to that question returns true then the code gets executed. If the answer to this question returns false or nil then nothing is done or our code continues to the next condition. There are many types of conditions that can be met and to help code those conditions Ruby has different symbols that can be used for different meanings. Some symbols and their meanings are are follows:
Source: https://www.rubyguides.com/ruby-tutorial/ruby-if-else/
So to check if something is true in Ruby language we use the if statement. To have our program check if this is NOT true then do something else we use the else statement. For example:

	if stock < 1
	   puts “Sorry we are out of stock!”
	else 
	   puts “Thanks for your order!”
	end 
	
Finally, to take things one step further you can use an elsif statement. When using elsif this keyword tests for another condition if and only if the previous condition has not been met. The keyword elsif can be used multiple times in our program. 

