Create a polished, Voxel-style 3D side-scrolling web game contained entirely within a single HTML file using Three.js. The game must emulate a 'Minecraft' aesthetic with a 'Flappy Bird' mechanical twist, featuring combat and dynamic environmental hazards.

Visual Style & Atmosphere
Aesthetic: A bright, colorful Voxel world (constructed entirely of cubes). The look should be crisp and blocky.

Environment:

A procedurally generated, infinite scrolling ground composed of grass and dirt blocks.

A dynamic skybox with moving block-clouds.

Lighting: Use DirectionalLight with cast shadows to emphasize the 3D block geometry, plus HemisphereLight for ambient fill.

Assets: All assets (Dragon, Archers, Terrain, Projectiles) must be constructed programmatically using THREE.BoxGeometry groups. No external models.

The Dragon: A green/red blocky winged creature.

Archers: Humanoid block figures standing on the ground.

Projectiles: Fireballs (orange glowing cubes) and Arrows (thin rectangular prisms).

Gameplay Mechanics
Perspective: Side-scrolling 3D view (OrthographicCamera preferred for the true isometric/voxel look, or narrow FOV PerspectiveCamera). The camera follows the Dragon along the X-axis.

Core Loop:

Flight Physics: The Dragon is subject to strong gravity. The player applies an upward velocity impulse (Flap) to keep the dragon airborne.

Hazards: Instead of static pipes, massive stone pillars (3x3 block thickness) dynamically move:

Falling Stones: Slide down from the top of the screen.

Rising Stones: Shoot up from the floor like pistons.

Combat System:

Archers: Enemies spawn periodically on the ground. They track the Dragon's position and fire arrows at an upward angle.

Dragon Fire: The player can spit fireballs.

Ballistics: The fireballs must follow a heavy ballistic trajectory (projectile motion), starting with forward velocity but curving sharply downward to hit ground targets.

Collision:

Fire vs. Archer: Archer flashes red and disappears (dies) with a particle scatter effect.

Arrow/Stone vs. Dragon: The Dragon takes damage.

Health & Game Over:

Implement a Health Bar (3 Hearts or a percentage). Hitting a Stone or Arrow reduces HP. Hitting the ground is instant Game Over.

Score: Points are awarded for distance traveled and per archer destroyed.

Controls (Cross-Platform)
Desktop:

Spacebar / Left Click: Flap wings (Jump).

Right Click / 'F' Key: Spit Fireball.

Mobile/Touch:

Tap Left Side of Screen: Flap wings.

Tap Right Side of Screen: Spit Fireball.

Technical Constraints
Single File: All HTML, CSS, and JavaScript (including Three.js via CDN) must be in one index.html file.

Performance:

Use InstancedMesh for the ground blocks and background elements to maintain high FPS.

Use object pooling for projectiles (arrows/fireballs) and particles.

Responsiveness: The canvas must handle window resizing gracefully, maintaining the view frustum so the game remains playable on all aspect ratios.

Code Structure: Ensure the code is modular (e.g., class Dragon, class World, class Game) for readability.