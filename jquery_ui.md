#jQuery UI

##Introduction
[jQuery UI] [jquery_ui] is a rather large library that extends the base jQuery to
provide numerous useful user interaction functionalities. Using this library you
can allow users to resize, select, drag, sort, and drop dom elements. It also provides
various widgets like autocompleting text fields, progress bars, etc.

##Installation
Go to [jQuery UI] [jquery_ui] and download the stable version. They also provide a custom download,
if you know exactly which functionalities you want (some are dependent upon each other). 
There are also various css themes should you choose to use them. Otherwise you can just select
which files you want to use from the entire library. The javascript files are located in the ui
subdirectory.

##Use
You enable jQuery UI functionalities by using jQuery to select your desired elements and calling 
jQuery UI functions on them. You will often pass in an options object which can further configure
the functionality as well as define callbacks at numerous events in the interaction.

```javascript
$(".tiles").draggable({

  drag: function() {
    console.log($(this).position()); // this is set to the dom element
  },

  drop: function() {
    console.log("Landed at: " + $(this).position());
  }

});

```

You will definitely want to refer to the [API Documentation] [jquery_docs].

##Interactions
The fun stuff!

###Draggable
Allows users to click and drag your DOM elements. Options include specification of what
the element is contained in and whether the element should snap to other elements, among
many others.


[jquery_ui]: http://jqueryui.com/
[jquery_docs]: http://api.jqueryui.com/
