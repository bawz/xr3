#XR3
###By Jason Silberman

####Getting Started
Xr3 is a simple way to load `node` elements as pages. It is *very* simple to implement. First:

	<script type="text/javascript" src="js/vendor/xr3.js"></script>

What we are doing here is just including the `xr3.js` script into our project. We need this script for XR3 to work. Next we need to wait for the page load and then call `xr3.run()`. *Make sure you also have [jQuery](http://jquery.com) loaded.

	<script type="text/javascript">
		jQuery(document).ready(function () {
			xr3.run();
		});
	</script>

That is the all the javascript we need for now, next we move to html.

####Your HTML
Here is a simple example html template for using XR3.

	<ul>
		<li data-page=".home" class="auto-load">Home</li>
		<li data-page=".about">About</li>
		<li data-page=".contact">Contact</li>
	</ul>
	
	<div class="page home" data-pg="true">
		<h2>Welcome</h2>
		<p>Welcome to my site.</p>
	</div>
	
	<div class="page about" data-pg>
		<h2>About Me</h2>
		<p>Here is a page about me.</p>
	</div>
	
	<div class="page contact" data-pg>
		<h2>Contact Me</h2>
		<p>Here is some contact stuff.</p>
	</div>

Now, I know there is a lot of code here but let me explain to you what it does. The first thing we are doing which is within a `ul` element. Basically we are making an unordered list and filling it with three `li` elements. There are two *key* things here: one, see how each thing has a `data-page` attribute? That tells the code which "page" to open when the element is clicked. And two, see how that `li` for the home page? See how it has a class `auto-load`? That is important to make sure to load that page first.

Next we are going to look at those `div` elements. Now each `div` has a class of `.page` and an attribute of `data-pt`. This signals to the code that this should be rendered as a page with XR3. Also each have another class that coordinates with a `li` in the `ul` element. Basiciclly what is happening is when a `li` here is clicked it fins the `data-page` attribute and uses that to target a `.page` element and add a `.load` class.

One more thing to note that is ***very*** important remember how the `li` for home had an extra class of `.auto-load`? One more thing to note is that whatever page that relates to, we need to make sure that its `data-pg` attribute must be set to true.