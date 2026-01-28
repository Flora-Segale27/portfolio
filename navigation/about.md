---
layout: post
title: ~About!~
permalink: /about/
comments: false
---

<style>
  /* Base grid layout */
  #grid_container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 15px;
    margin-bottom: 30px;
  }

  /* Make cards 5 and 6 full-width */
  #grid_container .game-card:nth-child(5),
  #grid_container .game-card:nth-child(6) {
    grid-column: 1 / -1;
  }

  /* Horizontal layout ONLY for cards 5 and 6 */
  #grid_container .wide-card .entry {
    display: flex;
    align-items: center;
    gap: 12px;
  }

  #grid_container .wide-card img {
    width: 130px;
    height: auto;
    flex-shrink: 0;
    border-radius: 5px;
  }

  #grid_container .wide-card p {
    text-align: left;
    margin: 0;
  }

  /* Add horizontal spacing for images in cards 1–4 */
  #grid_container .game-card:not(.wide-card) img {
    padding-left: 10px;
    padding-right: 10px;
    box-sizing: border-box;
  }

  /* Add horizontal spacing for text in cards 1–4 */
  #grid_container .game-card:not(.wide-card) .entry {
    padding-left: 10px;
    padding-right: 10px;
  }
</style>

### Intro:

These are my favorite video games!!

<div id="grid_container"></div>

<script>
var outputElement = document.getElementById("grid_container");
outputElement.innerHTML = "";

// Grouped data structure
const video_games = [
  {
    title: "Minecraft",
    color: "#4CAF50",
    entries: [
      { img: "{{site.baseurl}}/images/about/minecraft wallpaper.webp", note: "Basic Minecraft :) I've played since I was really young and really loved building houses and beating the game." },
      { img: "{{site.baseurl}}/images/about/minecraft dungeons.jpg", note: "Minecraft Dungeons is a DLC of Minecraft that I got into last year." }
    ]
  },
  {
    title: "Rise of The Tomb Raider",
    color: "#6b9dcaff",
    entries: [
      { img: "{{site.baseurl}}/images/about/rise cover.webp", note: "The first Tomb Raider game I played - I ABSOLUTELY LOVED ITT!" },
      { img: "{{site.baseurl}}/images/about/rise dynamic.jpg", note: "The art and surround sound and combat is top-notch! It always felt like I myself was getting shot XD" }
    ]
  },
  {
    title: "Shadow of The Tomb Raider",
    color: "#69145bff",
    entries: [
      { img: "{{site.baseurl}}/images/about/shadow cover.webp", note: "This game was also a masterpiece!" },
      { img: "{{site.baseurl}}/images/about/shadow dynamic.webp", note: "I have very vivid memories watching my dad play this as a kid and loving it :)" }
    ]
  },
  {
    title: "Genshin Impact",
    color: "#F06292",
    entries: [
      { img: "{{site.baseurl}}/images/about/NAHIDA.gif", note: "I really love the art style that this game uses!" },
      { img: "{{site.baseurl}}/images/about/juanderer.gif", note: "The lore used to be good... I loved the Liyue and Inazuma lore!" }
    ]
  },
  {
    title: "Destiny 2",
    color: "#FFB300",
    entries: [
      { img: "{{site.baseurl}}/images/about/d2 dynamic 2.jpg", note: "I absolutely ADORE the extensive lore that Bungie has built in the past 12 years of running this game!" },
      { img: "{{site.baseurl}}/images/about/d2 dynamic.webp", note: "I grew up watching my dad plasy Destiny 1, and when Destiny 2 came out, I was old enough to play as well! The gunplay and combat mechanics are super satisfying too." }
    ]
  },
  {
    title: "Forza Horizon 5",
    color: "#1d3284ff",
    entries: [
      { img: "{{site.baseurl}}/images/about/forza cover 2.webp", note: "My dad got this game for me along with the Xbox wheel, pedals, and clutch so I can practice driving before I can get my permit." },
      { img: "{{site.baseurl}}/images/about/forza cover.webp", note: "The scenery and the cars are super sick!" }
    ]
  }
];

