---
PG_TITLE: How To Update Vertices
---

# How To Update Vertices

## Vertex Data

The data contained in each of a mesh's vertices can be obtained from the vertex buffer. This data includes the position of and normal at the vertex 
as well as color and/or uv values. You can also obtain the indices for each vertex. 

```javascript
var positions = mesh.getVerticesData(BABYLON.VertexBuffer.PositionKind);
var normals = mesh.getVerticesData(BABYLON.VertexBuffer.NormalKind);
var colors = mesh.getVerticesData(BABYLON.VertexBuffer.ColorKind);
var uvs = mesh.getVerticesData(BABYLON.VertexBuffer.UVKind);

var indices = mesh.getIndices();
```
Each set of data is an array of numbers as detailed in [Creating Custom Meshes](/How_To/Custom.html). 

For example positions will be an array such as [-5, 2, -3, -7, -2, -3, -3, -2, -3, 5, 2, 3, 7, -2, 3, 3, -2, 3] and the  
indices array such as [0, 1, 2, 3, 4, 5] giving the following table.

index|position
-----|----
0| (-5, 2, -3)
1| (-7, -2, -3)
2| (-3, -2, -3)
3| (5, 2, 3)
4| (7, -2, 3)
5| (3, -2, 3)

## Updating the Data

Make sure that the mesh has been set as updatable on creation. Then this is just a matter of altering any of the data in the positions, normals, colors and uvs arrays to suit the project followed updating the vertex data 

```javascript
mesh.updateVerticesData(BABYLON.VertexBuffer.PositionKind, positions);
mesh.updateVerticesData(BABYLON.VertexBuffer.NormalKind, normals);
mesh.updateVerticesData(BABYLON.VertexBuffer.ColorKind, colors);
mesh.updateVerticesData(BABYLON.VertexBuffer.UVKind, uvs);
```

*Note: * When creating your own custom mesh to make it updatable you need to add a second parameter with value true when applying the mesh to  the vertex data.

```javascript
vertexData.applyToMesh(customMesh, true);
```

## Playgrounds

[Playground Example Scaling Positions](http://www.babylonjs-playground.com/#VE6GP#4)

[Playground Example Playing Around with Positions](http://www.babylonjs-playground.com/#VE6GP#2)


# Further Reading

[Custom Meshes](/How_To/Custom.html)  
[Normals in BJS](/resources/Normals)
