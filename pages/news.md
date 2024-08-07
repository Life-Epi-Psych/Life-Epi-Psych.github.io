---
layout: page
---

<style>
  /* Ensure cards have a consistent height */
  .card.fixed-card-size {
    display: flex;
    flex-direction: column;
    height: 400px; /* Fixed height for consistency */
    overflow: hidden; /* Prevent overflow */
    border: 1px solid #ddd; /* Optional: Add a border for better visibility */
  }

  /* Fixed height for the image container */
  .card-image {
    flex-shrink: 0;
    height: 200px; /* Fixed height for the image container */
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 1rem;
  }

  /* Ensure the image fits within the container while maintaining aspect ratio */
  .card-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  /* Ensure the content section fills the remaining space */
  .card-content {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    padding: 1rem;
  }

  /* Content area for title and excerpt */
  .card-content .media-content,
  .card-content .content {
    flex-grow: 1;
  }

  .card-content .content {
    overflow: hidden; /* Prevent overflow */
    text-overflow: ellipsis; /* Add ellipsis to overflow text */
    margin-top: auto; /* Push content to the bottom of the card */
  }

  /* Optional: Add some spacing between cards */
  .column {
    padding: 0.5rem;
  }
</style>

<section class="section">
  <div class="container">
    <h1 class="title">{{ "News" }}</h1>
    <div class="columns is-multiline">
      {% for post in site.posts %}
        <div class="column is-one-third">
          <div class="card fixed-card-size">
            <div class="card-image">
              <figure class="image">
                <img src="{{ post.image }}" alt="{{ post.title }}">
              </figure>
            </div>
            <div class="card-content">
              <div class="media">
                <div class="media-content">
                  <p class="title is-4"><a href="{{ post.url }}">{{ post.title }}</a></p>
                  <p class="subtitle is-6">{{ post.date | date: "%B %d, %Y" }}</p>
                </div>
              </div>
              <div class="content">
                {{ post.excerpt | strip_html | truncatewords: 28 }}
              </div>
            </div>
          </div>
        </div>
      {% endfor %}
    </div>
  </div>
</section>
