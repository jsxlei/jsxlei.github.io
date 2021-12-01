---
layout: page
permalink: /
title: about
nav: about
---
<!-- <a class="page-description" target="_blank">Computational Biology</a> • <a href="http://life.tsinghua.edu.cn/" class="page-description" target="_blank">School of Life Sciences</a> • <a href="http://tsinghua.edu.cn/" class="page-description" target="_blank">Tsinghua University</a>
address: <a href="https://www.google.com/maps/place/Biology+Building+of+Hall/@40.0027011,116.3177901,16z/data=!4m8!1m2!2m1!1z5riF5Y2O5aSn5a2mIOeUn-eJqeWMu-Wtpummhg!3m4!1s0x35f056a19b14bb3b:0xe54d0d0aeaf8c544!8m2!3d40.003354!4d116.31989?hl=en" class="page-description" target="_blank">Biomedical Building, Tsinghua University, Haidian District, Beijing, China</a> -->

<div class="col p-0 pt-4 pb-4">
  <h1 class="pb-3 title text-left font-weight-bold">Lei Xiong</h1>
  <h6 class="m-0 mb-2" style="font-size: 0.83em;">{{ page.description }}</h6>
  {% if page.address %}
      <h6 class="m-0 mb-2" style="font-size: 0.83em;">{{ page.address }}</h6>
  {% endif %}
</div>

<!-- Introduction -->

<div style="display: flex; flex-wrap: wrap;">
    <div class="text-justify p-0">
        <div class="col-xs-12 col-sm-6 p-0 pt-2 pb-sm-2 pb-4 pl-sm-4 text-center" style="float: right;">
          <img class="profile-img img-responsive" src="{{ 'prof_pic.jpg' | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}">
        </div>
        <p>
            I currently am a Postdoctorial Associate in Computer Science and Artificial Intelligence Laboratory (CSAIL) at the Massachusetts Institute of Technology (MIT), working with Prof. Manolis Kellis at <a href="http://compbio.mit.edu/" target="_blank" >MIT Compuatational Biology Lab</a>.

        </p>
        <p>
            I recieved my Ph.D. in Computational Biology at Tsinghua University and graduated with a B.A. in Biology at University of Science and Technology of China. 
        </p>

        <p>
            I have a broad interest in applying artificial intelligence algorithm to solve biological questions, especially focus on single-cell genomics.
        </p>
    </div>
</div>


<!-- News -->
<div class="news mt-3 p-0">
  <h1 class="title mb-4 p-0">News</h1>
  {% assign news = site.news | reverse %}
  {% for item in news limit: site.news_limit %}
    <div class="row p-0">
      <div class="col-sm-2 p-0">
        <span class="badge light-green darken-1 font-weight-bold text-uppercase align-middle date ml-3">
          {{ item.date | date: "%b %-d, %Y" }}
        </span>
      </div>
      <div class="col-sm-10 mt-2 mt-sm-0 ml-3 ml-md-0 p-0 font-weight-light text">
        <p>{{ item.content | remove: '<p>' | remove: '</p>' | emojify }}</p>
      </div>
    </div>
  {% endfor %}
</div>

<!-- Selected publications -->
<div class="news mt-3 p-0">
  <h1 class="title mb-4 p-0">Research</h1>
  {% bibliography -f papers -q @*[selected=true]* %}
</div>
