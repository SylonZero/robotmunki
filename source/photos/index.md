---
title: Photos
date: 2024-03-21
layout: page
---

<div class="gallery-grid">
  <img class="gallery-photo" src="/images/photo1.jpg" alt="Image Title 1">
  <img class="gallery-photo" src="/images/photo2.jpg" alt="Image Title 2">
  <img class="gallery-photo" src="/images/photo3.jpg" alt="Image Title 3">
</div>

<style>
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1rem;
  padding: 1rem 0;
}

.gallery-photo {
  width: 100%;
  height: 250px;
  object-fit: cover;
  cursor: pointer;
  transition: transform 0.2s;
}

.gallery-photo:hover {
  transform: scale(1.02);
}
</style> 