| Nama | NRP |Github |  
|---------------------------|------------|--------|  
|Ihsan Widagdo | 5025211231 | https://github.com/dagdo03 | 
|Lihardo Marson Purba | 5025211238 | https://github.com/Lihardo_238 |
|Dafarel Fatih Wirayudha | 5025211120 | https://github.com/Dafarelcky |

# Variety of Geometry
In the context of the Unity game engine, there are various geometries that can be used to create and manipulate 3D and 2D objects within the game environment. Some of the commonly used geometric shapes and concepts in Unity include:

1. Meshes: Unity allows you to create complex 3D models using meshes. Meshes can be imported from external 3D modeling software or created directly within Unity using the built-in tools. Meshes can be composed of vertices, edges, and faces, and they form the basis for most 3D models in Unity.

2. Primitives: Unity provides built-in primitive objects, such as cubes, spheres, cylinders, and planes, which can be used as basic building blocks for creating 3D scenes. These primitives can be easily manipulated, scaled, and textured to create more complex objects.

3. Geometry dimension: Unity supports various types of curves, including Bézier curves and splines, which can be used to create smooth and curved paths for animations and object movements.

4. Procedural Geometry: Unity provides support for handling lines and vectors, which are essential for performing mathematical operations and calculations in 2D and 3D space.

5. Terrain: Unity offers a built-in terrain system that allows developers to create realistic landscapes and environments. This terrain system enables the creation of terrains with various features such as hills, valleys, textures, and foliage.

6. Particles: Unity's particle system allows developers to create various special effects, such as fire, smoke, water, and explosions. These particle systems use geometry to represent and simulate the behavior of these effects in the game world.

These are some of the key geometric concepts and elements that are commonly used in Unity to create and design game environments, objects, and effects. By leveraging these geometric tools, developers can build visually appealing and immersive experiences for players.

### Meshes
In geometry, a mesh typically refers to a collection of vertices, edges, and faces that define the shape of a three-dimensional object. These elements are fundamental in creating 3D models and are extensively used in computer graphics, simulations, and various fields involving 3D design.

Here's a breakdown of the components of a mesh:

1. Vertices (or Points): These are individual points in a 3D space. They are defined by their coordinates (x, y, z) and act as the building blocks of the mesh.
2. Edges: Edges are the lines connecting pairs of vertices. They form the basic structure of the mesh, outlining the shape and providing a framework for the faces.
3. Faces (Polygons): Faces are flat surfaces formed by connecting three or more vertices with edges. They enclose a space and define the surface of the mesh. Common types of faces are triangles (3 vertices), quadrilaterals (4 vertices), and more complex polygons.

