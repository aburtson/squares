#Squares

This plugin includes a squares module, where each square can define steps or categories in a sequence. When a square is clicked, a description appears, and the squares are displayed at half-size.

##Initial setup

1. _Dependencies:_ verify that the jQuery and Bootstrap are included in your project.
2. Include **squares.js** in your JS directory.
3. Include **_squares.scss** or **squares.css** in your stylesheets.
4. Include the HTML inside **squares.html** on your page.
5. Run gulp, and your squares module will be up and running.

##Working with HTML

Below is the basic HTML structure:

```html
<div class="squares">
	<ul class="square-panel__list">
		<span class="square-panel__close"></span>
		<li class="square-panel">
			...
		</li>
		<li class="square-panel">...</li>
		<li class="square-panel">...</li>
		<li class="square-panel">...</li>
		<li class="square-panel">...</li>
		<li class="square-panel">...</li>
	</ul>
	<ul class="square__list">
		<li class="square ...">
			<div class="square__inner">
				<div class="square__content">
					...
				</div>
				<div class="square__arrow"></div>
			</div>
		</li>
		<li class="square ...">...</li>
		<li class="square ...">...</li>
		<li class="square ...">...</li>
		<li class="square ...">...</li>
		<li class="square ...">...</li>
	</ul>
</div>
```

The first `.square-panel` inside `.square-panel__list` corresponds to the first `.square` inside `.square__list`. Each `.square-panel` contains the content for each `.square`. 

Out of the box, the `.square-panel` contains an `h2` and a series of `p` tags. These can be replaced or modified as you see fit.

The contents of each `.square` can also be changed. Feel free to replace the text, or implement an icon or image. However, these modifications will require your own CSS.


##Working with JS

###The slideSelector function

At the bottom of the __squares.js__ file, you will find this function:

```javascript
$('.squares').squares();
```

This function creates your squares module.

If you want to customize the display settings of your slideSelector, include any of the below options, like so:

####columns

This dictates how many columns the squares will have on load. When the panel is opened, the squares will be half-size, so they will take up twice as many columns.

Choose a number from 1 to 4.

```javascript
$('.squares').squares({
    columns: 3
});
```

###Creating multiple versions

The squares module only works on the provided HTML base structure, which has the class `.squares`. If you want to target all squares modules on your site with the same settings, make sure to apply the function to `$('.squares')', like so:

```javascript
$('.squares').squares();
```
 
Otherwise, you can add classes or ids to different instances of the HTML, and run another function, like so:
 
```javascript
$('.your-class').squares();
$('.your-other-class').squares();
```
 
You can keep these functions inside the __squares.js__ file, or add it to another JS file, as long as it is included on your site after __squares.js__.

####Unique settings for each version

You can even add different settings in each function for further customization, like so:

```javascript
$('.your-class').slideSelector({
    columns: 1
});

$('.your-other-class').slideSelector({
    columns: 3
});
```

__Note:__ If you do create different versions of the slideSelector, make sure to avoid including the default `$('.squares').squares();` on the same HTML page as your other slideSelector versions. 