// Build each game card
video_games.forEach((game, index) => {
  const gameCard = document.createElement("div");
  gameCard.className = "game-card";

  // Mark cards 5 & 6 as wide
  if (index === 4 || index === 5) {
    gameCard.classList.add("wide-card");
  }

  gameCard.style.border = `3px solid ${game.color}`;
  gameCard.style.padding = "16x";
  gameCard.style.borderRadius = "10px";
  gameCard.style.background = "#302b2bff";

  const title = document.createElement("h3");
  title.textContent = game.title;
  title.style.textAlign = "center";
  title.style.marginBottom = "5px";
  title.style.marginTop = "5px";
  title.style.fontSize = "1.1em";
  gameCard.appendChild(title);

  const innerColumn = document.createElement("div");
  innerColumn.style.display = "flex";
  innerColumn.style.flexDirection = "column";
  innerColumn.style.gap = "10px";

  game.entries.forEach(entry => {
    const item = document.createElement("div");
    item.className = "entry";

    const img = document.createElement("img");
    img.src = entry.img;
    img.alt = game.title;

    // Only shrink images for cards 5 & 6
    if (index === 4 || index === 5) {
      img.style.width = "130px";
      img.style.height = "auto";
      img.style.flexShrink = "0";
    } else {
  img.style.width = "100%";   // or 85%, or 80% — tune to taste
  img.style.height = "auto";
  img.style.margin = "0 auto"; // centers the image
    }

    img.style.objectFit = "cover";
    img.style.borderRadius = "5px";

    const note = document.createElement("p");
    note.textContent = entry.note;
    note.style.fontSize = "0.9em";
    note.style.opacity = "0.8";

    item.appendChild(img);
    item.appendChild(note);
    innerColumn.appendChild(item);
  });

  gameCard.appendChild(innerColumn);
  outputElement.appendChild(gameCard);
});
</script>

### Places I've Lived or Have Family In:

<div class="row">
<img src="{{site.baseurl}}/images/about/minnesota flag.png" style="height:100px; margin-right:50px;" alt="Minnesota">
<img src="{{site.baseurl}}/images/about/og flag.png" style="height:100px; margin-right:50px;" alt="Orange County">
<img src="{{site.baseurl}}/images/about/san diego flag.png" style="height:100px; margin-right:50px;" alt="San Diego">
<img src="{{site.baseurl}}/images/about/puglia flag.png" style="height:100px; margin-right:50px;" alt="Puglia">
</div>

- ⭐ **Minnesota** - My dad and I were both born in Minnesota! Once I was born in St. Paul, Minnesota's capital, I stayed there until I was 18 months old, and then my family moved to Irvine, California.
- ⭐ **Orange County** - I lived in Irvine and attended Woodbury ELementary until I was 7 years old, then I moved to...
- ⭐ **San Diego** and have lived here since then!
- ⭐ **Puglia/Italy** My mom was born in Italy, specifically, Puglia, which is one of the south-east regions of Italy. We go back every summer to visit my family there.




### Journey through Life

These are the places I've gone to school:

- 🏫 I attended two elementary schools: Woodbury K-6 Elementary and Del Sur Elementary.
- 🚌 I graduated 5th grade from Del Sur and then attended Oak Valley Middle (6th–8th grade).
- 📚 I'm currently a freshman at Del Norte High.

### My Family

My family consists of my mom, dad, and my baby brother.

- My dad's side of the family is from Minnesota, USA, with Irish and Northern Italian origins.
- My mom's side is from Puglia (the "heel" of Italy's "boot"). Many relatives later moved to Northern Italy near the borders with Austria, Germany, and France. Their children learn Italian, German, and English at school.

Some of my most recent favorite pictures — scroll right to see more!

<style>
.image-gallery {
  display: flex;
  gap: 10px;
  overflow-x: auto;
  padding: 10px 0;
  scroll-snap-type: x mandatory;
  scrollbar-width: thin;
}

.image-gallery img {
  height: 350px;
  flex-shrink: 0;
  border-radius: 10px;
  scroll-snap-align: start;
  object-fit: cover;
}
</style>

<div class="image-gallery">
    <img src="{{site.baseurl}}/images/about/anthony_selfie.png" alt="Anthony selfie">
    <img src="{{site.baseurl}}/images/about/d2_fynch.png" alt="Destiny 2 Character">
    <img src="{{site.baseurl}}/images/about/hoco_pic_w_girls.png" alt="Homecoming with friends">
    <img src="{{site.baseurl}}/images/about/last_race_group_pic.png" alt="Last race group">
    <img src="{{site.baseurl}}/images/about/scarlette.png" alt="Scarlette">
</div>
