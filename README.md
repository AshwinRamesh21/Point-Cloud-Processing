# Point-Cloud-Processing
This is a repository that is specifically created for the **Quaranteam Hackathon hosted by Codecadamy Central India Chapter.**

# Point Clouds
Point Clouds are datasets that represent objects or space. These points represent the X, Y, and Z geometric coordinates of a single point on an underlying sampled surface. They are a means of collating a large number of single spatial measurements into a dataset that can then represent a whole data. Usually, point clouds are 3D, but when colour information is present, the point cloud becomes 4D.  

![Point Clouds](https://miro.medium.com/max/3000/1*dfZrhF4dJEY6NP56Mg9i2A.png)
# 3D Meshes
Now, we know what point clouds are. We will look at another common term that is fairly associated with the world of 3D modelling and in this case, point clouds. That term is called 3D Mesh. 3D meshes are geometric data structures most often composed of a bunch of connected triangles that explicitly describe a surface. they are  the structural build of a 3D model consisting of polygons(in this case - triangles). 3D meshes use reference points in X, Y and Z axes to define shapes with height, width and depth.

![3D Mesh](https://images.squarespace-cdn.com/content/v1/5cb50c0dca525b5f7c4b4841/1592269273248-YR92Z81FBAKBV02IVZXK/flapping+remap+to+wireframe+mesh2_COMPACT.gif?format=750w)
# Levels of Details (LOD)
In computer graphics, level of detail (LOD) refers to the complexity of a 3D model representation. LOD can be decreased as the model moves away from the viewer or according to other metrics such as object importance, viewpoint-relative speed or position. LOD techniques increase the efficiency of rendering by decreasing the workload on graphics pipeline stages, usually vertex transformations.

![LOD](https://ars.els-cdn.com/content/image/1-s2.0-S0198971516300436-gr3.jpg)

There are 2 Algorithms used in this Project:
<ol>1. Ball-Pivoting Algorithm (BPA)</ol>
<ol>2. Poisson Reconstruction Algorithm</ol>

# Ball-Pivoting Algorithm (BPA)
It is a type of an algorithm, where we let a "ball" which is dependent on the scale of the mesh and also larger than the average of 2 points in the mesh to find the point cloud from the particular mesh.

When the ball is rolling, it will eventually get "stuck" upon 3 points which results in the formation of a **"Seed Triangle"**. From that location, the ball rolls along the triangle edge formed from two points. The ball then settles in a new location: a new triangle is formed from two of the previous vertices and one new triangle is added to the mesh. As we continue rolling and pivoting the ball, new triangles are formed and added to the mesh. The ball continues rolling and rolling until the mesh is fully formed.

The values of the variables like Radius of the ball and Average distances between the points are based on the size and scale of the input point cloud. Here, the smaller the Radius of the ball, more triangles, which results in more detailed mesh. Keep in mind that the number of the traingles in a mesh is directly proportional to the model's depth, clarity and definition. Be aware that it will increase the computational time and CPU usage.

![BPA](https://doc.cgal.org/latest/Advancing_front_surface_reconstruction/structured_example.png)
# Poisson Reconstruction 
The Poisson Reconstruction is a bit more mathematical as it involves computation of the implicit function along with the reconstruction of the surface based on the CGAL library's function Delaunay Refinement. Its approach is known as an implicit meshing method. To put it in simpler terms, we take a smooth cloth material and put it on the mesh which results in the watertight model. 

![PR](https://doc.cgal.org/latest/Poisson_surface_reconstruction_3/bimba.jpg)
# Final Stages - Export 
Once our meshes are generated, there are a lot of open-source 3D modelling software such as Blender and Meshlab. Download them, or you can either view them directly in Windows ny using the defualt 3D Model Viewer. Since, we are exporting the meshes direclty in **.ply (Polygon File Format)** format, it will be easy for us to load them and play with them in Blender.

## References
>[What are Point Clouds](https://info.vercator.com/blog/what-are-point-clouds-5-easy-facts-that-explain-point-clouds)
>[Transactions on Visualization and Computer Graphics, 1999 - The Ball-Pivoting Algorithm for Surface Reconstruction](https://vgc.poly.edu/~csilva/papers/tvcg99.pdf)
>[Eurographics Symposium on Geometry Processing, 2006 - Poisson Surface Reconstruction](https://hhoppe.com/poissonrecon.pdf)
>[Sampled Point Cloud Download Link](https://drive.google.com/drive/folders/1Ih_Zz9a6UcbUlaA-puEB_is7DYvXrb4w)
