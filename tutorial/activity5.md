# Activity 5: Advanced Interactivity

## Activity Example
- [Activity 5: Advanced Interactivity](../activities/activity5.html)

Now that we have our object following our mouse activity, why not add a little behavior to these movements? 

Currently the mouse tracking happens with a mapping of mouse position to the cube position with no consideration of mouse presses or some separation of behaviors, so lets require mouse down to move the object, and ray intersection to ensure the user is actually clicking on that object for movement!

```javascript
//simple boolean to track mouse presses
var down = false;
function onMouseMove(event) {
  ////////////////////////////////////Same behavior as activity 4
  event.preventDefault();
  mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
  mouse.y = - (event.clientY / window.innerHeight) * 2 + 1;
  // Make the sphere follow the mouse
  var vector = new THREE.Vector3(mouse.x, mouse.y, 0.5);
  vector.unproject(camera);
  var dir = vector.sub(camera.position).normalize();
  var distance = - camera.position.z / dir.z;
  var pos = camera.position.clone().add(dir.multiplyScalar(distance));
  ///////////////////////////////////
  var mouse3D = new THREE.Vector3((event.clientX / window.innerWidth) * 2 - 1,
    -(event.clientY / window.innerHeight) * 2 + 1,
    0.5);
  //check for intersection with cube
  var raycaster = new THREE.Raycaster();
  raycaster.setFromCamera(mouse3D, camera);
  var intersects = raycaster.intersectObject(cube);

  if (intersects.length > 0) {
    console.log(intersects[0]);
    //if mouse is pressed down
    if (down) {
      cube.position.copy(pos);
    }
  }
};

document.addEventListener('mousemove', onMouseMove, false);
document.addEventListener('mousedown', function () {
  down = true;
});
document.addEventListener('mouseup', function () {
  down = false;
});
```
At this point in time, your mouse should now follow your mouse when you have pressed the mouse button down and will only react to the interactions of the mouse when you are over the cube with a mouse button pressed.

![Cube Mouse Down Following](./images/mouse_down.gif)

If you're having trouble, feel free to compare your code with the example solution contained in [`activity5.html`](../activities/activity5.html).

When you're ready, go ahead and move on to [Activity 6](./activity6.md)!

### Applicable Learning Outcomes:
#### Learning Outcome 1: Geometries and Meshes
The student will be able to use THREE.js to draw basic 3D objects in a web browser.
#### Learning Outcome 3: Animation
The student will be able to create a basic render loop in THREE.js to create visible animations of 3D objects in the browser window.
#### Learning Outcome 4: Interactivity
The student will be able to connect 3D objects to browser events to dynamically move and manipulate objects on the scene in response to user input.
