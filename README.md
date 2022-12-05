# Coding-One-Final-Project
Repository for the coding one final project

**MIMIC link:** https://mimicproject.com/code/e9298342-2ed7-7899-e402-b8180d359d1d


For my final project, I extended my homework from session 7 and created an interactive Three.js woodland scene. The majority of the objects are built using THREE.Groups, with each object defined in a separate class and instances of each created in the main scene script.

The scene is comprised of a few static objects. Each object is composed of multiple geometries grouped together and use various textures to render them more realistic. A few of the objects are animated. For instance, the sun (in the sunny scene) rotates around the skybox, using a pivot to rotate around the y-axis. The clouds move along the x-axis, resetting to the left of the skybox once they pass through the right side. Finally, the raindrops move down the y-axis, resetting to the cloud position once they reach the ground. Each of the animated objects call their own animate() function defined in their class. 

A few of the objects are randomised. Examples are the Tree class, which randomises the circumference and height of the tree, as well as the Cloud class, which randomises the size of the cloud. The trees are also placed randomly in a circle around the centre of the screen, and the clouds placed randomly on the x and z-axis in the sky.

If the user double clicks the screen, the scene will transition from a sunny scene to a rainy scene. Helper functions are defined to encapsulate this logic and toggle various objects on and off: changing the scene to rainy will render the sun invisible, add spotlights to the lamppost, create rainfall, add more clouds and change the colour of the sky and clouds. Going back to the sunny scene will undo these changes. Helper functions in the respective object classes were written in order to easily add/remove/change colours of instances. 

In the rainy scene, if a user clicks anywhere on the scene, a lightning bolt will appear and disappear two seconds later. The location of the bolt relies on the mouse x and y coordinates. Helper functions were written to draw a bolt and clear it after two seconds have elapsed (this is using Three.js Clock functionality). 

One of the main characteristics of the rainy scene is the use of rainfall. A separate class Rain() was created which extends the THREE.Points class, and uses a Float32Array() of x, y and z points to model individual raindrops. These coordinates are randomly generated and span the skybox. When the scene goes back to sunny, the rain is toggled off through use of a helper function. 

Finally, there are a few sources of lights in the scene, which change depending on if it’s a sunny or rainy scene. Ambient light is constant throughout. In the sunny scene, the sun emits a directional light targeted on the pond and moves with the sun. In the rainy scene, two spotlights are placed in the lamp posts and are toggled on, generating a glow on the two benches. These are toggled off again when sunny. 
