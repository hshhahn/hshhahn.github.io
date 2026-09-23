---
layout: page
title: Availability
permalink: /availability/
nav: true
nav_order: 4
---

{% if site.google_calendar_embed_url %}
  <div class="availability-calendar">
    <p class="availability-calendar__intro">
      Here is my current schedule! (My timezone is in ET)
    </p>
    <div class="availability-calendar__viewport">
      <iframe
        class="availability-calendar__frame"
        src="{{ site.google_calendar_embed_url }}"
        title="Sanghyun Hahn's availability calendar"
        loading="lazy"
        tabindex="-1"
        aria-hidden="true"
        scrolling="no"
      ></iframe>
    </div>
  </div>
{% endif %}
