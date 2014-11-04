quadtree
========

My quadtree implementation in javascript.

How to use:
```javascript
var maxW = 2000,
  maxH = 1100;
// generating elements
var elements = [];
for (var i = 0; i < 5000; i ++) {
  elements.push({x: Math.round(maxW * Math.random()), y: Math.round(maxH * Math.random()), w: 1, h: 1});
}
// initializing the index
var options = {
  top: 0,
  left: 0,
  bottom: maxH,
  right: maxW,
  max_depth: 1,
  max_per_cell: 20,
  debug_mode: true
};
var tree = quadtree(options);
// insert elements into the index
tree.insert(elements);

// getting all items close to myObj (x+- w /2 and y +- h/2)
var myObj = {x: 1000, y: 1000, h: 20, w: 30};
  var items = tree.queryContainedBy(myObj);
  console.log( items );
```

Examples 
-----
In *.html files.

Canvas example is also available here:
http://jsbin.com/lesudu/1/ (http://jsbin.com/lesudu/1/edit)

Links
-----
https://en.wikipedia.org/wiki/Quadtree

License
----- 
MIT
