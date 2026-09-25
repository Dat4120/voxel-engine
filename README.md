# Voxel Engine

<img width="1717" height="715" alt="Screenshot 2026-09-25 175336" src="https://github.com/user-attachments/assets/a2ba97b1-0e8d-48fb-9cf6-cf0a68754f4e" />
<br>
A Minecraft-style procedurally generated voxel world utilizing multi-threaded generation (JavaScript web workers), rendered with WebGL2. Includes mesh reconstruction with voxel placing/destroying. Chunks are generated around the player and are stored and eventually removed from memory.
<br><br>
Various visual effects like ambient occlusion and light spreading are applied to each chunk mesh and updated upon state change. Far chunks use level-of-detail rendering to speed up performance, where they increasingly become lower resolution the farther they are. Chunks also perform greedy meshing and face culling to minimize generated geometry. Every block face checks several adjacent neighbors to compute the lighting values, occlusion, and ability to be merged into a plane. 
<br><br>
This program makes large use of value noise and Fractal Brownian Motion to procedurally generate textures and infinite terrain without loading assets. Textures are packed into a WebGL2 texture array as opposed to traditional texture atlasses for easier repeat filtering (due to the greedy mesher generating faces that are bigger than 1x1 units).
