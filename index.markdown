---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

# layout: home
layout: default
---

<table>
  <tr>
    <td style="border: 1px solid transparent;">
      <p></p>
      <p></p>
    </td>
  </tr>
  {% assign categories = "introduction|소개,interview|인터뷰,fieldwork|답사,recipe|레시피,journal|일지,read|읽기" | split: ',' %}
  {% for category in categories %}
    {% assign category_split = category | split: '|' %}
    {% assign category_id = category_split[0] %}
    {% assign category_name = category_split[1] %}
    {% assign link = "posts-" | append: category_id %}
    {% assign category_posts = site.categories[category_id] %}
    <tr>
      <td style="border: 1px solid transparent;">
        <p>→ {{ category_name }}</p>
        <ul>
          {% for i in (0..4) %}
          {% assign post = category_posts[i] %}
          <li class="post-list-item-index">
            <a href="{{ post.url | relative_url }}">
              {{ post.title | escape }}
            </a>
          </li>
          {% endfor %}
          <li class="post-list-item-index">
            <a href="{{ link }}">더보기</a>
          </li>
        </ul>
      </td>
    </tr>
  {% endfor %}
</table>