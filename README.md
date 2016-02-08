### Features
* Create Tree table from HTML table
* Comparibaly fast on big tables 
* Ability to specify column to make a tree
* Compatible with jquery-ui $.widget
* Ability to save the state of the tree
* Ability to expand/collapse by level of hierarchy

### Demo
   http://gagiks.github.io/jquery-tbltree/
   

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
levelPickerTemplate:| String | `<div class="tbltree-level-pickers">\n<span id="0" class="tbltree-level-item">[1]</span>&nbsp;\n<span id="1" class="tbltree-level-item">[2]</span>&nbsp;\n<span id="2" class="tbltree-level-item">[3]</span>&nbsp;\n<span id="3" class="tbltree-level-item">[4]</span>&nbsp;\n</div>` | HTML template of level pickers, each element having class `tbltree-level-item` must have numberic id, identifying the level we want to show.
indentTemplate:		| String | `<span class="tbltree-indent"></span>` | HTML Element that will be placed as padding, depending on the depth of nesting node
expanderExpandedClass:| String | 'tbltree-expander-expanded' | Class using for expander element when it expanded
expanderCollapsedClass:| String | 'tbltree-expander-collapsed' | Class using for expander element when it collapsed

#### 2. Methods
Method 			| Description | Example
--------- 	| ----------- | ------- 
showLevel   | Show level of tree we want | ``` $('#table1').tbltree('showLevel', 2) ```
expand      | Expand row with ID         | ``` $('#table1').tbltree('expand', '1.1') ```
collapse    | Collapse row with ID       | ``` $('#table1').tbltree('collapse', '1.1') ```
isCollapsed | Returns true if row is collpased  | ``` $('#table1').tbltree('isCollapsed', '1.1') ```
isExpanded  | Returns true if row is expanded   | ``` $('#table1').tbltree('isExpanded', '1.1') ```

