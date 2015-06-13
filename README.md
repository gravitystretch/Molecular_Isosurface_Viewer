
# Molecular_Isosurface_Viewer
A WebGL App for playing with Metaballs and Small Molecules

SEE EXAMPLE HERE! https://classes.soe.ucsc.edu/cmps160/Spring15/projects/dsalisbu/final_project/code/PROTEIN_METABALLS.html

Implementation notes:

This program uses webgl and a very few THREE.js functions to render a pointset
as a meta ball surface.  I wrote this program as final project for a graphics 
class at UCSC. It recieved a second place recognition out of the 25 or so projects.

Marching cubes code:  I based much of my meta ball implementation from code by Nicholas at
http://philogb.github.io/blog/2010/12/10/animating-isosurfaces-with-webgl-and-workers/.
This implematation uses web workers to parallelize computing the isovalues at each point
in the 3D grid.  Much of my conceptual understanding of marching cubes came from 
 http://paulbourke.net/geometry/polygonise/. 

Environment mapping:  Environment mapping was implemented by rendering six faces of cube and mapping a texture to each.
A reflection vector was then calculated from the point of view of the camera, and then mapped to one of the textures
based on the angle of the refletion vector.  My reflections are not perfect if you look closely.  I was wasn't able to
get a texture cube to render, so I mapped reflections to textures by finding which dimension of the vector had
the largest component, and using that to pick which cube map to map to.  The other two direction components were used to
map the coordinates on the texture. 
