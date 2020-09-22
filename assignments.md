---
layout: page
title: Assignments
permalink: /assignments/
---

Use [**this**](../static_files/docs/AzureDevOpsAccount.pdf) guide to create Azure DevOps account. Next create a project named AI99001 and finall use [**this**](../static_files/docs/AdminAccess.pdf) guide to give me and TAs admin access.  

> ⚠ When following the guides above, make sure you use your own **student id** and use **AI99001** for project name. Also do not forget to add the **TA Account** as indicated in the guide.

## *Setup*
After setting up Azure DevOps and cloning it on your computer make sure you initialize your repository with ".gitignore" file and README.md. Include your full name and student ID in the README.md file. Further instruction for setting up your repository will follow soon.


<ul id="archive">
{% for asg in site.assignments reversed %}
      <li class="archiveposturl" style="background: transparent">
        <span><a href="{{ asg.url | prepend: site.baseurl}}">{{ asg.title }}</a></span>
<strong style="font-size:100%; font-family: 'Titillium Web', sans-serif; float:right">
<a title="Download problems (pdf)" href="{{ asg.pdf | prepend: site.baseurl }}"><i class="fas fa-file-pdf"></i></a> 
{% if asg.attachment %}
&nbsp; <a title="Download attachments (zip)" href="{{ asg.attachment | prepend: site.baseurl }}"><i class="fas fa-file-archive"></i></a>
{% endif %}
</strong> 
      </li>
{% endfor %}
</ul>