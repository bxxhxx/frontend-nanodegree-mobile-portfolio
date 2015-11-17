##Introduction:

This is my submission for Project 4. The criteria was to optimize this online portfolio for speed by applying Critical Rendering Path principles.

##How to run the web pages:

You can download the files at: https://github.com/bxxhxx/frontend-nanodegree-mobile-portfolio Then you need to open the index.html in your browser. You can also directly access it through Github pages at: http://bxxhxx.github.io/frontend-nanodegree-mobile-portfolio/
The original source was from: https://github.com/udacity/frontend-nanodegree-mobile-portfolio

##Optimization for Part I:

Mainly, the following changes were applied to index.html to achieve a PageSpeed
score ABOVE 90:
- Originally Google fonts were adding a huge amount of time for loading. I researched and used
techniques to load google fonts differently:
http://www.sitepoint.com/improve-page-performance-font-loader/
- Added in-line css style sheet
- Reduced image size for pizzeria and Cameron's img by running grunt
- Created media query for print css style sheet
- Used onload method to delay non-critical script
- Added async to delay google-analytics


##Optimization for Part II:

To insure frame rate at 60fps, I changed/improved the following among others:
- FSL in updatePositions function:
Basically I moved the "scrollTop" layout measurement outside of the "style" loop, put it in a variable and use the variable inside the "style.left" loop
- Original formatting had created 200 background pizzas, most of which were not on screen.
I reduced this number to 40.
- I created a small array containing the five "phases" used for calculating the style.left
in the loop. And then called these values within the loop.
- Improved the slider for the size changes by greatly reducing calculation for style.width
by using a simple set of percentages.
- When possible I used a faster selector method: getElement..., instead of querySelector