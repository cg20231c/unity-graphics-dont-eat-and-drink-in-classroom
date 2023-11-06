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

### Procedural Geometry
Procedural geometry in Unity refers to the process of generating and manipulating 3D or 2D shapes and models dynamically at runtime, without relying on pre-made assets. Instead of using static meshes or models, procedural geometry involves algorithmic generation or modification of geometric shapes, terrains, or structures to create dynamic and customizable content.

The main advantage of procedural geometry lies in its ability to generate complex or varied content on the fly, which can be particularly useful for creating dynamic and adaptive environments, terrains, levels, or objects in games and simulations. This approach allows developers to create intricate and diverse content without having to manually design and model every detail, thereby saving time and resources and enabling the creation of rich, varied, and realistic virtual worlds.

Here is the example of procedural geometry :
![Alt text](<img/procedgeo.png>)

Here is the code of the procedural geometry that we have created : 
```c#
public class ProceduralGeometry : MonoBehaviour
{
    void Start()
    {
        // Create a new empty mesh
        Mesh mesh = new Mesh();

        // Define the vertices for a cube
        Vector3[] vertices = new Vector3[8];
        vertices[0] = new Vector3(0, 0, 0);
        vertices[1] = new Vector3(1, 0, 0);
        vertices[2] = new Vector3(1, 1, 0);
        vertices[3] = new Vector3(0, 1, 0);
        vertices[4] = new Vector3(0, 0, 1);
        vertices[5] = new Vector3(1, 0, 1);
        vertices[6] = new Vector3(1, 1, 1);
        vertices[7] = new Vector3(0, 1, 1);

        // Define the triangles using vertex indices
        int[] triangles = new int[]
        {
            0, 2, 1, 0, 3, 2, // Front face
            4, 5, 6, 4, 6, 7, // Back face
            0, 1, 5, 0, 5, 4, // Bottom face
            2, 3, 7, 2, 7, 6, // Top face
            1, 2, 6, 1, 6, 5, // Right face
            0, 4, 7, 0, 7, 3  // Left face
        };

        // Assign vertices and triangles to the mesh
        mesh.vertices = vertices;
        mesh.triangles = triangles;

        // Recalculate normals and bounds
        mesh.RecalculateNormals();
        mesh.RecalculateBounds();

        // Create a new game object
        GameObject cubeObject = new GameObject("ProceduralCube");

        // Add a mesh filter and renderer to the object
        cubeObject.AddComponent<MeshFilter>().mesh = mesh;
        cubeObject.AddComponent<MeshRenderer>().material = new Material(Shader.Find("Standard"));

        // Set the position of the object in the scene
        cubeObject.transform.position = new Vector3(0, 0, 0);
    }
}

```

### Particle Systems

In Unity, a particle system is a specialized graphical effect that simulates the behavior of particles such as fire, smoke, rain, snow, or other visual elements. Particle systems are used to create various visual effects, including explosions, magical spells, weather effects, and environmental phenomena, to enhance the overall visual quality and immersion of a game or application.

Unity's built-in Particle System allows developers to create and customize complex particle effects directly within the Unity Editor. It provides a wide range of parameters and settings that enable the manipulation of particle properties such as color, size, shape, emission rate, velocity, and lifetime. These settings can be adjusted to achieve various visual effects and behaviors, allowing for the creation of dynamic and realistic particle simulations.

Here is the example of particle systems in unity :
![Alt text](<img/particle.gif>)

Here is the code for particle script : 
```c#
public class CreateParticle : MonoBehaviour
{
    void Start()
    {
        // Create a new GameObject for the particle system
        GameObject particleObject = new GameObject("Particle System");

        // Add the ParticleSystem component
        ParticleSystem particleSystem = particleObject.AddComponent<ParticleSystem>();

        // Configure the particle system
        var mainModule = particleSystem.main;
        mainModule.startColor = Color.blue;
        mainModule.startSize = 0.2f;

        // Create and configure the shape module
        var shapeModule = particleSystem.shape;
        shapeModule.shapeType = ParticleSystemShapeType.Sphere;
        shapeModule.radius = 1f;

        // Create and configure the emission module
        var emissionModule = particleSystem.emission;
        emissionModule.rateOverTime = 10;

        // Play the particle system
        particleSystem.Play();
    }
}

```
## 2D Geometry
1. Points: The simplest form of geometry, representing a single coordinate in a 2D plane.
2. Lines: Composed of two points, lines can be used for various purposes, such as drawing outlines or constructing shapes.
3. Curves: These include various types like Bézier curves and splines. They are used for creating smooth and intricate shapes.

## 3D Geometry
1. Vertice
   - represented as a single Point in field
   ![Ss Soal1](img/Screenshot%202023-11-06%20165525.png)