Here's the example to create a simple mesh using code:
```c
using UnityEngine;

public class CreateMesh : MonoBehaviour
{
    void Start()
    {
        // Create a new mesh
        Mesh mesh = new Mesh();

        // Define the vertices of the mesh
        Vector3[] vertices = new Vector3[62];
        // F Front face
        vertices[0] = new Vector3(0.3f, 0f, 0.1f);
        vertices[1] = new Vector3(0.35f, 0f, 0.1f);
        vertices[2] = new Vector3(0.35f, 1f, 0.1f);
        vertices[3] = new Vector3(0.3f, 1f, 0.1f);
        vertices[4] = new Vector3(0.3f, 0.95f, 0.1f);
        vertices[5] = new Vector3(0.65f, 0.95f, 0.1f);
        vertices[6] = new Vector3(0.65f, 1f, 0.1f);
        vertices[7] = new Vector3(0.3f, 0.525f, 0.1f);
        vertices[8] = new Vector3(0.3f, 0.475f, 0.1f);
        vertices[9] = new Vector3(0.65f, 0.475f, 0.1f);
        vertices[10] = new Vector3(0.65f, 0.525f, 0.1f);

        // F Back face
        vertices[11] = new Vector3(0.3f, 0f, -0.1f);
        vertices[12] = new Vector3(0.35f, 0f, -0.1f);
        vertices[13] = new Vector3(0.35f, 1f, -0.1f);
        vertices[14] = new Vector3(0.3f, 1f, -0.1f);
        vertices[15] = new Vector3(0.3f, 0.95f, -0.1f);
        vertices[16] = new Vector3(0.65f, 0.95f, -0.1f);
        vertices[17] = new Vector3(0.65f, 1f, -0.1f);
        vertices[18] = new Vector3(0.3f, 0.525f, -0.1f);
        vertices[19] = new Vector3(0.3f, 0.475f, -0.1f);
        vertices[20] = new Vector3(0.65f, 0.475f, -0.1f);
        vertices[21] = new Vector3(0.65f, 0.525f, -0.1f);

        // F Left face
        vertices[22] = new Vector3(0.3f, 0f, 0.1f);
        vertices[23] = new Vector3(0.3f, 0f, -0.1f);
        vertices[24] = new Vector3(0.3f, 1f, -0.1f);
        vertices[25] = new Vector3(0.3f, 1f, 0.1f);

        // F Right face
        vertices[26] = new Vector3(0.65f, 0.95f, -0.1f);
        vertices[27] = new Vector3(0.65f, 1f, -0.1f);
        vertices[28] = new Vector3(0.65f, 1f, 0.1f);
        vertices[29] = new Vector3(0.65f, 0.95f, 0.1f);
        vertices[30] = new Vector3(0.35f, 0.95f, 0.1f);
        vertices[31] = new Vector3(0.35f, 0.95f, -0.1f);
        vertices[32] = new Vector3(0.35f, 0.525f, -0.1f);
        vertices[33] = new Vector3(0.35f, 0.525f, 0.1f);
        vertices[34] = new Vector3(0.65f, 0.525f, 0.1f);
        vertices[35] = new Vector3(0.65f, 0.525f, -0.1f);
        vertices[36] = new Vector3(0.65f, 0.475f, -0.1f);
        vertices[37] = new Vector3(0.65f, 0.475f, 0.1f);
        vertices[38] = new Vector3(0.35f, 0.475f, 0.1f);
        vertices[39] = new Vector3(0.35f, 0.475f, -0.1f);
        vertices[40] = new Vector3(0.35f, 0f, -0.1f);
        vertices[41] = new Vector3(0.35f, 0f, 0.1f);

        // F Top face
        vertices[42] = new Vector3(0.3f, 1f, 0.1f);
        vertices[43] = new Vector3(0.3f, 1f, -0.1f);
        vertices[44] = new Vector3(0.65f, 1f, -0.1f);
        vertices[45] = new Vector3(0.65f, 1f, 0.1f);
        vertices[46] = new Vector3(0.35f, 0.525f, 0.1f);
        vertices[47] = new Vector3(0.35f, 0.525f, -0.1f);
        vertices[48] = new Vector3(0.65f, 0.525f, -0.1f);
        vertices[49] = new Vector3(0.65f, 0.525f, 0.1f);

        // F Bottom face
        vertices[50] = new Vector3(0.3f, 0f, 0.1f);
        vertices[51] = new Vector3(0.3f, 0f, -0.1f);
        vertices[52] = new Vector3(0.35f, 0f, -0.1f);
        vertices[53] = new Vector3(0.35f, 0f, 0.1f);
        vertices[54] = new Vector3(0.35f, 0.475f, 0.1f);
        vertices[55] = new Vector3(0.35f, 0.475f, -0.1f);
        vertices[56] = new Vector3(0.65f, 0.475f, -0.1f);
        vertices[57] = new Vector3(0.65f, 0.475f, 0.1f);
        vertices[58] = new Vector3(0.35f, 0.95f, 0.1f);
        vertices[59] = new Vector3(0.35f, 0.95f, -0.1f);
        vertices[60] = new Vector3(0.65f, 0.95f, -0.1f);
        vertices[61] = new Vector3(0.65f, 0.95f, 0.1f);


        // Define the triangles of the mesh
        int[] triangles = new int[96] { 0, 1, 2, 0, 2, 3, 2, 4, 5, 2, 5, 6, 7, 8, 9, 7, 9, 10, // F Front face
        11, 12, 13, 11, 13, 14, 13, 15, 16, 13, 16, 17, 18, 19, 20, 18, 20, 21, // F Back face
        22, 23, 24, 22, 24, 25, // F Left face
        26, 27, 28, 26, 28, 29, 30, 31, 32, 30, 32, 33, 34, 35, 36, 34, 36, 37, 38, 39, 40, 38, 40, 41, // F Right face
        42, 43, 44, 42, 44, 45, 46, 47, 48, 46, 48, 49, // F Top face
        50, 51, 52, 50, 52, 53, 54, 55, 56, 54, 56, 57, 58, 59, 60, 58, 60, 61, // F Bottom face
        };

        // Assign the vertices and triangles to the mesh
        mesh.vertices = vertices;
        mesh.triangles = triangles;

        // Recalculate the bounds of the mesh
        mesh.RecalculateBounds();

        // Create a new game object
        GameObject meshObject = new GameObject("CustomMesh");

        // Add a mesh filter and renderer to the game object
        meshObject.AddComponent<MeshFilter>().mesh = mesh;
        meshObject.AddComponent<MeshRenderer>().material = new Material(Shader.Find("Standard"));
    }
}
```
Here's the result:
![Alt text](<mesh.png>)

### Primitive Object
A primitive object typically refers to simple and standard shapes or elements that serve as the building blocks for creating more complex 3D models. These primitives are basic geometrical shapes and include objects like:

When discussing 3D objects and geometry in computer graphics, a "primitive object" typically refers to simple and standard shapes or elements that serve as the building blocks for creating more complex 3D models. These primitives are basic geometrical shapes and include objects like:

1. Cube/Box: A six-sided object where each side is a square. It's often referred to as a box or a cube. Each face is made up of two triangles, so it has 12 triangles or faces in total.

2. Sphere: A perfectly round geometrical object where all points on its surface are equidistant from the center point. It's made up of many vertices, edges, and faces (triangles) to approximate its round shape.

3. Cylinder: A solid geometric figure with straight parallel sides and a circular or oval cross-section. It has three major components: the top and bottom circular faces and the curved side.

4. Cone: Similar to a cylinder but with a pointed top at a single vertex and a circular base. It also has a curved surface connecting the base to the vertex.

5. Plane/Quad: A flat, two-dimensional surface defined by four vertices and two triangles. It's also called a quad when it consists of four sides forming a rectangle.

Here's the example to create a primitive object using code:
```c

```
