---
layout: blank
title: "Decentralized Finance"
permalink: /f24_syllabus
---

<table style="table-layout: fixed; font-size: 88%;">
  <thead>
      <th style="width: 10%;"> <i>Date</i> </th>
      <th style="width: 20%;"> Quiz<br>(Due by <i>Date</i>) </th>
      <th style="width: 40%;"> Asynchronous Lecture Video<br>(Watch by <i>Date</i>) </th>
      <th style="width: 30%;"> Synchronous Lecture<br>(At 10:00 AM on <i>Date</i>) </th>
  </thead>
  <tbody>
    {% for row in site.data.f24syllabus %}
    <tr>
      <td> {{ row.date }} </td>
      <td>
        {% if row.quiz %}
          {% if row.quiz.name == "None" %}
          None
          {% else %}
          <a target="_parent" href="{{row.quiz.link}}" style="text-decoration: underline;">{{row.quiz.name}}</a>
        {% else %}
          TBD
        {% endif %}
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
        {% if row.reading %}
        <ul style="margin-bottom: 0;">
          {% for r in row.reading %}
            {% if r.file %}
              {% assign reading_link = 'https://berkeley-defi.github.io/assets/material/' | append: r.file %}
            {% endif %}
            {% if r.link %}
              {% assign reading_link = r.link %}
            {% endif %}
          <li> <a target="_parent" href="{{reading_link}}" style="font-size: 80%;"> Reading: {{ r.name }} </a> </li>
          {% endfor %}
        </ul>
        {% endif %}
      </td>
      <td>
        {% if row.ama %}
          {{row.ama}}
          {% if row.recording %}
            <br><a target="_parent" href="{{row.recording}}" style="text-decoration: underline;">Watch Recording</a>
          {% endif %}
        {% else %}
          TBD
        {% endif %}
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>
