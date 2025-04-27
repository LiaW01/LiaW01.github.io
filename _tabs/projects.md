---
layout: default
icon: fas fa-archive
permalink: /projects/
order: 1
---

<style>
.cards-container {
  display: flex;
  justify-content: center;
}

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(360px, 1fr));
  gap: 30px;
  max-width: 800px;
  padding: 20px;
}
/* original card setting
.card {
  display: flex;
  flex-direction: column;
  background: #fff;
  border: 1px solid #ddd;
  border-radius: 16px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.05);
  overflow: hidden;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  text-decoration: none;
  color: inherit;
}


.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 20px rgba(0,0,0,0.1);
}
*/

.card {
  display: flex;
  flex-direction: column;
  background: var(--card-bg); /* ✅ use CSS variable */
  border: 1px solid var(--main-border-color); /* ✅ use dark/light dynamic color */
  border-radius: 16px;
  box-shadow: var(--card-shadow); /* ✅ use dynamic shadow */
  overflow: hidden;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  text-decoration: none;
  color: var(--text-color); /* ✅ use dynamic text color */
}

.card:hover {
  background: var(--card-hovor-bg); /* ✅ slightly lighter background on hover */
}

.card-link {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 10;
}

/* Make content clickable second priority
.card-content, .card-footer {
  position: relative;
  z-index: 20;
}
*/

.card img {
  width: 100%;
  height: 240px;
  object-fit: cover;
}

.card-content {
  padding: 20px;
}

.card h3 {
  margin-top: 0;
  font-size: 1.2em;
  margin-bottom: 8px;
  display: flex;
  align-items: center;
  gap: 6px;
}

.card p {
  font-size: 0.95em;
  margin-bottom: 10px;
  color: #555;
}

.card .meta {
  font-size: 0.85em;
  color: #888;
  margin-bottom: 10px;
}

.tag {
  border-radius: 0.7em;
  padding: 6px 8px 7px;
  margin-right: 0.8rem;
  line-height: 3rem;
  letter-spacing: 0;
  border: 1px solid var(--tag-border) !important;
  box-shadow: 0 0 3px 0 var(--tag-shadow);

  span {
    margin-left: 0.6em;
    font-size: 0.7em;
    font-family: Oswald, sans-serif;
  }
}

#tags {
  @include bp.lt(bp.get(lg)) {
    justify-content: center !important;
  }
}
</style>


{% assign project1 = site.posts | where: "title", "Optimizing Blackjack Strategies with Reinforcement Learning" | first %}
{% assign project2 = site.posts | where: "title", "Probability of Default Prediction for Banca Massiccia" | first %}
{% assign project3 = site.posts | where: "title", "Identifying Anomalous Transactions" | first %}

<div class="cards-container">
  <div class="cards">

    <!-- Project 1 -->
    <div class="card">
      <a href="{{ project1.url }}" class="card-link"></a>
      <img src="{{ project1.cover }}" alt="{{ project1.title }}">
      <div class="card-content">
        <h3>{{ project1.title }}</h3>
        <div class="meta">Category: {{ project1.category }}</div>
        <p>{{ project1.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project1.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project1.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project1.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

    <!-- Project 2 -->
    <div class="card">
      <a href="{{ project2.url }}" class="card-link"></a>
      <img src="{{ project2.cover }}" alt="{{ project2.title }}">
      <div class="card-content">
        <h3>{{ project2.title }}</h3>
        <div class="meta">Category: {{ project2.category }}</div>
        <p>{{ project2.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project2.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project2.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project2.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

    <!-- Project 3 -->
    <div class="card">
      <a href="{{ project3.external_link | default: project3.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project3.cover }}" alt="{{ project3.title }}">
      <div class="card-content">
        <h3>{{ project3.title }}</h3>
        <div class="meta">Category: {{ project3.category }}</div>
        <p>{{ project3.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project3.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project3.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project3.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

  </div>
</div>
