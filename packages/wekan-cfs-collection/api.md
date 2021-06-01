## cfs-collection Public API ##

CollectionFS, FS.Collection object

_API documentation automatically generated by [docmeteor](https://github.com/raix/docmeteor)._

-

### <a name="FS.Collection.prototype.insert"></a>*fsCollection*.insert(fileRef, [callback])&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ###

*This method __insert__ is defined in `prototype` of `FS.Collection`*

__Arguments__

* __fileRef__ *{[FS.File](#FS.File)|[File](#File)}*  

 File data reference

* __callback__ *{function}*  (Optional)

 Callback `function(error, fileObj)`


__Returns__  *{FS.File}*
The `file object`
[Meteor docs](http://docs.meteor.com/#insert)

> ```FS.Collection.prototype.insert = function(fileRef, callback) { ...``` [api.common.js:8](api.common.js#L8)


-

### <a name="FS.Collection.prototype.update"></a>*fsCollection*.update(selector, modifier, [options], [callback])&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ###

*This method __update__ is defined in `prototype` of `FS.Collection`*

__Arguments__

* __selector__ *{[FS.File](#FS.File)|object}*  
* __modifier__ *{object}*  
* __options__ *{object}*  (Optional)
* __callback__ *{function}*  (Optional)
[Meteor docs](http://docs.meteor.com/#update)

> ```FS.Collection.prototype.update = function(selector, modifier, options, callback) { ...``` [api.common.js:71](api.common.js#L71)


-

### <a name="FS.Collection.prototype.remove"></a>*fsCollection*.remove(selector, [callback])&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ###

*This method __remove__ is defined in `prototype` of `FS.Collection`*

__Arguments__

* __selector__ *{[FS.File](#FS.File)|object}*  
* __callback__ *{Function}*  (Optional)
[Meteor docs](http://docs.meteor.com/#remove)

> ```FS.Collection.prototype.remove = function(selector, callback) { ...``` [api.common.js:92](api.common.js#L92)


-

### <a name="FS.Collection.prototype.findOne"></a>*fsCollection*.findOne(selector)&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ###

*This method __findOne__ is defined in `prototype` of `FS.Collection`*

__Arguments__

* __selector__ *{[selector](http://docs.meteor.com/#selectors)}*  
[Meteor docs](http://docs.meteor.com/#findone)
Example:
```js
var images = new FS.Collection( ... );
// Get the file object
var fo = images.findOne({ _id: 'NpnskCt6ippN6CgD8' });
```

> ```FS.Collection.prototype.findOne = function(selector) { ...``` [api.common.js:122](api.common.js#L122)


-

### <a name="FS.Collection.prototype.find"></a>*fsCollection*.find(selector)&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ###

*This method __find__ is defined in `prototype` of `FS.Collection`*

__Arguments__

* __selector__ *{[selector](http://docs.meteor.com/#selectors)}*  
[Meteor docs](http://docs.meteor.com/#find)
Example:
```js
var images = new FS.Collection( ... );
// Get the all file objects
var files = images.find({ _id: 'NpnskCt6ippN6CgD8' }).fetch();
```

> ```FS.Collection.prototype.find = function(selector) { ...``` [api.common.js:138](api.common.js#L138)


-

### <a name="FS.Collection.prototype.allow"></a>*fsCollection*.allow(options)&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ###

*This method __allow__ is defined in `prototype` of `FS.Collection`*

__Arguments__

* __options__ *{object}*  
    * __download__ *{function}*  

    Function that checks if the file contents may be downloaded

    * __insert__ *{function}*  
    * __update__ *{function}*  
    * __remove__ *{function}*  

    Functions that look at a proposed modification to the database and return true if it should be allowed

    * __fetch__ *{[string]}*  (Optional)

    Optional performance enhancement. Limits the fields that will be fetched from the database for inspection by your update and remove functions

[Meteor docs](http://docs.meteor.com/#allow)
Example:
```js
var images = new FS.Collection( ... );
// Get the all file objects
var files = images.allow({
insert: function(userId, doc) { return true; },
update: function(userId, doc, fields, modifier) { return true; },
remove: function(userId, doc) { return true; },
download: function(userId, fileObj) { return true; },
});
```

> ```FS.Collection.prototype.allow = function(options) { ...``` [api.common.js:164](api.common.js#L164)


-

### <a name="FS.Collection.prototype.deny"></a>*fsCollection*.deny(options)&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ###

*This method __deny__ is defined in `prototype` of `FS.Collection`*

__Arguments__

* __options__ *{object}*  
    * __download__ *{function}*  

    Function that checks if the file contents may be downloaded

    * __insert__ *{function}*  
    * __update__ *{function}*  
    * __remove__ *{function}*  

    Functions that look at a proposed modification to the database and return true if it should be denyed

    * __fetch__ *{[string]}*  (Optional)

    Optional performance enhancement. Limits the fields that will be fetched from the database for inspection by your update and remove functions

[Meteor docs](http://docs.meteor.com/#deny)
Example:
```js
var images = new FS.Collection( ... );
// Get the all file objects
var files = images.deny({
insert: function(userId, doc) { return true; },
update: function(userId, doc, fields, modifier) { return true; },
remove: function(userId, doc) { return true; },
download: function(userId, fileObj) { return true; },
});
```

> ```FS.Collection.prototype.deny = function(options) { ...``` [api.common.js:200](api.common.js#L200)

