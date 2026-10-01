---
layout: page
title: Art
permalink: /art/
description: Photography and visual art.
nav: true
nav_order: 5
images:
  photoswipe: true
---

<p class="art-intro">
  I am drawn to moments when light changes the way ordinary things are seen. I photograph both natural and built environments, paying attention to how light creates patterns, reflections, textures, and shadows, and how these shifts can make familiar forms feel unexpectedly structured, quiet, or strange.
</p>

<style>
  .art-intro {
    max-width: 44rem;
    margin: 0 auto 3rem;
    line-height: 1.75;
    color: var(--global-text-color-light, #555);
    text-align: center;
  }
  .photo-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 6px;
  }
  .photo-grid a {
    display: block;
    aspect-ratio: 1;
    overflow: hidden;
    background: var(--global-bg-color);
  }
  .photo-grid a img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition: opacity 0.25s ease;
  }
  .photo-grid a:hover img {
    opacity: 0.88;
  }
  @media (max-width: 576px) {
    .photo-grid { grid-template-columns: repeat(2, 1fr); gap: 4px; }
  }
</style>

<div class="pswp-gallery photo-grid" id="art-gallery">

  <a href="/assets/img/art/selected/01-tunnel.jpg"
     data-pswp-width="1165" data-pswp-height="1536">
    <img src="/assets/img/art/selected/01-tunnel.jpg" loading="eager"
         alt="Black-and-white view from beneath a concrete tunnel, with patterned shadows and reflected light." />
  </a>

  <a href="/assets/img/art/selected/02-hydrangea.jpg"
     data-pswp-width="1373" data-pswp-height="1536">
    <img src="/assets/img/art/selected/02-hydrangea.jpg" loading="lazy"
         alt="White hydrangea blossoms selectively illuminated against deep shadow." />
  </a>

  <a href="/assets/img/art/selected/03-building-shadows.jpg"
     data-pswp-width="918" data-pswp-height="1307">
    <img src="/assets/img/art/selected/03-building-shadows.jpg" loading="lazy"
         alt="Tree shadows projected across a black-and-white building facade." />
  </a>

  <a href="/assets/img/art/selected/04-fog-beach.jpg"
     data-pswp-width="1536" data-pswp-height="1152">
    <img src="/assets/img/art/selected/04-fog-beach.jpg" loading="lazy"
         alt="A figure walking across a foggy beach between dark sea stacks." />
  </a>

  <a href="/assets/img/art/selected/05-parking-light.jpg"
     data-pswp-width="1536" data-pswp-height="1152">
    <img src="/assets/img/art/selected/05-parking-light.jpg" loading="lazy"
         alt="Sunlight cuts diagonally through a concrete parking structure." />
  </a>

  <a href="/assets/img/art/selected/06-water-leaves-bw.jpg"
     data-pswp-width="1000" data-pswp-height="1536">
    <img src="/assets/img/art/selected/06-water-leaves-bw.jpg" loading="lazy"
         alt="Black-and-white leaves floating over rippling water." />
  </a>

  <a href="/assets/img/art/selected/09-hosta.jpg"
     data-pswp-width="1536" data-pswp-height="1247">
    <img src="/assets/img/art/selected/09-hosta.jpg" loading="lazy"
         alt="Hosta leaves emerge from darkness, their ribs picked out by directional light." />
  </a>

  <a href="/assets/img/art/selected/10-glass-refraction.jpg"
     data-pswp-width="1397" data-pswp-height="1518">
    <img src="/assets/img/art/selected/10-glass-refraction.jpg" loading="lazy"
         alt="Close study of a glass of water — rim, waterline, refraction, and spectral highlights." />
  </a>

  <a href="/assets/img/art/selected/08-flowers-bw.jpg"
     data-pswp-width="1136" data-pswp-height="1175">
    <img src="/assets/img/art/selected/08-flowers-bw.jpg" loading="lazy"
         alt="Black-and-white flowers emerging from deep shadow." />
  </a>

</div>
