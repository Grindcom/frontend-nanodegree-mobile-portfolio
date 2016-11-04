# My Additions to the Website Performance Optimization Project
## Getting Started  
This App can be  
1. [seen here](https://grindcom.github.io/frontend-nanodegree-mobile-portfolio/),  
2. Or you can download all the files to a local folder.  
3. Or you can clone it using `git clone https://github.com/Grindcom/frontend-nanodegree-mobile-portfolio.git`  
If you choose to download the files, create a folder and place the repository files and folders in them; keep in mind that your local folder can have any name, but the repository file structure must be the same.

## Optimizations Used  

### Critical Rendering Path - index.html
In order to achieve a PageSpeed Insights core of 95 for mobile and 97 for Desktop I used the following techniques.  
1. Moved all scripts from the head to below the closing body tag.  
2. Resized the images linked to in the index file.
3. Compressed those images.  
4. Removed the link to google fonts.  
5. Used a 'defer' in the script for google-analytics.  
6. Minified style.css and placed it in-line in the index.html file.

#### Tools Used
1. http://compressjpeg.com/ to compress the related images.
2. Grunt to resize images.
2. Minify css with https://cssminifier.com/
3. Minify html with  https://kangax.github.io/html-minifier/
4. Chrome devtools  

### Getting Rid of Jank - views/js/main.js and views/pizza.html  
In order to remove the jank...
1. Refactor `changePizzaSizes(size)` function.
2. Reduce the number of moving pizzas created from 200 to around 20.
3. Change any querySelectorAll function calls to getElementsByClassName;  it was suggested that this is a more efficient method.  
4. Refactor `resizePizzas(size)` function.  
5. Use constants for pizza size; SMALL, MEDIUM, LARGE.  

### Tools Used  
1. [Compress png files](http://compresspng.com/)  
2. Chrome devtools  

## - Below is the original ReadMe content -
## Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository and inspect the code.  

### Getting started

####Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

####Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js.

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

### Optimization Tips and Tricks
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>
