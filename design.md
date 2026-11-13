---
title: Project Design
permalink: /design/
# Paste the share link from screencast.com here.
video: https://app.screencast.com/Vl1qsPT5BOw3l
# A picture or short video of your design. Upload it to assets/images first.
schematic: /assets/images/schematic.mp4
# Optional one-line caption under the schematic.
schematic_caption:
---

Ember is our remote-controlled robot that fights fires at campsites. Ember's best
trick: stopping fires before they start!

<style>
  .design-figure { margin: 0 0 1rem; text-align: center; }
  .design-figure img,
  .design-figure video { display: block; max-width: 100%; margin: 0 auto; }
  .design-figure video { max-width: 480px; width: 100%; }
  .design-figure figcaption { font-size: 0.9em; color: var(--text-muted); margin-top: 0.5rem; }
  /* The shared theme sets iframe { height: auto }, which collapses a bare iframe.
     Wrap the player in a 16:9 box and fill it. */
  .design-video { aspect-ratio: 16 / 9; width: 100%; margin: 0 0 0.75rem; }
  .design-video iframe { width: 100%; height: 100%; border: 0; }
</style>

{% if page.schematic %}
## Schematic

<figure class="design-figure">
  {% if page.schematic contains '.mp4' %}
  <video src="{{ page.schematic | relative_url }}" autoplay loop muted playsinline controls>
    Your browser can't play this video. <a href="{{ page.schematic | relative_url }}">Download it</a> instead.
  </video>
  {% else %}
  <a href="{{ page.schematic | relative_url }}">
    <img src="{{ page.schematic | relative_url }}" alt="{{ site.title }} robot schematic">
  </a>
  {% endif %}
  {% if page.schematic_caption %}<figcaption>{{ page.schematic_caption }}</figcaption>{% endif %}
</figure>
{% endif %}

{% if page.video %}
## Video

{% assign video_id = page.video | split: '/' | last %}
<div class="design-video">
  <iframe src="https://app.screencast.com/connector/embed/index/{{ video_id }}" title="{{ site.title }} project video" allowfullscreen loading="lazy"></iframe>
</div>

<p><a href="{{ page.video }}">Watch on Screencast &rarr;</a></p>
{% endif %}

## How it works

A fire needs heat, fuel, and oxygen. Ember takes them away:

1. **Detect.** Ember detects a fire.
2. **Remove fuel.** It plows a dirt ring to remove fuel.
3. **Cool heat.** It uses the water cannon to cool the fire down.
4. **Smother oxygen.** It blankets the base of the fire in foam to smother it.
5. **Mist and patrol.** Ember goes back to its dock to recharge and refill with
   water. Once recharged, it mists the campsite and clears away dead brush.
