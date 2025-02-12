<h2 id="publications" style="margin: 2px 0px -15px;">Projects</h2>

<div class="publications">
  {% for category in site.data.publications.main %}
  <div class="category-block">
    <h3>{{ category.title }}</h3>
    <ol class="bibliography">
      {% for entry in category.entries %}
      {% assign parts = entry | split: "
      " %} <!-- 按换行符分割文本 -->
      <li>
        <div class="pub-row">
          <div class="col-sm-12">
            <!-- 显示带编号的标题（第一行） -->
            <div class="project-title">
              {{ parts[0] | markdownify | remove: '<p>' | remove: '</p>' }}
            </div>
            
            <!-- 显示详细内容（后续行） -->
            <div class="project-details">
              <ul>
                {% for line in parts offset:1 %} <!-- 跳过第一行 -->
                  {% assign trimmed_line = line | strip %}
                  {% if trimmed_line != "" %}
                    <li>{{ trimmed_line }}</li>
                  {% endif %}
                {% endfor %}
              </ul>
            </div>
          </div>
        </div>
      </li>
      {% endfor %}
    </ol>
  </div>
  {% endfor %}
</div>
