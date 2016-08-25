# Additional widgets repository for DeepSee Web
This repository contains several examples of custom widgets for DeepSeeWeb.

# Creating custom portlet

To register new type of widget instead exists one, custom portlet should be created first. 
Full documentation about portlet creation can be found here: [Creating Portlets for Use in Dashboards](http://docs.intersystems.com/latest/csp/docbook/DocBook.UI.Page.cls?KEY=D2IMP_ch_portlets)
Follow the steps to use portlet as custom widget:

1) Create portlet class in desired namespace. Simplest class can be like this:
```
Class DSW.CustomPortlet Extends %DeepSee.Component.Portlet.abstractPortlet
{
}
```
2) In DeepSee go to widget section and press "+" button to add new widget on dashboard.

3) From the list select "Portlet" > "CustomPortlet". Note: "CustomPortlet" is name of the class, that was created in step one.

4) Set widget data source, widget name and press "Ok".

5) Save dashboard.

Now custom widget can be used in DeepSeeWeb. Just configure custom addons as specified [here](https://github.com/intersystems-ru/DeepSeeWeb#creating-custom-widgets) or use following example:
```
{
	"widgets": [{
		"url": "src/factories/customWidget.js",
		"class": "CustomWidget",
		"name": "dsw.customportlet",
		"type": "custom",
		"directive": "custom-directive"
  }]
}
```
Source file for custom widget can be found in DSW repo here: [customWidget.js](https://github.com/intersystems-ru/DeepSeeWeb/blob/master/src/factories/customWidget.js)
    	
