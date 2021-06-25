# Opdracht6
Interaction headset

![grass](https://user-images.githubusercontent.com/86419683/123462596-d2c32500-d5ea-11eb-9a4e-bf834ce0b305.jpg)
![wood](https://user-images.githubusercontent.com/86419683/123462614-d787d900-d5ea-11eb-8e69-389490a7a5bf.jpg)
![wood2](https://user-images.githubusercontent.com/86419683/123462618-d8b90600-d5ea-11eb-80d9-3e2e117cdd64.jpg)

[main](https://github.com/lotteeymann/Opdracht6/blob/32ab00e162e65e3d3b34370e38dde88b9ed2752b/main.js)

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Hello, WebVR! • A-Frame</title>
    <meta name="viewport" content="width=device-width">
    <script src="https://aframe.io/releases/1.0.4/aframe.min.js"></script>
    <script src="main.js" defer></script>
  </head>
  <body>
    <a-scene background="color: #333333">
      <a-assets>
          <img id="wood" src="wood.jpg" />
          <img id="wood2" src="wood2.jpg" />
          <img id="grass" src="grass.jpg" />
      </a-assets>

      <a-camera>
        <a-entity id="mouseCursor"
          cursor="fuse: true; fuseTimeout: 1500">
        </a-entity>
        <a-ring id="cursorRing" 
          position="0 0 -1"
          radius-inner= "0.02"
          radius-outer= "0.03"
          material="color: red; shader: flat">
        </a-ring>
      </a-camera>
      
      <a-box id="myBox" 
        position="-1 1 -3" 
        rotation="0 45 0" 
        width="3" 
        height="1" 
        depth="1" 
        src="#wood"
        shadow 
        animation__mouseenter="
          property: components.material.material.color; 
          type: color; 
          to: blue; 
          startEvents: mouseenter; 
          dur: 500;"
        animation__mouseleave="
          property: components.material.material.color; 
          type: color; 
          to: red; 
          startEvents: mouseleave; 
          dur: 500;">  
      </a-box>
      <a-box id="myOtherBox" 
        position="2 1 -3" 
        rotation="0 45 0" 
        width="3" 
        height="1" 
        depth="1" 
        src="#wood2"
        shadow>  
      </a-box>
      <a-plane id="ground"
        position="0 0 -4" 
        rotation="-90 0 0" 
        width="100" 
        height="100" 
        color="#7BC8A4" 
        material="src: #grass; repeat: 10 10"
        shadow>
      </a-plane> 
    </a-scene>
  </body>
</html>
