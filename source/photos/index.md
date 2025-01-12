---
title: Photos
date: 2024-03-21
layout: page
---

<div class="gallery-grid">
  <img class="gallery-photo" src="../images/photo-1.jpg" alt="Prospect Park 1">
  <img class="gallery-photo" src="../images/photo-2.jpg" alt="Prospect Park 2">
  <img class="gallery-photo" src="../images/photo-3.jpg" alt="Prospect Park 3">
</div>

<!-- Lightbox container -->
<div id="lightbox" class="lightbox" style="display: none;">
  <span class="close">&times;</span>
  <img id="lightbox-img" class="lightbox-content">
  <div class="caption"></div>
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

/* Lightbox styles */
.lightbox {
  display: none;
  position: fixed;
  z-index: 999;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.9);
  padding: 2rem;
}

.lightbox-content {
  margin: auto;
  display: block;
  max-width: 90%;
  max-height: 90vh;
  object-fit: contain;
}

.close {
  position: absolute;
  right: 35px;
  top: 15px;
  color: #f1f1f1;
  font-size: 40px;
  font-weight: bold;
  cursor: pointer;
}

.caption {
  margin: auto;
  display: block;
  width: 80%;
  max-width: 700px;
  text-align: center;
  color: #ccc;
  padding: 10px 0;
  height: 150px;
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const lightbox = document.getElementById('lightbox');
  const lightboxImg = document.getElementById('lightbox-img');
  const caption = document.querySelector('.caption');
  
  // Open lightbox
  document.querySelectorAll('.gallery-photo').forEach(img => {
    img.onclick = function() {
      lightbox.style.display = 'flex';
      lightboxImg.src = this.src;
      caption.textContent = this.alt;
    }
  });
  
  // Close lightbox
  document.querySelector('.close').onclick = function() {
    lightbox.style.display = 'none';
  }
  
  // Close on outside click
  lightbox.onclick = function(e) {
    if (e.target === lightbox) {
      lightbox.style.display = 'none';
    }
  }
  
  // Close on escape key
  document.addEventListener('keydown', function(e) {
    if (e.key === 'Escape' && lightbox.style.display === 'flex') {
      lightbox.style.display = 'none';
    }
  });
});
</script> 