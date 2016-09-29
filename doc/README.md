DOMModifier

This is a javascript project designed to provide an alternative to the jQuery library. I've initiated the project by creating the main
implmentation class called DOMModify. There are many useful function that could be added to this project. Below, I explain what i've 
done thus far so that the project is easy to navigate for developers who would like to make additions:

Some Facts
---------------------------------------------------------------------
*Main implementation class: DOMModify
*DOMModify prototype alias: p

	We add new function to DOMModify as follows:
	p.newFunctionName = function( arguments  ) {
	}

*DOMModify stores the matched node in the __node property
*If there was a failure to find a valid DOM node, null is stored in __node property
*Before executing any function or property of __node, check to make sure __node != null with this.nn function
*The globally defined requiredElementProperties indexed array stores a list of properties/function by which
objects are tested to make sure they are proper DOM Elements. If you add any properties to this check to make 
sure they are fully cross browser compatible at http://www.w3schools.com/jsref/dom_obj_all.asp
*Functionality can be added to functions individually to test for the presense of DOMElement non-universal properties
*Note that all code is contained in DOMModify.html. It is inside the script tag of an html file in order to make it
 easier to test

What i'd like to see happen
-----------------------------------------------------------------------
*instantiation of DOMModify and aliasing of the instance and the instance's most important functions
*DOMModify constructor should no longer be used to match elements, rather a function should be created
 and aliased to do this. Thus, the end user won't have to instantiate DOMModify only call a member function to
 match an element. This member function should pass back the main instance of DOMModify

	So rather than the following:
		var DomModify = new DOMModify( "#myId" );
		DomModify.doSomething( args );
	The user would implement an instance of the DOMModify object instantiated with document like:
		DomModify.match("#myId").doSomething( args );
	or aliased to something shorter:
		_d("#myId).doSomething( args );
	where "_d" is clearly the alias for "DomModify.match". Similar to JQuery

*Creation of code to parse out css selector strings. This code is needed due to limitations in backward 
 compatibility of DOMElement's querySelector function in older versions of browsers
*Addition of a function to watch for the ready state in the rendering of the DOM Document
*addition of any functions you think would be useful or important in DOM manipulation. Just be careful
 to make sure that any member functions/properties of DOM Elements you use are fully compatible with
 all major browsers including older versions. If not, create an alternative route of execution that
 will work in other browsers or older versions of the browser
