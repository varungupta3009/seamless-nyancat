# Infinite Modular Nyan Cat 🌌🐈🌈

A fully seamless, CSS-animated, tileable SVG implementation of Nyan Cat.

Unlike standard, massive SVGs that are hard to scale dynamically, this project breaks the famous space cat down into two modular, 118x118 pixel tiles:

## 📁 What's Included

This repository includes two variations of the tiles depending on your needs, plus a ready-to-use HTML preview:

* **`index.html`** - A live HTML/CSS boilerplate demonstrating how to stitch the SVGs together perfectly using Flexbox.

**The Offset Variations (Recommended)**

* **`rainbow.svg` & `cat.svg`** - In these files, the internal animation is shifted right by half a rainbow block (15px). This makes the individual SVGs look perfectly centered and visually appealing when viewed entirely on their own, while still stitching together flawlessly in HTML.

**The "Perfect" Alignment Variations**

* **`rainbow-perfect.svg` & `cat-perfect.svg`** - The original, non-offset versions. The internal rainbow blocks start mathematically flush with the `0` edge of the SVG viewbox. They function identically to the offset versions when stitched in CSS, but look slightly asymmetrical when opening the raw SVG files by themselves.

By utilizing CSS Flexbox, you can easily stitch as many `rainbow.svg` tiles together as you want to create an infinite, dynamic, gapless rainbow trail of any length!

## 🚀 Usage

You can create a perfect, seamless animation simply by putting the SVGs next to each other inside a flex container.

### HTML

```html
<div class="nyan-container">
  <img src="rainbow.svg" class="nyan-tile" alt="Rainbow trail">
  <img src="rainbow.svg" class="nyan-tile" alt="Rainbow trail">
  <img src="rainbow.svg" class="nyan-tile" alt="Rainbow trail">
  
  <img src="cat.svg" class="nyan-tile" alt="Nyan Cat">
</div>

```

### CSS

```css
.nyan-container {
  display: flex;
  flex-direction: row;
  /* Flexbox eliminates standard inline-block image gaps */
}

.nyan-tile {
  display: block;
  width: 118px; 
  height: 118px;
}

```

## 🛠️ How it Works

To prevent animation "clipping" when the CSS transform slides the rainbow to the left, the internal SVG viewboxes have been meticulously math-matched. They overlap their internal elements by exactly half a rainbow block (15px) so that when placed side-by-side in HTML, the animation loop passes from one image tag to the next without a single dropped frame or visual gap.

### ⚖️ Why two versions?

When you slice a continuous, moving animation into static 118x118 bounding boxes, the exact mathematical cut can look a bit awkward when viewing just that one single slice.

The standard files (`rainbow.svg` / `cat.svg`) shift the internal elements by 15px so the blocks look centered and whole when viewed in isolation (like inside a folder preview or a design app). The `-perfect` variations lack this visual offset, representing the absolute raw cut. Because both sets use the exact same overlapping animation math, you can use whichever set fits your project's workflow best!

## 👏 Credits & Attribution

* **Original CSS/SVG Animation base:** [Gowee's nyancat-svg](https://github.com/Gowee/nyancat-svg)
* **Original HTML5 Cat Frames:** [iliana's html5nyancat](https://github.com/iliana/html5nyancat)

## 📄 License

[MIT License](LICENSE)
