---
layout: page
title: Lectures
permalink: /lectures/
---
> Worksheet template can be found [here](static_files/docs/WorkSheetAnswerTemplate.pdf)


> 🆕 Students in track1 can signup to take notes [here](https://www.signupgenius.com/go/10C0D48ADAB22A1F9C70-note) and students in track2 can sign up [here](https://www.signupgenius.com/go/10C0D48ADAB22A1F9C70-note1). After signing up, please use [this](https://www.overleaf.com/latex/templates/iust-student-course-note-template/pgcyqhkkxcqr) LaTeX template in overleaf for the notes (zip version also available [here](static_files/Notes_Template.zip). You can either edit in overleaf or download MikTeX and TeXStudio on your computer. I recommend the latter. Please make sure you edit only what is needed in main.tex and write your notes in session.tex. Since we integrate all notes into a signle document, it is best not to modify any other files. Please remove any image/codefile/... you are not using. When you are done, please share your notes through an overleaf project, or send me a zipped version of the TeX files along with the PDF.


<ul id="archive">
{% for lecture in site.lectures reversed %}
<li class="archiveposturl" style="background: transparent">
<div class="lecture-container">
    {% if lecture.thumbnail %}
    <div class="thumbnail">
      <div class="center-cropped" style="margin-top:5px;margin-bottom:5px;background-image: url('{{ lecture.thumbnail | prepend: site.baseurl }}');">
        <img src="{{ lecture.thumbnail | prepend: site.baseurl }}"/>
      </div>
    </div>
    {% endif %}
    <div class="content">
        <span><a href="
            {% if lecture.slides contains '://' %}
              {{ lecture.slides }} 
            {% else %}
              {{ lecture.slides | prepend: site.baseurl }} 
            {% endif %}">{{ lecture.title }}</a>
            </span><br>

       {% if lecture.tldr %}
            <strong>tl;dr:</strong> 
            {{ lecture.tldr }}
            <br/>
        {% endif %}

        {% if lecture.notetaker %}
            <strong>Note Taker:</strong>
            <span style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif; font-size:12pt;">{{ lecture.notetaker }}</span>
            <br/>
        {% endif %}

        <strong>
            {% include lecture_links.html lecture=lecture %}
        </strong>        
    </div>
</div>
</li>
{% endfor %}
</ul>