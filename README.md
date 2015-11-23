###### Graphics Programming - Exercise 9
# Introduction to 3D

In this exercise we will look at 3D using the HTML5 Canvas.

## Exercises
Save each exercise as a separate source file:

1. Create a blank HTML file.
    
    ```html 
    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="UTF-8">
        <title></title>
        <style type="text/css">
          ...
        </style>
      </head>
      <body>
        ...
        <script type="text/javascript"></script>
      </body>
    </html>
    ```

1. Download three.js and add it to your HTML file.

1. Add a renderer.

    ```js
    var renderer = new THREE.WebGLRenderer();
    renderer.setSize(400, 300);
    document.body.appendChild(renderer.domElement);
    ```

1. Add a scene.

    ```js
    var scene = new THREE.Scene();
    ```

1. Add a sphere to the scene.

    ```js
    var sphere_geom = new THREE.SphereGeometry(0.5, 12, 12);
    var sphere_mat = new THREE.MeshBasicMaterial({color: 0xff66ff});
    var sphere = new THREE.Mesh(sphere_geom, sphere_mat);
    scene.add(sphere); 
    ```

1. Add a camera.

    ```js
    var camera = new THREE.PerspectiveCamera(75, 400/300, 1, 1000);
    camera.position.z = 2;
    ``` 
    
1. Add and call a step() function which rotates the sphere.

    ```js
    var step = function () {
      sphere.rotateX(Math.PI/180);
      sphere.rotateY(Math.PI/180);
      renderer.render(scene, camera);
      requestAnimationFrame(step);
    };
    step();
    ```

1. View your sphere.

1. Add a directional light.

    ```js
    var directionalLight = new THREE.DirectionalLight(0xffffff, 0.5);
    directionalLight.position.set(0, 1, 2);
    scene.add(directionalLight);
    ```

1. Change your material to a Lambert material.

    ```js
    var material = new THREE.MeshLambertMaterial({color: 0xff66ff});
    ```

1. Now view your sphere.

1. Have your sphere move over back from left to right on the canvas.

## Advanced exercises

1. Have the sphere slowly change in colour.

1. Add another sphere that moves from top to bottom.

1. Write a function that returns true if the spheres are touching or in collision and false otherwise.

## Notes

- [Creating a scene](http://threejs.org/docs/#Manual/Introduction/Creating_a_scene) from threejs.org.

