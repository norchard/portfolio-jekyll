---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<div class='title'>
  <h1 id='intro'> I am a<span id='occupation' onClick='occupationClick(event)'> software engineer</span><br /> based in Brooklyn, currently working at <a href='http://mapbox.com' target='_blank'>Mapbox</a>.</h1>
</div>

<div id='posts'>
  <h2>Writing from my batch at the <a id='recurse' href='http://recursecenter.com' target='_blank'>Recurse Center</a>:</h2>
  <ul>
      {% for post in site.posts %}
          <li><a href='{{ post.url | relative_url }}'><strong>{{post.title}}</strong></a> - {{post.description}}</li>
      {% endfor %}
  </ul>
</div>
