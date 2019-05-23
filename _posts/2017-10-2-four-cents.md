---
layout: post
title:  "Four Cents"
date:   2017-10-3
excerpt: "A no-frills, static website for calculating fuel discounts and cost-effectivness with JavaScript."
tag:
- portfolio
comments: true
---

[Four Cents](https://www.fourcents.me) is a website dedicated to providing a convenient way to calculate how much petrol to pump when you're using a per-litre discount. This solves a problem I often faced when pumping petrol: I have $40 to put in, but a 4c/L discount to be applied at checkout.. how much should I pump to reach $40.00 exactly? A small problem indeed, and one achievable with a calculator (but not very conveniently).


Any solution needed to be intuitive and quick to load; waiting for a bloated website/app to load while sitting at the service station wasn't on. Therefore, the "back-end" is written in Javascript in a static/local manner. The website incredibly small (a few kB) and quick to load. The hosting is provided by [GitHub Pages](https://pages.github.com/) who provides static site hosting, and accelerated using [CloudFlare's free CDN](https://cloudflare.com) to allow quick access worldwide. 

The site itself has a simple design and provides an intuitive input steps to calculate the solution. Additionally, I included a calculation that determines at what price E10 fuel becomes cost-effective (this code can be seen [here](https://github.com/curtiswest/petrol-discount-calculator/blob/056ef51a5e2cfc2d2d59c806f4f4d688b166a0ab/calc.js#L47)). This is based on the energy content in the fuel (as ethanol is less energy-dense than petrol), which is a relatively good approximation for the fuel's possible Km/L (MPG). Of course, this still depends on the engine's efficiency, and it doesn't account for the environmental impact of ethanol fuel which can easily outweigh the few cents difference. 

# Summary
* Four Cents is a small, convenient website for calcuating fuel discounts and E10 cost effectiveness. 
* It is static, local and its functionality is implemented in JavaScript.
* It uses custom CSS for a mobile-friendly and desktop-friendly design. 
* It is reachable at: [https://www.fourcents.me](https://www.fourcents.me)
* It's code is [available on my Github](https://github.com/curtiswest/petrol-discount-calculator). 