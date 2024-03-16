---
type(類型): books
title(標題): "[[<% tp.file.title %>]]"
cover(封面): 
author(作者):
  - '[[<% tp.system.prompt("请输入作者")%>]]'
genre(分類): <% tp.system.suggester(["fiction", "non-fiction"], ["fiction", "non-fiction"], true, 'genre')%>
status(狀態): <% tp.system.suggester(["to-read", "reading", "done"], ["to-read", "reading", "done"], true, 'status')%>
rating(評分): 
myRating(我的評級): 
summary(總結): 
date_creation(建立日期): <% tp.file.creation_date("YYYY-MM-DD") %>
date_start(開始日期): 
date_finish(日期完成):
---
## 3 sentences to describe the book(簡介)
1. 
2. 
3. 

## 5 take aways(帶走)
1. 
2. 
3. 
4. 
5. 

## Review(審查)
<% tp.file.cursor() %>


## Related(有關的)



## ## Reference(參考)
