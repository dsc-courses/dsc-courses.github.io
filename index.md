---
layout: minimal
title: UCSD Data Science Course Websites
nav_exclude: false
nav_order: 1
has_right_toc: true
---

# UCSD Data Science Course Websites
{:.no_toc}

This site contains course websites for many of the courses in and adjacent to UCSD's data science curriculum.

<!-- With any questions with this site, feel free to email TBD. -->

{: .red }
Note from Sam Lau: This is **not** intended to be used as a list of all courses that HDSI offers, and the information here may be out of date. In particular, I was only able to find websites for (most of) the undergraduate DSC courses, so all other course links will get more out-of-date as time goes on! If you want to fix the information for a course, please feel free to send a pull request to [the GitHub repo for this website][repo]. For official information about all of our course offerings, please refer to the [Undergraduate](https://datascience.ucsd.edu/current-students/course-descriptions-and-prerequisites/) and [Graduate](https://datascience.ucsd.edu/graduate/) program pages on the official HDSI website.

[repo]: https://github.com/dsc-courses/dsc-courses.github.io

<!-- A related list, compiled by Jason Fleischer, contains descriptions of [all ML/AI-adjacent courses at UCSD as of 2020/2021](https://docs.google.com/document/d/1kQeD_OQ_b2NcfkXBtmtQw4HNJ0lv-VDvj2Yz9SkVP1Q/edit#heading=h.ri0364kcpnnm). -->

**Site last updated: {{ site.time | date: "%b %Y" }}**

[Undergraduate DSC courses](#undergraduate-dsc-courses){: .btn .btn-blue } &nbsp;&nbsp;&nbsp; [Undergraduate COGS courses](#undergraduate-cogs-courses){: .btn .btn-green } &nbsp;&nbsp;&nbsp; [Graduate DSC courses](#graduate-dsc-courses){: .btn .btn-purple }

{% for module in site.modules %}

---
{{ module }}
{% endfor %}
