isbn::    {{isbn13}}
length::  {{totalPage}} pages
genre::   [[<%=book.category.toLowerCase()%>]]
year::    [[<%=book.publishDate.substring(0,4)%>]]
author::  <%=book.authors.map(author => `[[${author}]]`).join(', ').toLowerCase()%>
<% await tp.file.rename("{{title}}".toLowerCase()) %>
tags :: [[books]]

---

<%=book.description.toLowerCase()%>

![cover|200]({{coverUrl}})
