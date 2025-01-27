---
title: Reducing inline prompt flicker
description: >-
  When using a Redfast zone, you may encounter a flicker. This type of issue is
  especially prominent when replacing existing blocks of content with zone on
  your webapp. This recipe provides you with some approaches to reduce or
  eliminate flicker
hidden: false
recipe:
  color: '#018FF4'
  icon: 🦉
---
```javascript JavaScript
<style>
  [data-rf-zone="banner"]:empty + .slider {
    display: none;
  }
</style>
<div data-rf-zone="banner"></div> 
<div class="slider">
  <div class="slider1"><img src="/img1.png" /></div>
  <div class="slider2"><img src="/img2.png" /></div>
  <div class="slider3"><img src="/img3.png" /></div>
</div>

<style>
  [data-rf-zone="banner"]:empty + .slider {
    display: none;
  }
</style>
<div data-rf-zone="banner">
  <img src="/redfast-img1.png" />
  <img src="/redfast-img2.png" />
  <img src="/redfast-img3.png" />
</div> 
<div class="slider">
  <div class="slider1"><img src="/img1.png" /></div>
  <div class="slider2"><img src="/img2.png" /></div>
  <div class="slider3"><img src="/img3.png" /></div>
</div>

<style>
  .slider { display: none; }
  [data-rf-zone="banner"]:empty + .slider {
    display: none;
  }
</style>
<script>
(function() {
  // if after X seconds maximum and still no zone data then show the original banner
  setTimeout(() => {
    const slider = document.querySelector(".slider");
    const hasZoneData = document.querySelector('[data-rf-zone="banner"] > div');
    if (slider && !hasZoneData && slider.style.display === "none") {
      // slider.style.opacity = "1";
      slider.style.display = "block";
      // set zone to display none
      const rfZone = document.querySelector('[data-rf-zone="banner"]');
      rfZone.style.display = "none";
    }
  }, 5000);
})();
</script>

<div data-rf-zone="banner"></div> 
<div class="slider">
  <div class="slider1"><img src="/img1.png" /></div>
  <div class="slider2"><img src="/img2.png" /></div>
  <div class="slider3"><img src="/img3.png" /></div>
</div>

<style>
  .slider { display: none; }
  [data-rf-zone="banner"]:empty + .slider {
    display: none;
  }
</style>
<script>
(function() {
  const hasPlacementData = false;
  RF.on("actions", (data) => {
    const banner = "banner";
    hasPlacementData = data.paths.find(item => item.zone === banner);
  });

  // if after X seconds maximum and still no zone data then show the original banner
  setTimeout(() => {
    const slider = document.querySelector(".slider");
    if (slider && !hasZoneData && slider.style.display === "none") {
      // slider.style.opacity = "1";
      slider.style.display = "block";
      // set zone to display none
      const rfZone = document.querySelector('[data-rf-zone="banner"]');
      rfZone.style.display = "none";
    }
  }, 5000);

  // As an alternate to setTimeout you can also save the data into your Redux Store (React), Vuex Store (Vue), etc 
  // if you are rendering the component from within your framework so you can show or hide by re-rendering

  // React example
  import { toggleRedfastBanner } from './actions';

  RF.on("actions", (data) => {
    const banner = "banner";
    hasPlacementData = data.paths.find(item => item.zone === banner);
    store.dispatch(toggleRedfastBanner(hasPlacementData));
  });
    
})();
</script>

<div data-rf-placement="banner"></div> 
<div class="slider">
  <div class="slider1"><img src="/img1.png" /></div>
  <div class="slider2"><img src="/img2.png" /></div>
  <div class="slider3"><img src="/img3.png" /></div>
</div>

```

```json Response Example
{"success":true}
```

# Initial loading

<!-- javascript@1-11 -->

This is a typical loading of an inline zone in its empty state

# Fetch prompt

<!-- javascript@13-27 -->

After Redfast data is loaded the original slider will be hidden. This achieves the desired outcome, but results in a flashing on the screen in the interm where the slider is being hidden and the zone is loaded.

# Reduce flicker option A

<!-- javascript@29-57 -->

Check if the redfast zone <div> has data

# Reduce flicker option B

<!-- javascript@59-105 -->

Check if the SDK has received data