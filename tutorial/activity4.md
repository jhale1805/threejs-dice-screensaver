# Activity 4: Interactive Scenes

## Activity Example
- [Activity 4: Interactive Scenes](../activities/activity4.html)


After adding our objects to our scene, we can actually manipulate them with document manipulation, in adding an on mouse event to track the movement of our mouse and to add movement for your objects. 

This code manipulates the camera by adjusting where it is positioned, pushes it to the scene, and makes the camera look directly at the scene we are creating. We then make our event code to represent the actions needed to track our mouse.

```javascript
// Back up the camera so the cube is within the camera's 
// view and add camera to the scene
camera.position.set(0, 0, 5);
scene.add(camera);
camera.lookAt(scene.position);

// Redraw the scene on the browser window to see the 3D cube
renderer.render(scene, camera);
var mouse = { x: 0, y: 0 };

function onMouseMove(event) {
  event.preventDefault();
  mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
  mouse.y = - (event.clientY / window.innerHeight) * 2 + 1;
  // Make the cube follow the mouse
  var vector = new THREE.Vector3(mouse.x, mouse.y, 0.5);
  vector.unproject(camera);
  var dir = vector.sub(camera.position).normalize();
  var distance = - camera.position.z / dir.z;
  var pos = camera.position.clone().add(dir.multiplyScalar(distance));
  cube.position.copy(pos);
};
document.addEventListener('mousemove', onMouseMove, false);

```

At this point in time, your cube should be tracking your mouse movements and you should see the position update while you are activating the `mousemove` event listener.

![Cube Follows Mouse Movement](./images/mouse_move.gif)
 
If you're having trouble, feel free to compare your code with the example solution contained in [`activity4.html`](../activities/activity4.html).

When you're ready, go ahead and move on to [Activity 5](./activity5.md)!

### Applicable Learning Outcomes:
#### Learning Outcome 1: Geometries and Meshes
The student will be able to use THREE.js to draw basic 3D objects in a web browser.
#### Learning Outcome 3: Animation
The student will be able to create a basic render loop in THREE.js to create visible animations of 3D objects in the browser window.
#### Learning Outcome 4: Interactivity
The student will be able to connect 3D objects to browser events to dynamically move and manipulate objects on the scene in response to user input.