+++
title = 'Automatically Create a task using Shortcuts'
date = 2025-01-22T12:23:34+09:00
draft = false
tags = ['productivity']
+++

## Problem
I want to use the ios reminders app more extensively but creating reminders is annoying. Especially when you have to type out everything and manually select the date even when the text is provided via mail.

## Solution

Created a shortcut that recieves text, parses the selected text into three parts: title, description, and date(+time)
and takes the parsed result to create a reminder. Most of the logic can be reused for creating calendar events as well.

GPT prompt: Give me three lines. First Line, only include an appropriate title. Second Line, give me a brief description. Third Line, try to parse the date and time in short format. DO NOT make a key-value list, just the values on each line. DO NOT include markdown formatting.

### Example

selected text:
```
remember to go to the hospital at 6am day after tomorrow.
```
parsed output (using chatGPT):
```
Reminder: Hospital Visit  
You need to go to the hospital at 6am day after tomorrow.  
2025-01-24 06:00
```

## Conclusion
ChatGPT is very good at parsing relevent data when given a block of text although you do need to go through some trial and error to get it in the format you need.
Creating a shorcut isn't the best 'development' experience as the documentation for shorcut actions is quite lacking and dragging and dropping blocks on an iphone is time consuming.
With that being said, it would take a lot more time trying to create an app of some kind for a simple functionality like this.
All in all, despite its limitations, using the shorcuts app was quite a fun experience and I was pleasently surprised by its capabilities.

## Troubleshooting
- After splitting text using the Split Text shortcut, you need to use the Get Item from List shortcut to actually use the individual values
- The Show Result shorcut can be used for debugging purposes (sort of like adding print statements for debugging; not perfect but it works)