| Nama | NRP |Github |  
|---------------------------|------------|--------|  
|Ihsan Widagdo | 5025211231 | https://github.com/dagdo03 | 
|Lihardo Marson Purba | 5025211238 | https://github.com/Lihardo_238 |
|Dafarel Fatih Wirayudha | 5025211120 | https://github.com/Dafarelcky |

# Variety of Geometry
In the context of the Unity game engine, there are various geometries that can be used to create and manipulate 3D and 2D objects within the game environment.

## 2D Geometry
1. Points: The simplest form of geometry, representing a single coordinate in a 2D plane.
2. Lines: Composed of two points, lines can be used for various purposes, such as drawing outlines or constructing shapes.
3. Curves: These include various types like Bézier curves and splines. They are used for creating smooth and intricate shapes.

## 3D Geometry
1. Vertice
   - represented as a single Point in field
   ![Ss Soal1](Images/Screenshot%202023-11-06%20165525.png)

2. Edge
   - Consist of vertices and edge
   ![Ss Soal1](Images/Screenshot%202023-11-06%20172950.png)
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
    ![Ss Soal1](Images/Screenshot%202023-11-06%20195545.png)

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
Unity's Terrain settings are parameters and properties that allow you to configure and fine-tune the behavior and appearance of a terrain in your scene. These settings are accessible in the Terrain Inspector and provide control over various aspects of the terrain.
