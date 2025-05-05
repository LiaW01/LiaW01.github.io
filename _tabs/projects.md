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

{% assign project1 = site.posts | where: "title", "Optimizing Bike Rebalancing in NYC’s Citi Bike System with Reinforcement Learning" | first %}

{% assign project2 = site.posts | where: "title", "Detecting and Mitigating Implicit Bias in Analyst Role Descriptions" | first %}

{% assign project3 = site.posts | where: "title", "Probability of Default Prediction for Banca Massiccia" | first %}

{% assign project4 = site.posts | where: "title", "Mental Health Subscription Plan Recommender" | first %}

{% assign project5 = site.posts | where: "title", "Emergent Communication through Deep Learning" | first %}

{% assign project6 = site.posts | where: "title", "Optimizing Blackjack Strategies with Reinforcement Learning" | first %}

{% assign project7 = site.posts | where: "title", "Emotion Detection from Plain Text" | first %}

{% assign project8 = site.posts | where: "title", "Optimizing Movie Recommendation System" | first %}

{% assign project9 = site.posts | where: "title", "Exploring Global Salary Disparities" | first %}

{% assign project10 = site.posts | where: "title", "Analyzing Music Popularity and Recommendations With Spotify Data" | first %}

{% assign project11 = site.posts | where: "title", "Identifying Anomalous Transactions" | first %}

{% assign project12 = site.posts | where: "title", "Time-Series Analysis on US Candy Production" | first %}

{% assign project13 = site.posts | where: "title", "Countries’ Sustainability Exploratory Data Analysis" | first %}


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


    <!-- Project 4 -->
    <div class="card">
      <a href="{{ project4.external_link | default: project4.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project4.cover }}" alt="{{ project4.title }}">
      <div class="card-content">
        <h3>{{ project4.title }}</h3>
        <div class="meta">Category: {{ project4.category }}</div>
        <p>{{ project4.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project4.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project4.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project4.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>


    <!-- Project 5 -->
    <div class="card">
      <a href="{{ project5.external_link | default: project5.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project5.cover }}" alt="{{ project5.title }}">
      <div class="card-content">
        <h3>{{ project5.title }}</h3>
        <div class="meta">Category: {{ project5.category }}</div>
        <p>{{ project5.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project5.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project5.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project5.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

    <!-- Project 6 -->
    <div class="card">
      <a href="{{ project6.external_link | default: project6.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project6.cover }}" alt="{{ project6.title }}">
      <div class="card-content">
        <h3>{{ project6.title }}</h3>
        <div class="meta">Category: {{ project6.category }}</div>
        <p>{{ project6.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project6.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project6.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project6.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

    <!-- Project 7 -->
    <div class="card">
      <a href="{{ project7.external_link | default: project7.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project7.cover }}" alt="{{ project7.title }}">
      <div class="card-content">
        <h3>{{ project7.title }}</h3>
        <div class="meta">Category: {{ project7.category }}</div>
        <p>{{ project7.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project7.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project7.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project7.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

    <!-- Project 8 -->
    <div class="card">
      <a href="{{ project8.external_link | default: project8.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project8.cover }}" alt="{{ project8.title }}">
      <div class="card-content">
        <h3>{{ project8.title }}</h3>
        <div class="meta">Category: {{ project8.category }}</div>
        <p>{{ project8.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project8.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project8.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project8.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

    <!-- Project 9 -->
    <div class="card">
      <a href="{{ project9.external_link | default: project9.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project9.cover }}" alt="{{ project9.title }}">
      <div class="card-content">
        <h3>{{ project9.title }}</h3>
        <div class="meta">Category: {{ project9.category }}</div>
        <p>{{ project9.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project9.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project9.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project9.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

    <!-- Project 10 -->
    <div class="card">
      <a href="{{ project10.external_link | default: project10.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project10.cover }}" alt="{{ project10.title }}">
      <div class="card-content">
        <h3>{{ project10.title }}</h3>
        <div class="meta">Category: {{ project10.category }}</div>
        <p>{{ project10.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project10.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project10.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project10.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

    <!-- Project 11 -->
    <div class="card">
      <a href="{{ project11.external_link | default: project11.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project11.cover }}" alt="{{ project11.title }}">
      <div class="card-content">
        <h3>{{ project11.title }}</h3>
        <div class="meta">Category: {{ project11.category }}</div>
        <p>{{ project11.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project11.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project11.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project11.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

    <!-- Project 12 -->
    <div class="card">
      <a href="{{ project12.external_link | default: project12.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project12.cover }}" alt="{{ project12.title }}">
      <div class="card-content">
        <h3>{{ project12.title }}</h3>
        <div class="meta">Category: {{ project12.category }}</div>
        <p>{{ project12.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project12.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project12.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project12.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>

    <!-- Project 13 -->
    <div class="card">
      <a href="{{ project13.external_link | default: project13.url }}" class="card-link" target="_blank" rel="noopener noreferrer"></a>
      <img src="{{ project13.cover }}" alt="{{ project13.title }}">
      <div class="card-content">
        <h3>{{ project13.title }}</h3>
        <div class="meta">Category: {{ project13.category }}</div>
        <p>{{ project13.excerpt | strip_html | truncate: 100 }}</p>
        <div class="tags">
          {% for tag in project13.tags %}
            {% unless tag == "project" %}
              <span class="tag">{{ tag }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% if project13.repo %}
          <div class="card-footer">
            <a class="btn" href="{{ project13.repo }}" target="_blank">GitHub Repo</a>
          </div>
        {% endif %}
      </div>
    </div>


  </div>
</div>
