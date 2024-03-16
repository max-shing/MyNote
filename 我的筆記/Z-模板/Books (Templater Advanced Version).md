---
<%*
let title = tp.file.title;
if (title.startsWith("未命名")) {
 title = await tp.system.prompt("E輸入書名");
 if(!title) return;
}
if (title == "") {
title = "未命名";
} else {
await tp.file.rename(title);
}
await tp.file.move("/41-書/" + title)
-%>
type: books
title: "[[<% title %>]]"
cover: 
author: '[[<% tp.system.prompt("Enter the author of the book")%>]]'
genre: <% tp.system.suggester(["fiction", "non-fiction"], ["fiction", "non-fiction"], true, 'genre')%>
status: <% tp.system.suggester(["done", "reading", "to-read"], ["done", "reading", "to-read"], true, 'status')%>
rating: 
myRating: 
summary: 
date_creation: <% tp.file.creation_date("YYYY-MM-DD") %>
date_start: 
date_finish:
---
## 3 sentences to describe the book(簡介)
1. <% tp.file.cursor() %>
2. 
3. 

## 5 take aways(帶走)
1. 
2. 
3. 
4. 
5. 

## Review(審查)



## Related(有關的)



## Reference(參考)




