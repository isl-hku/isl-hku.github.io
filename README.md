# Lab Website Management Guide

This guide helps lab members update the website with new publications, member profiles, and news. No coding experience is required—follow the steps below!

## Adding/Updating Publications

Publications are managed through BibTeX files. Follow these steps to add new papers or update existing ones:

- Locate the BibTeX folder: Go to the _bibliography folder in the website repository.
  Choose the right file:

  - Add journal papers to journal.bib

  - Add preprints to journal.bib (with @misc type)

  - Add conference papers to conf.bib

  - Add patents to others.bib

- Format your entry: Use standard BibTeX format. 

Include a groups field to tag the paper with relevant keywords (e.g., groups = {computational imaging}).

You can also include fileds like note, website, github, and any other media report links. Here is an example:

```bibtex
@article{Doe2024,
  author = {Doe, John and Smith, Jane},
  title = {New Advances in Lensless Imaging},
  journal = {Optics Express},
  year = {2024},
  note = {Invited paper},
  award = {},
  groups = {lensless imaging},  <!-- Match one of the keywords in "By Key Words" tab -->
  project ={},
  code = {},
  news = {},
  eurekalert = {},
  wechat ={},
}
```

Commit your changes and push to the repository. The website will auto-update in 2 minutes.

## Creating Your Member Profile

  - Prepare your photo:
    Use a square headshot (e.g., 400x400 pixels)

  - Save it as firstname_lastname.jpg (e.g., john_doe.jpg)
    Upload it to the assets/images/member/

  - Create your profile file:

    - Go to the _team folder

    - Create a new file named firstname_lastname.md (match the photo filename!)
- Copy the template below and fill in your details:

---

```markdown
---
name: Your Full Name  <!-- e.g., "John Doe" -->
position: your role  <!-- e.g., "phdstudent", "postdoc", "researchstaff" -->
avatar: firstname_lastname.jpg  <!-- Match your photo filename -->
twitter: your_twitter_id 
avatar: xxxx.jpg
linkedin: xxxx <!-- ID only -->
email: 
scholar: https://scholar.google.com/citations?user=MvOSTcUAAAAJ
web: 
orcid: 0000-0000-0000-0000
github: xxx   <!-- ID only -->
joined: 2023  <!-- e.g., 2024 -->
left: ""
---


<i class="fa fa-building"></i> Your Office Location (e.g., "RIC 1481")
<br>

<hr>

### Bio

A short description of your background (e.g., education, previous research, interests). Keep it brief!

<hr>

### Research Interests

- Area 1 (e.g., "Computational imaging")
- Area 2 (e.g., "Deep learning for microscopy")
- Area 3

### Others

```

---

Save and push: Commit the new file and photo, then push to the repository. 

Your profile will appear on the "People" page automatically.



## Adding Lab News
Share lab updates, paper acceptances, conferences, or other announcements:
Steps:

- Open the news file: Go to _posts/
- Add a new md file, name it as YYYY-MM-DD-xxxxx  <!-- e.g., 2024-06-15 -->
- Upload banner image to the assets/images/post/

Example:

```markdown
---
layout: post
title: "some title"
description: 
categories: publication
header-img: banner.jpg
lang: en
---


Blablabla.....


| <img src="/assets/images/post/yyy.gif" width="70%"> |
| :--------------------------------------------------: |
|                 caption                  |
```


Save and push: Commit your changes. The news will appear on the homepage page.


## Final Notes

All changes go live automatically after pushing to the repository (no need for extra steps)

Double-check filenames (e.g., photo and profile filenames must match exactly)

For help, ask the lab website manager or check past entries as examples







