# Car model

Put your exported car model here:

```txt
public/models/ae86.glb
```

The driving scene automatically checks for `/models/ae86.glb`.
If the file exists, it loads that model. If it does not exist, the temporary
low-poly fallback car is used so the site still runs.

Use a `.glb` file when possible. It is the easiest format for Three.js because
the geometry, materials, and textures can be packed into one file.

If your model appears too big, too small, sideways, or backwards, adjust this
object in `src/components/DrivingWorld.jsx`:

```js
const carModel = {
  url: '/models/ae86.glb',
  length: 1.35,
  position: [0, 0.02, 0],
  rotation: [0, 0, 0],
}
```

`length` is the desired in-game model length. The app automatically centers and
scales the imported model so unusually huge Sketchfab exports do not cover the
whole scene.
