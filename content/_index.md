+++
title = "STA course website template"
+++

This site provides an example of Hugo generated course website. It is designed to showcase the flexibility in page and file organization while demonstrating the nuances in implementation.

Folder structure and their URL rendering after https://courses.utstat.utoronto.ca/STA000

```
content
├── _index.md                       <-- /
├── lectures
│   ├── _index.md                   <-- /lectures
│   ├── week-1
│   │   ├── _index.md               <-- /lectures/week-1
│   │   ├── Lecture-1.pdf           <-- /lectures/week-1/Lecture-1.pdf
│   │   ├── lecture-1-data.txt      <-  /lectures/week-1/lecture-1-data.txt
│   │   ├── Monday.md               <-- /lectures/week-1/monday
│   │   ├── tuesday.md              <-- /lectures/week-1/tuesday
├── Assignments
│   ├── _index.md                   <-- /assignments
│   ├── homework-1
│   │   ├── _index.md               <-- /assignments/homework-1
│   │   ├── Project-1.pdf           <-- /assignments/homework-1/Project-1.pdf
│   │   ├── Answers
│   │   │   ├── _index.md           <-- /assignments/homework-1/answers
├── contact.md                      <-- /contact
├── img
│   └── logo.png
└── material 
    └── Markdown-Syntax.pdf
```

Might be good to know:

- URLs are case sensitive.
  - Folders and *.md names get converted to lower case by Hugo. Static files such as images, pdf, and txt do not. This means that
    - https://courses.utstat.utoronto.ca/sta000 does not render this site. STA000 in the URL must be capitalized.
    - folder and page names are turned to lower case in the url, eg page 'Monday.md' and folder 'Assignment' become 'monday' and 'assignment'.
    - Attachment names like Lecture-1.pdf retains its capitalization.
- Try using absolute path to refer to pages within the site, and using relative path for images and attachments.
  - Absolute path for static files may get converted to start at https://courses.utstat.utoronto.ca/ instead of https://courses.utstat.utoronto.ca/STA000/ causing broken links.
- If nested navigation menu is needed then order them by weight in the front matter -- between the "+++" lines at the top of each page.
  - Simple menu can be specified in hugo.toml
