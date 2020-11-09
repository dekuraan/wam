# WAM
Wam Ain't Minecraft
## Purpose
Many great minecraft modpacks and minigames have been created, some of them so great as to be considered games on their own. See [Rebirth of the Night](https://github.com/Rebirth-of-the-Night/Rebirth-Of-The-Night) and [Blightfall](https://www.technicpack.net/modpack/blightfall.592618).
The only problem with these games is that they are troublesome to install and are made slow by the Java based Minecraft engine.
WAM aims to replace the sluggishness of Java with the speed of Rust, using dynamic libraries for modding.
## Aims
### Fast
(even on iGPU's)
Eventually want to be able to run on the browser
### Accessible
WAM should be coop first, making it easy to both host and join a game.
Development of a mod/pack should also be accessible.
### Community Developed
WAM should be structured to allow the community develop
## Mod System
Mods would be in the form of rust dynamic libraries (dylib).
"Templates" for mods can be created as mods, for instance you would import the block library and adjust a few things to create a new block.
Mods should be extremely easy to create. For instance armor should be a model rendered with a pallette for the material it is made with, so if one wanted to add a material to their mod they could easily just create a pallete for it. Further than this it could be a common pallete used for anything made with the material. Of course custom models could be created later, but it should be made easy for someone to just add a material and improve it later.
## Engine
With the introduction of bevy I am not sure which engine to develop WAM with. I really like the ergonomics and speed of legion. WGPU looks like the best rendering engine right now. Rapier seems like the obvious choice for physics.
## Voxel Stuff
### Engine
Each block is an ECS entity.
Blocks are indexed by position and store collision, visibility, mesh, textures in an asset store with handles as components.
This would allow easy queries over blocks for game logic.
### Renderer
Blocks not voxels.
I think blocks allow for much more detail and more creative models than voxel ones do.
While I think eventually multiple renderers would be cool I think a optimised block renderer would be first one.
This renderer should have at least:
- Shading
- Illumination
- Transparency
Should also be added:
- Ambient Occlusion
After the fast renderer is done, I also think a PBR and RTX renderer would be neat.
## MVP Goal
3 different WAM games developed through mods.
