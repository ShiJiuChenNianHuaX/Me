<h2 id="publications">Projects</h2>

{% for category in site.data.publications.main %}
<div class="category-section">
  <h3>{{ category.title }}</h3>
  
  <ol class="bibliography">
    {% for item in category.entries %}
    <li>
      <div class="pub-row">
        <div class="col-sm-3 abbr">
          {% if item.image %}
          <img src="{{ item.image }}" class="teaser img-fluid z-depth-1">
          {% endif %}
        </div>
        
        <div class="col-sm-9">
          <div class="title">{{ item.title }}</div>
          <div class="description">{{ item.description }}</div>
          
          <div class="links">
            {% if item.link %}
            <a href="{{ item.link }}" class="btn btn-sm">Demo</a>
            {% endif %}
          </div>
        </div>
      </div>
    </li>
    {% endfor %}
  </ol>
</div>
{% endfor %}
