### Features
* Create Tree table from HTML table
* Ability to specify column to make a tree
* Compatible with jquery-ui $.widget
* Ability to save the state of the tree
* Ability to expand/collapse by level of hierarchy


### Basic Example

<table>
  <tr class="header"> <td>#</td><td> <div id="levels"></div>Title</td><td>Column 1</td><td>Column 2</td><td>Column 3</td></tr>
</table>

### Usage
#### 1. Install
<p>Include jQuery and jQuery-ui in your page:</p>
```html
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jqueryui/1.10.1/jquery-ui.min.js"></script>
```
**_Include Plugin in your page:_**
```html
<script type="text/javascript" src="./js/jquery.tbltree.js"></script>
<link type="text/css" href="css/jquery.tbltree.css" rel="stylesheet">
```
If you want to use `saveState:` option, then need to include $.coocke plugin as well:
```html
<script type="text/javascript" src="./js/jquery.cookie.js"></script>
```

#### 2. Make a tree
<p>Create HTML Table by adding 'row-id' and 'parent-id' attributes to "tr" tags.
Attributes names can be configured by options `rowAttr` and `parrentAttr`.</p>
```html
<table id="table1">
  <tr>
    <td>Title</td><td>Column 1</td><td>Column 2</td><td>Column 3</td>
  </tr>
  <tr row-id="1">
    <td>Level 1</td><td class="data">2</td><td class="data">2</td><td class="data">2</td>
  </tr>
  <tr row-id="1.1" parent-id="1" >
    <td>Level 1.1</td><td class="data">2</td><td class="data">2</td><td class="data">2</td>
  </tr>
  <tr row-id="2">
    <td>Level 2</td><td class="data">2</td><td class="data">2</td><td class="data">2</td>
  </tr>
  <tr row-id="2.1" parent-id="2" >
    <td>Level 2.1</td><td class="data">2</td><td class="data">2</td><td class="data">2</td>
  </tr>
</table>
```

<p>Add javascript code:</p>
```javascript
 $(function() {
     // initialize with default options
    $( "#table1" ).tbltree();
  });
```

### Configuration

#### 1. Settings
Parameter 			| Type | Default | Description  
--------- 			| ---- | ------- | -----------
rowAttr:  			| String | 'row-id' | Attribute name which is set for `<tr>` tags and identifies the ID of the row.
parentAttr:			| String | 'parent-id' | Attribute name which is set for `<tr>` tags and identifies the ID of parent row.<br> **Note: this attribute must be skipped for root nodes.**
initState:			| String | 'collapsed' |
treeColumn:			| String | 0 | Identifies the column of the table we want to make a tree.
saveState:			| Boolean | false | If true tree state will be save after page is re-loaded
saveStateName:		| String | 'tbltree-state' | Name of cookie to save state
levelPicker:		| String | '' | jQuery selectot of an element where we cant to render level pickers.
expanderTemplate:	| String | `<span class="tbltree-expander"></span>` | HTML Element when you click on that will be collapse/expand branches
levelPickerTemplate:| String | `<div class="tbltree-level-pickers">
<span id="0" class="tbltree-level-item">[1]</span>&nbsp;
<span id="1" class="tbltree-level-item">[2]</span>&nbsp;
<span id="2" class="tbltree-level-item">[3]</span>&nbsp;
<span id="3" class="tbltree-level-item">[4]</span>&nbsp;
</div>` |
indentTemplate:		| String | `<span class="tbltree-indent"></span>` |
expanderExpandedClass:| String | 'tbltree-expander-expanded' |
expanderCollapsedClass:| String | 'tbltree-expander-collapsed' |


### Rather Drive Stick?
If you prefer to not use the automatic generator, push a branch named `gh-pages` to your repository to create a page manually. In addition to supporting regular HTML content, GitHub Pages support Jekyll, a simple, blog aware static site generator written by our own Tom Preston-Werner. Jekyll makes it easy to create site-wide headers and footers without having to copy them across every page. It also offers intelligent blog support and other advanced templating features.

### Authors and Contributors
You can @mention a GitHub username to generate a link to their profile. The resulting `<a>` element will link to the contributor's GitHub Profile. For example: In 2007, Chris Wanstrath (@defunkt), PJ Hyett (@pjhyett), and Tom Preston-Werner (@mojombo) founded GitHub.

### Support or Contact
Having trouble with Pages? Check out the documentation at http://help.github.com/pages or contact support@github.com and we’ll help you sort it out.
