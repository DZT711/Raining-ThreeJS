<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>3D Rain Simulation - Three.js</title>
  <style>
    /* Reset margins and eliminate scrollbars for a clean, full-screen canvas */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    html, body {
      width: 100%;
      height: 100%;
      overflow: hidden;
      background-color: #050811; /* Deep midnight-blue base */
    }
    #webgl-canvas {
      display: block;
      width: 100%;
      height: 100%;
    }
  </style>

  <!-- Import maps polyfill for ES module imports via CDN -->
  <script type="importmap">
    {
      "imports": {
        "three": "https://unpkg.com/three@0.160.0/build/three.module.js"
      }
    }
  </script>
</head>
<body>
  <canvas id="webgl-canvas"></canvas>

  <script type="module">
    import * as THREE from 'three';

    // -------------------------------------------------------------
    // 1. Scene & Render Setup
    // -------------------------------------------------------------
    const canvas = document.getElementById('webgl-canvas');
    const scene = new THREE.Scene();

    // Add a dark foggy atmosphere for depth
    scene.background = new THREE.Color(0x0a0e1a);
    scene.fog = new THREE.FogExp2(0x0a0e1a, 0.002);

    // Perspective camera overlooking the field
    const camera = new THREE.PerspectiveCamera(
      60,
      window.innerWidth / window.innerHeight,
      0.1,
      1000
    );
    camera.position.set(0, 50, 160);
    camera.lookAt(0, 0, 0);

    // WebGLRenderer with anti-aliasing enabled
    const renderer = new THREE.WebGLRenderer({
      canvas,
      antialias: true
    });
    renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
    renderer.setSize(window.innerWidth, window.innerHeight);

    // -------------------------------------------------------------
    // 2. Raindrop Particle System Configuration
    // -------------------------------------------------------------
    const RAIN_COUNT = 15000;
    const BOUNDS = {
      x: 350,
      yMin: -100,
      yMax: 200,
      z: 350
    };

    // Arrays to store position coordinates and individual drop velocities
    const positions = new Float32Array(RAIN_COUNT * 3);
    const velocities = new Float32Array(RAIN_COUNT);

    // Initialize particles across a wide 3D bounding box
    for (let i = 0; i < RAIN_COUNT; i++) {
      const i3 = i * 3;

      // Uniform random distribution in 3D space
      positions[i3]     = (Math.random() - 0.5) * BOUNDS.x * 2; // X
      positions[i3 + 1] = Math.random() * (BOUNDS.yMax - BOUNDS.yMin) + BOUNDS.yMin; // Y
      positions[i3 + 2] = (Math.random() - 0.5) * BOUNDS.z * 2; // Z

      // Slight random downward velocity for natural variation (between 2.5 and 4.5 units/frame)
      velocities[i] = 2.5 + Math.random() * 2.0;
    }

    // Assign positions to BufferGeometry
    const rainGeometry = new THREE.BufferGeometry();
    rainGeometry.setAttribute('position', new THREE.BufferAttribute(positions, 3));

    // Semi-transparent, light-blue PointsMaterial
    const rainMaterial = new THREE.PointsMaterial({
      color: 0x9ac8eb,
      size: 0.65,
      transparent: true,
      opacity: 0.75,
      depthWrite: false, // Prevents z-fighting and improves particle blending
      blending: THREE.AdditiveBlending
    });

    const rainParticles = new THREE.Points(rainGeometry, rainMaterial);
    scene.add(rainParticles);

    // -------------------------------------------------------------
    // 3. Animation & Reset Loop
    // -------------------------------------------------------------
    const posAttribute = rainGeometry.attributes.position;

    function animate() {
      requestAnimationFrame(animate);

      const posArray = posAttribute.array;

      for (let i = 0; i < RAIN_COUNT; i++) {
        const i3 = i * 3;

        // Apply downward velocity to Y coordinate
        posArray[i3 + 1] -= velocities[i];

        // Slight wind sway along X axis
        posArray[i3] -= 0.15;

        // Position-reset logic: if raindrop reaches the floor threshold, reset to top
        if (posArray[i3 + 1] < BOUNDS.yMin) {
          posArray[i3 + 1] = BOUNDS.yMax;
          // Re-randomize horizontal coordinate to prevent visible repeating patterns
          posArray[i3] = (Math.random() - 0.5) * BOUNDS.x * 2;
          posArray[i3 + 2] = (Math.random() - 0.5) * BOUNDS.z * 2;
        }

        // Wrap around horizontally if blown too far by the wind
        if (posArray[i3] < -BOUNDS.x) {
          posArray[i3] = BOUNDS.x;
        }
      }

      // Signal Three.js that the position buffer was modified
      posAttribute.needsUpdate = true;

      renderer.render(scene, camera);
    }

    animate();

    // -------------------------------------------------------------
    // 4. Responsive Resize Listener
    // -------------------------------------------------------------
    window.addEventListener('resize', () => {
      const width = window.innerWidth;
      const height = window.innerHeight;

      camera.aspect = width / height;
      camera.updateProjectionMatrix();

      renderer.setSize(width, height);
      renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
    });
  </script>
</body>
</html>
