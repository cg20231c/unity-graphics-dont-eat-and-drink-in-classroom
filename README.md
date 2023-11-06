| Nama | NRP |Github |  
|---------------------------|------------|--------|  
|Ihsan Widagdo | 5025211231 | https://github.com/dagdo03 |  

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