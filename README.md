# at Responsive Accordion or Tabs jQuery Plugin

at Responsive Accordion or Tabs is a jQuery plugin that takes unordered lists formatted in a certain manner and can display them as tabs when the tabs fit horizontally, and accordions when they don't.

This plugin is built heavily upon the work by Stuart Robson found at http://codepen.io/sturobson/pen/xgfeI. The reason for this plugin, though, is that his method requires changing CSS breakpoints. For static tabs this is not a problem, but I needed something that would always work, no matter what names were added to the tabs. Instead of using hard-coded CSS breakpoints for when the tabs will no longer fit, this plugin is dynamic, as it calculates when to make the tabs an accordion and vice versa.

This plugin also keeps track of accordion/tab states via hashbangs. This is accomplished by way of using "Cowboy" Ben Alman's jQuery BBQ: Back Button & Query Library plugin found at http://benalman.com/projects/jquery-bbq-plugin/.

This plugin has been tested and works with modern versions of Chrome, Firefox, Edge, Safari, iOS, and Android.

## Usage

Include the plugin scripts and style file.

```html
<script src="//ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>
<script src="jquery.bbq.min.js" type="text/javascript"></script>
<script src="jquery.atAccordionOrTabs.min.js" type="text/javascript"></script>
<link rel="stylesheet" href="jquery.atAccordionOrTabs.min.css">
```

###Example Usage

```html
<ul class="tabs-example">
  <li><a>Paperboy</a>
	<section>
	  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras tincidunt pellentesque lorem, id suscipit dolor rutrum id. Morbi facilisis porta volutpat. Fusce adipiscing, mauris quis congue tincidunt, sapien purus suscipit odio, quis dictum odio tortor in sem. Ut sit amet libero nec orci mattis fringilla. Praesent eu ipsum in sapien tincidunt molestie sed ut magna. Nam accumsan dui at orci rhoncus pharetra tincidunt elit ullamcorper. Sed ac mauris ipsum. Nullam imperdiet sapien id purus pretium id aliquam mi ullamcorper.</p>
	</section>
  </li>
  <li><a>Super Mario Bros.</a>
	<section>
	  <p>Ut laoreet augue et neque pretium non sagittis nibh pulvinar. Etiam ornare tincidunt orci quis ultrices. Pellentesque ac sapien ac purus gravida ullamcorper. Duis rhoncus sodales lacus, vitae adipiscing tellus pharetra sed. Praesent bibendum lacus quis metus condimentum ac accumsan orci vulputate. Aenean fringilla massa vitae metus facilisis congue. Morbi placerat eros ac sapien semper pulvinar. Vestibulum facilisis, ligula a molestie venenatis, metus justo ullamcorper ipsum, congue aliquet dolor tortor eu neque. Sed imperdiet, nibh ut vestibulum tempor, nibh dui volutpat lacus, vel gravida magna justo sit amet quam. Quisque tincidunt ligula at nisl imperdiet sagittis. Morbi rutrum tempor arcu, non ultrices sem semper a. Aliquam quis sem mi.</p>
	 </section>
  </li>
  <li><a>Zelda</a>
	<section>
	  <p>Donec mattis mauris gravida metus laoreet non rutrum sem viverra. Aenean nibh libero, viverra vel vestibulum in, porttitor ut sapien. Phasellus tempor lorem id justo ornare tincidunt. Nulla faucibus, purus eu placerat fermentum, velit mi iaculis nunc, bibendum tincidunt ipsum justo eu mauris. Nulla facilisi. Vestibulum vel lectus ac purus tempus suscipit nec sit amet eros. Nullam fringilla, enim eu lobortis dapibus, quam magna tincidunt nibh, sit amet imperdiet dolor justo congue turpis.</p>    
	</section>
  </li>
  <li><a>Dr. Mario</a>
	<section>
		 <p>Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Phasellus dui urna, mollis vel suscipit in, pharetra at ligula. Pellentesque a est vel est fermentum pellentesque sed sit amet dolor. Nunc in dapibus nibh. Aliquam erat volutpat. Phasellus vel dui sed nibh iaculis convallis id sit amet urna. Proin nec tellus quis justo consequat accumsan. Vivamus turpis enim, auctor eget placerat eget, aliquam ut sapien.</p>
	</section>
  </li>
</ul>

<script type="text/javascript">
$('.tabs-example').accordionortabs();
</script>
```

## Plugin Options

**defaultOpened**: which tab is open (default is 0)

By default no accordion or tab is set to be open. Of course while in tab view, some tab's content must be showing, so it will default to showing the first tab's content, but in accordion mode they will all be shut. If you want the third accordion/tab to be open upon page load, then you would set it to 3. If you want the first accordion/tab to be open no matter which mode it's in, you should set it to 1.


#####Example Usage

```html
<script type="text/javascript">
$('.tabs-example').accordionortabs({
	defaultOpened: 3
	});
</script>
```


**tabsIfPossible** (true or false: default is true)

If you use this plugin normally to allow for accordions or tabs but have an instance where you want the item to always show as an accordion, give the table a special class or ID, use that class or ID in the jQuery selector, and set this option to false.


#####Example Usage

```html					
<script type="text/javascript">
$('.tabs_never_shown').accordionortabs({
	tabsIfPossible: false
	});
</script>
```


**hashbangPrefix** (default is 'tabset_')

This plugin will make hashbangs as users browse through your accordion/tabs and will produce urls like www.example.com/your-page.html#!tabset_0=2&tabset_1=1. If you want some nomenclature other than tabset_, indicate that here.


#####Example Usage

```html					
<script type="text/javascript">
$('.tabs-example').accordionortabs({
	hashbangPrefix: "games_"
	});
</script>
```


**centerTabs** (true or false: default is false)

By default the tabs are aligned left. Set this option to true if you would like the plugin to keep your tabs centered above the content.


#####Example Usage

```html					
<script type="text/javascript">
$('.tabs-example').accordionortabs({
	centerTabs: true
	});
</script>
```