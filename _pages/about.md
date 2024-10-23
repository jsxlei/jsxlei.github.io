---
layout: page
permalink: /
title: about
nav: about
years: [2024, 2023, 2022, 2019, 2015]
---

<!-- Introduction -->

<div style="display: flex; flex-wrap: wrap;">
    <div class="text-justify p-0">
        <div id="sidebar" class="col-xs-12 col-sm-4 p-0 pt-2 pb-sm-2 pb-4 pl-sm-4 text-center" style="float: right;">
          <img class="profile-img img-responsive" src="{{ 'prof_pic2.jpg' | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}">
          <nav class="sidebar">
            <!-- <ul> -->
              <li class="font-weight-bold"><a href="/assets/pdf/CV_leixiong.pdf">Bio</a></li>
              <li class="font-weight-bold"><a href='#education'>Education</a></li>
              <li class="font-weight-bold"><a href='#news'>News</a></li>
              <li class="font-weight-bold"><a href='#publications'>Publications</a></li>
              <li class="font-weight-bold"><a href='#softwares'>Softwares</a></li>
              <li class="font-weight-bold"><a href='#honors and awards'>Honors and Awards</a></li>
            <!-- </ul> -->
          </nav>
        </div>
        <h1 class="pb-3 title text-left font-weight-bold">Lei Xiong</h1>
          <p>
            <b>Postdoctoral Scholar</b> <br>
            <b>Genetics </b> <br> 
            <b>Stanford University </b> <br>
          </p>
        <p> 
My research interests are centered on the development and application of innovative deep learning approaches to solve complex biological questions, with a primary focus on advancing our understanding of gene regulation and cellular diversity. To achieve this goal, I build models that can effectively capture and interpret complex features from biological datasets, which provides new insights into fundamental biological processes. Specifically, I will <b>Decipher Mechanisms of Macrophage Dynamics and Cellular Crosstalk in Cancer</b>. Through my work, I aim to drive significant advances in the field of single-cell multiomics and regulatory DNA sequence, which has the potential to contribute to a better understanding of human health and disease.
        </p>
        <p>
          Feel free to reach out by email <b>jsxlei at gmail.com</b> or other social media listed above!
        </p>
    </div>
</div>

<!-- Education-->
<div id="education" class="news mt-3 p-0">
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
            <b>Advisor</b>: Prof.<a href="http://life.tsinghua.edu.cn/lifeen/info/1034/1075.htm" target="_blank"><b>Qiangfeng Cliff Zhang</b></a> <br>
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
            <b>Advisor</b>: Prof.<a href="https://molbio.princeton.edu/people/nieng-yan" target="_blank"><b>Nieng Yan</b></a> <br>
            <b>Thesis</b>: Structure basis and transport mechanism of membrane protein GLUT3
        </p>
      </div>
    </div>
</div>

<!-- News -->
<div id="news" class="news mt-3 p-0">
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

<div id="publications" class="news mt-3 p-0">
  <h2 class="font-weight-bold">Publications</h2>
  <nobr><em><sup>*</sup></em></nobr> for equal authorship, <nobr><em><sup>#</sup></em></nobr> for corresponding authorship.
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

<!-- Software -->
<div id="software" class="news mt-3 p-0">
  <h2 class="font-weight-bold">Softwares</h2>
  <div id="softwares" class="row mt-2 pt-3" style="overflow: visible !important;">
    {% assign sorted_softwares = site.softwares | sort: "importance" | reverse %}
    {% for software in sorted_softwares %}
      <div class="project-card">
        {% if software.redirect %}
          <a href="{{ software.redirect }}" target="_blank">
        {% else %}
          <a href="{{ software.url | prepend: site.baseurl | prepend: site.url }}">
        {% endif %}
          <div class="card">
            <img class="card-img-top" src="{{ software.img | prepend: site.baseurl | prepend: site.url }}" alt="project thumbnail" height="150"/>
            <div class="card-body">
              <h5 class="card-title">{{ software.title }}</h5>
              <p class="card-text">{{ software.description }}</p>
              <p>
                <!-- <a href="https://github.com/{{ software.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a> -->
                <a href="https://github.com/jsxlei/{{ software.github }}/stargazers"><img src="https://img.shields.io/github/stars/jsxlei/{{ software.github }}?logo=GitHub&amp;color=yellow" alt="Stars"></a>
                <a href="https://pypi.org/software/{{ software.github }}"><img src="https://img.shields.io/pypi/v/{{ software.github }}.svg" alt="PyPI"></a>
                <a href="https://pepy.tech/software/{{ software.github }}"><img src="https://pepy.tech/badge/{{ software.github }}" alt="Downloads"></a>
              </p>
              <div class="row ml-1 mr-1 p-0">
                {% if software.wordpress %}
                  <div class="wordpress-icon" data-toggle="tooltip" title="Blog Post">
                    <div class="icon">
                      <a href="{{ software.wordpress }}" target="_blank"><i class="fab fa-wordpress-simple wp-icon"></i></a>
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
<div class="news mt-3 p-0">


<!-- Honors and Awards-->
<div id="honors and awards" class="news mt-3 p-0">
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
