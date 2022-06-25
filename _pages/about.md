---
layout: page
permalink: /
title: about
nav: about
years: [2022, 2021, 2019, 2015]
---

<!-- Introduction -->

<div style="display: flex; flex-wrap: wrap;">
    <div class="text-justify p-0">
        <div class="col-xs-12 col-sm-4 p-0 pt-2 pb-sm-2 pb-4 pl-sm-4 text-center" style="float: right;">
          <img class="profile-img img-responsive" src="{{ 'prof_pic2.jpg' | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}">
        </div>
        <h1 class="pb-3 title text-left font-weight-bold">Lei Xiong</h1>
        <p>
            <b>Postdoctorial Associate</b> <br>
            <b>Computer Science and Artificial Intelligence Laboratory (CSAIL) </b> <br> 
            <b>Massachusetts Institute of Technology (MIT) </b> <br>
            <b>Broad Institute of MIT and Harvard</b> <br>
        </p>
        <p> 
          Currently I am developing algorithms to learn the regulation mechanisms from epigenetics to transcriptomes with paired mulit-omics single-cell datasets after I joined Manolis Kellis Lab.
        </p>
        <p>
          My PhD research focuses on developing artificial intelligence tool for clustering single-cell ATAC-seq data to uncover gene regulation in cell heterogeneity <a href="https://github.com/jsxlei/SCALE" target="_blank"><b>(SCALE)</b></a> and online integration by projecting million-sized single-cell datasets onto the same batch-free biological embedding space via a generalized encoder <a href="https://github.com/jsxlei/SCALE" target="_blank"><b>(SCALEX)</b></a>. 
        </p>
        <p>
          I am also passionate about applying network analysis methods. Previously, I did some research in structural-protein-protein interaction (PPI) network to find out structural modules enriching cancer mutations and drug targets.
        </p>
        <p>
          Before I switched to computational, I had two years experimental experience in structure biology lab at USTC and Tsinghua when I was a undergraduate student. 
        </p>
        <p>
          I have a broad interest in applying cutting-edge artificial intelligence algorithms to solve biological questions.
        </p>
        <p>Feel free to reach out by email jsxlei at gmail.com or other social media listed above!
        </p>

    </div>
</div>


<!-- News -->
<div class="news mt-3 p-0">
  <h2 class="font-weight-bold">News</h2>
  {% assign news = site.news | reverse %}
  {% for item in news limit: site.news_limit %}
    <div class="row p-0">
      <div class="col-sm-2 p-0">
        <span class="badge light-blue darken-1 font-weight-bold text-uppercase align-middle date ml-3">
          {{ item.date | date: "%b %-d, %Y" }}
        </span>
      </div>
      <div class="col-sm-10 mt-2 mt-sm-0 ml-3 ml-md-0 p-0 font-weight-light text">
        <p>{{ item.content | remove: '<p>' | remove: '</p>' | emojify }}</p>
      </div>
    </div>
  {% endfor %}
</div>

<!-- publications -->
<div class="news mt-3 p-0">
  <h2 class="font-weight-bold">Publications</h2>
  {% for y in page.years %}
  <div class="row m-0 p-0" style="border-top: 1px solid #ddd; flex-direction: row-reverse;">
    <div class="col-sm-1 mt-2 p-0 pr-1">
      <h3 class="bibliography-year">{{y}}</h3>
    </div>
    <div class="col-sm-11 p-0">
      {% bibliography -f papers -q @*[year={{y}}]* %}   
    </div>
  </div>
  {% endfor %}
</div>

<!--  @*[selected=true]*   -->

<h2 class="font-weight-bold">Softwares</h2>
<div id="projects" class="row mt-2 pt-3" style="overflow: visible !important;">
  {% assign sorted_projects = site.projects | sort: "importance" | reverse %}
  {% for project in sorted_projects %}
    <div class="project-card">
      {% if project.redirect %}
        <a href="{{ project.redirect }}" target="_blank">
      {% else %}
        <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
      {% endif %}
        <div class="card">
          <img class="card-img-top" src="{{ project.img | prepend: site.baseurl | prepend: site.url }}" alt="project thumbnail">
          <div class="card-body">
            <h5 class="card-title">{{ project.title }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <div class="row ml-1 mr-1 p-0">
              {% if project.wordpress %}
                <div class="wordpress-icon" data-toggle="tooltip" title="Blog Post">
                  <div class="icon">
                    <a href="{{ project.wordpress }}" target="_blank"><i class="fab fa-wordpress-simple wp-icon"></i></a>
                  </div>
                </div>
              {% endif %}
              {% if project.github %}
                {% assign github_id = project.title | append: project.github | replace: '/', '-' | replace: ' ', '-' %}
                <div class="github-icon">
                  <div class="icon" data-toggle="tooltip" title="Code Repository">
                    <a href="https://github.com/{{ project.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
                  </div>
                </div>
              {% endif %}
            </div>
          </div>
        </div>
      </a>
    </div>
  {% endfor %}
</div>

<!-- Education-->
<div class="news mt-3 p-0">
  <h2 class="font-weight-bold">Education</h2>
    <div class="row p-0">
      <div class="col-sm-2 p-0">
        <span class="badge light-blue darken-1 font-weight-bold text-uppercase align-middle date ml-3">
          2015-2020
        </span>
      </div>
      <div class="col-sm-10 mt-2 mt-sm-0 ml-3 ml-md-0 p-0 font-weight-light text">
        <p><b>Tsinghua University</b> <br>
            <b>Ph.D. in Computational Biology</b> <br>
            <b>Advisor</b>: <a href="http://life.tsinghua.edu.cn/lifeen/info/1034/1075.htm" target="_blank"><b>Prof. Qiangfeng Cliff Zhang</b></a> <br>
            <b>Thesis</b>: Artificial intelligence method for single-cell ATAC-seq data via feature extraction
        </p>
      </div>
    </div>
    <div class="row p-0">
      <div class="col-sm-2 p-0">
        <span class="badge light-blue darken-1 font-weight-bold text-uppercase align-middle date ml-3">
          2011-2015
        </span>
      </div>
      <div class="col-sm-10 mt-2 mt-sm-0 ml-3 ml-md-0 p-0 font-weight-light text">
        <p><b>University of Science and Technology of China (USTC)</b> <br>
            <b>B.S. in Biology, Shitsan Pai Talent Program in Life Sciences </b><br>
            <b>Advisor</b>: <a href="https://molbio.princeton.edu/people/nieng-yan" target="_blank"><b>Prof. Nieng Yan</b></a> <br>
            <b>Thesis</b>: Structure basis and transport mechanism of membrane protein GLUT3
        </p>
      </div>
    </div>
</div>


<!-- Honors and Awards-->
<div class="news mt-3 p-0">
  <h2 class="font-weight-bold">Honors and Awards</h2>
  {% assign awards = site.awards | reverse %}
  {% for item in awards limit: site.awards_limit %}
    <div class="row p-0">
      <div class="col-sm-2 p-0">
        <span class="badge light-blue darken-1 font-weight-bold text-uppercase align-middle date ml-3">
          {{ item.date | date: "%Y" }}
        </span>
      </div>
      <div class="col-sm-10 mt-2 mt-sm-0 ml-3 ml-md-0 p-0 font-weight-light text">
        <p>{{ item.content | remove: '<p>' | remove: '</p>' | emojify }}</p>
      </div>
    </div>
  {% endfor %}
</div>
