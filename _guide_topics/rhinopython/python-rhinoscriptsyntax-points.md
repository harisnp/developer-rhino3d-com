---
title: Points in Python
description: This guide provides an overview of the RhinoScriptSytntax point geometry in Python.
authors: ['Scott Davidson']
author_contacts: ['scottd']
apis: ['RhinoPython']
languages: ['Python']
platforms: ['Mac', 'Windows']
categories: ['Python in Rhino']
origin:
order: 2
keywords: ['script', 'Rhino', 'python']
layout: toc-guide-page
---
 
## Points

In Python, a Rhino 3D point is represented as a [Point3d](http://developer.rhino3d.com/api/RhinoCommonWin/html/T_Rhino_Geometry_Point3d.htm) structure. Conceptually, Point3d exist in memory as a zero-based list containing three numbers.  These three numbers represent the X, Y and Z coordinate values of the point.

```
point3D contains [1.0, 2.0, 3.0]  
```

A Point3D structure can be constructed in a number of different ways.  Two common ways are:

```
import rhinoscriptsyntax as rs

pnt = rs.CreatePoint(1.0, 2.0, 3.0)
pnt = rs.CreatePoint(1.0, 2.0) # This creates a point with the Z coordinate set to 0
```

A point3D list can be accessed like a simple python list, one element at a time:

```python
import rhinoscriptsyntax as rs

pnt = rs.CreatePoint(1.0, 2.0, 3.0)

print(pnt[0]) #Prints the X coordinate of the Point3D
print(pnt[1]) #Print the Y coordinate of the Point3D
print(pnt[2]) #Print the Z coordinate of the Point3D
```

The coordinates of a Point3d may also be accessed through its .X, .Y and .Z property.

```python
import rhinoscriptsyntax as rs

pnt = rs.CreatePoint(1.0, 2.0, 3.0)

print(pnt.X) # Prints the X coordinate of the Point3D
print(pnt.Y) # Print the Y coordinate of the Point3D
print(pnt.Z) # Print the Z coordinate of the Point3D
```

To change an individual coordinate of a Point3d simply assign a new value to the correct coordinate through the index location or coordinate property:

```python
import rhinoscriptsyntax as rs

pnt = rs.CreatePoint(1.0, 2.0, 3.0)

pnt[0] = 5.0 # Sets the X coordinate to 5.0
pnt.Y = 45.0 # Sets the Y coordinate to 45.0

print(pnt) #Print the Z coordinate
```

The 'CreatePoint()' function is very flexible.  It can take a list or tuple of tow or 3 numbers and return a Point3d.  The function can also extract the coordinates of a Rhino GUID to return a Point3D.

Rhinoscriptsyntax contains a number of methods to manipulate points.  See [RhinoScript Points and Vectors Methods]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-point-vector-methods) for details.

For those familar with RhinoScript which represents points as a pure list, the Python represtnation is a little different and offers a few more options.

It is important to understand the difference betweene a Point3d and a Guid of a point in Rhino.  A Guid is an identifier of an object in the Rhino document. The Guid's object is something that can be drawn, belongs to a layer and is counted as a Rhino object.  A Point3d is simply a structure of 3 numbers that exists in memory.  It can be manipulated in memory, but will not be seen or saved in Rhino unless it is added to the Rhino document through the `rs.AddPoint()` command.

---

## Related Topics

- [What is RhinoScriptSyntax and RhinoScript?]({{ site.baseurl }}/guides/rhinopython/what-are-python-rhinoscript)
- [Python List of Points]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-list-points)
- [Python Vectors]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-vectors)
- [Python Lines]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-lines)
- [Python Planes]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-plane)
- [Python Objects]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-objects)
- [RhinoScript Points and Vectors Methods]({{ site.baseurl }}/guides/rhinopython/python-rhinoscriptsyntax-point-vector-methods)
- [Point3d RhinoCommon Documentation](http://developer.rhino3d.com/api/RhinoCommonWin/html/T_Rhino_Geometry_Point3d.htm)