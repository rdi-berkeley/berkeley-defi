---
layout: blank
title: "Decentralized Finance"
permalink: /f22_syllabus
---

<table style="table-layout: fixed; font-size: 88%;">
  <thead>
      <th style="width: 10%;"> <i>Date</i> </th>
      <th style="width: 20%;"> Quiz<br>(Due by <i>Date</i>) </th>
      <th style="width: 40%;"> Asynchronous Lecture Video<br>(Watch by <i>Date</i>) </th>
      <th style="width: 30%;"> Synchronous AMA<br>(At 10:00 AM on <i>Date</i>) </th>
  </thead>
  <tbody>
    {% for row in site.data.f22syllabus %}
    <tr>
      <td> {{ row.next }} </td>
      <td>
        {% if row.quiz %}
          <a target="_parent" href="{{row.quiz.link}}" style="text-decoration: underline;">{{row.quiz.name}}</a>
        {% else %}
          TBD
        {% endif %}
      </td>
      <td> {{ row.topic }}
        <br>
        {% if row.youtube_premiere %}
          [<a target="_parent" href="{{row.youtube_premiere}}" style="font-size: 80%;text-decoration: underline;">Premiere</a>]
        {% endif %}
        {% if row.youtube_playlist %}
          [<a target="_parent" href="{{row.youtube_playlist}}" style="font-size: 80%;text-decoration: underline;">Playlist</a>]
        {% endif %}
        {% if row.slides %}
        <ul style="margin-bottom: 0;">
          {% for s in row.slides %}
          <li> <a target="_parent" href="https://rdi.berkeley.edu/berkeley-defi/assets/material/{{s.file}}" style="font-size: 80%;"> Slides: {{ s.name }} </a> </li>
          {% endfor %}
        </ul>
        {% endif %}      
      </td>
      <td>
        {% if row.ama %}
          {{row.ama}}
        {% else %}
          TBD
        {% endif %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>