2. Edge
   - Consist of vertices and edge
   ![Ss Soal1](img/Screenshot%202023-11-06%20172950.png)
   Here is the code for line :
  ```C#
using UnityEngine;

public class LineDrawer : MonoBehaviour
{
    public LineRenderer lineRenderer;

    void Start()
    {
        lineRenderer = GetComponent<LineRenderer>();

        // Set the position count to 2 for a straight line.
        lineRenderer.positionCount = 2;

        // Set the start and end positions of the line.
        lineRenderer.SetPosition(0, new Vector3(0, 0, 0));
        lineRenderer.SetPosition(1, new Vector3(1, 1, 1));

        // Customize the Line Renderer properties.
        lineRenderer.startWidth = 0.1f;  // Adjust the width as needed.
        lineRenderer.endWidth = 0.1f;    // Adjust the width as needed.

        // Disable the line renderer's useWorldSpace property to ensure local space coordinates.
        lineRenderer.useWorldSpace = false;
    }
}


  ```
3. Mesh
   - A mesh is a collection of vertices, edges, and faces that represent the shape and structure of a 3D object. These components are organized in a way that allows the object to be rendered and interact with other objects in the game world. 
    ![Ss Soal1](img/Screenshot%202023-11-06%20195545.png)

    Here's the code for mesh above :
```C#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CustomMesh : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        Mesh mesh = new Mesh();
        mesh.vertices = new Vector3[]
        {
            new Vector3(0, 0, 0), // Vertex 1
            new Vector3(5, 0, 0), // Vertex 2
            new Vector3(10, 5, 0), // Vertex 3
            new Vector3(0,0,-3),
            new Vector3(5,0,-3),
            new Vector3(10,5,-3),
        };

        mesh.triangles = 
            new int[] { 0, 1, 2,
                        0, 2, 3,
                        3, 2, 5,
                        5, 3, 4,
                        4, 1, 5,
                        5, 2, 1,
                        1, 4, 3,
                        3, 0, 1
                        }; // Triangle indices
        // Optional: Define UV coordinates for textures (if using textures)
        mesh.uv = new Vector2[]
        {
            //left triangle
            new Vector2(0, 0),
            new Vector2(0, 1),
            new Vector2(1, 0),
            //top part - left
            new Vector2(0, 1),
            new Vector2(0, 0),
            new Vector2(1, 0),
            //top part - right
            new Vector2(1, 0),
            new Vector2(1, 1),
            new Vector2(0, 1),
            //right part
            new Vector2(0, 0),
            new Vector2(1, 0),
            new Vector2(1, 1),
            //back part - left
            new Vector2(0, 1),
            new Vector2(0, 0),
            new Vector2(1, 0),
            //back part - right
            new Vector2(1, 0),
            new Vector2(1, 1),
            new Vector2(0, 1),
            //down part - left
            new Vector2(0, 0),
            new Vector2(0, 1),
            new Vector2(1, 1),
            //down part - right
            new Vector2(0, 0),
            new Vector2(1, 0),
            new Vector2(1, 1)
        };

        mesh.RecalculateNormals(); // Recalculate normals for lighting

        // Assign the created mesh to the Mesh Filter component
        GetComponent<MeshFilter>().mesh = mesh;
    }

    // Update is called once per frame
    void Update()
    {
        // Add any update logic here if needed
    }
   }


   ```

## Terrain
-   In Unity, a "Terrain" refers to a type of object used to create and represent outdoor environments, such as landscapes, mountains, forests, and other natural terrains. Unity provides a Terrain system, which is a built-in feature that allows developers to generate and manipulate terrains within their game or application. Terrains are commonly used to create large outdoor scenes, open-world environments, or terrain-based simulations.

There are 5 main part of sub-utils in terrain :
1. Create Neighbor Terrains
-   The "Create Neighbor Terrains" sub-utils in Unity's Terrain Inspector allow you to generate neighboring terrains that seamlessly connect to the edges of an existing terrain. This is particularly useful when you want to create a larger, continuous terrain by tiling or stitching multiple terrains together.
2. Paint Terrain
-   The "Paint Terrain" sub-utils in Unity's Terrain Inspector allow you to paint textures and details onto your terrain. This is essential for adding ground textures, such as grass, sand, rocks, or dirt, to make your terrain look realistic.
3. Paint Trees
-   Painting trees on a Unity terrain is a crucial aspect of creating realistic outdoor environments. The "Paint Trees" tool in the Terrain Inspector enables you to place trees on your terrain to add vegetation and create lush, natural landscapes.
4. Paint Details
-   Painting details on a Unity terrain, such as grass, flowers, rocks, or other small objects, can significantly enhance the visual quality and realism of outdoor scenes. The "Paint Details" tool in the Terrain Inspector allows you to place and customize these small objects.
5. Terrain Settings
-    Unity's Terrain settings are parameters and properties that allow you to configure and fine-tune the behavior and appearance of a terrain in your scene. These settings are accessible in the Terrain Inspector and provide control over various aspects of the terrain.
