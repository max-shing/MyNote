---
<%*
let title = tp.file.title;
if (title.startsWith("未命名")) {
  title = await tp.system.prompt("新建筆記檔名", title);
  if (!title) return;
}
if (title == "") {
  title = "未命名";
} else {
  await tp.file.rename(title);
}
const aTags = ["blog", "yt-videos", "obsidian", "autohotkey", "windows"];
let tag = await tp.system.suggester(aTags, aTags);
if (tag == "yt-videos") {
  tag = "blog, yt-videos";
}
let random_picture = await tp.web.random_picture("1600x900", title+","+tag);
-%>
created: <% tp.file.creation_date() %>
aliases: [ <% title %> ]
tags: [ <% tag %> ]
---
# <% title %>

Modified:: <%+ tp.file.last_modified_date() %>

<% random_picture %>

<% tp.file.cursor(1) %>

## 相關連結
<% tp.file.cursor(2) %>


<%* if (tag.contains("yt-videos")) { %>
## 教學影片

<iframe width="650" height="315" src="https://www.youtube.com/embed/$$" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<%* } %>

＃＃