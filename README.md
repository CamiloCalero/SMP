<div align="center">
  <img src="https://github.com/user-attachments/assets/277f7de3-c29e-4c8d-8e2a-bba0ed00daeb"
       width="350">
</div>

## Editors

Here are the main tools to create resource packs for Minecraft. Click the image to head to the website.

### Blockbench

<a href="https://blockbench.net/">
  <img src="https://github.com/user-attachments/assets/64674a01-0643-4449-8603-df1f48e8615f"
       align="left"
       width="100"
       style="margin-right: 10px;">
</a>

Blockbench allows to create models, skins, textures, titles and animations.

This program counts with many plugins to make whatever you want really. But to create custom models for named mobs, you want to install CEM Template Loader. More on this in the next section.

<br clear="left">

### CreateTextures

<a href="https://createtextures.com/">
  <img src="https://github.com/user-attachments/assets/aceaf504-1786-442f-80c4-e36e38ef7135"
       align="left"
       width="100"
       style="margin-right: 10px;">
</a>

Use CreateTextures to quickly create skins or textures with Minecraft version templates.

Here you can just select the Minecraft version you're at and edit any item in the game using the texture editor.

<br clear="left">

## Creating a custom entity model

Here you can take any Minecraft entity and edit it's 3D model and texture.

Open Blockbench, go to **File** → **Plugins**, and search for CEM Template Loader, install it. 

Either on the new file window, or with **File** → **New**, scroll down to Loaders and you will find **CEM Template Loader**. Click it.  
Here you will find a bunch of different entities you can edit. Select one, load it and start editing.

## Resource pack structure

A resource pack must follow this structure:

```text
SMP/
├── pack.png
├── pack.mcmeta
└── assets/
    └── minecraft/
        ├── blockstates/
        ├── lang/
        │   └── en_us.json
        ├── optifine/
        │   ├── cem/
        │   │   └── entityName.jem
        │   └── random/
        │       └── entity/
        │           └── entityName/
        │               └── entityName.properties
        │               └── entityName.png
        └── textures/
            ├── block/
            │   └── blockName.png
            └── item/
                └── itemName.png
```

You can find the correct way to store a specific file by obtaining the game files themselves (more on this below) or if you are using CreateTextures, it will automatically place the textures where they belong, all you have to do is copy that exact structure in the SMP resource pack folder.

### Obtaining game files

Sometimes you might need to check how Minecraft names certain textures and where they are stored, or you might just want to change the name of something in the game, like for example Emerald → Pacochelín. Here's how you can do it:

### To find a texture for a specific item or entity

### To rename something

## Updating resource pack

Once you've finished modifying the resource pack, you need to create a GitHub release by uploading the pack in a zip file and provide a hash for said file. Here are the steps.

1. To create the zip file, remember to select all files inside the SMP folder (that is: assets, pack.mcmeta and pack.png), and zip them. **Do not zip the SMP folder**. When you open the zip, you want to see something like:
    
    ```text
    assets/
    pack.mcmeta
    pack.png
    ```
    
    and not
   
    ```text
    SMP/
    ├── assets/
    ├── pack.mcmeta
    └── pack.png
    ```
    
    This is important as the latter will cause Minecraft not to recognize it as a resource pack.

2. Place the zip in the same location as the SHA1_Calculator tool if it's not already there. Double click SHA1_Calculator.bat and it will automatically calculate and copy the hash to your clipboard. Close that window and paste that strange text in the SHA-1 field shown in the next section.

3. Go to the GitHub repository → **Releases** → **Draft a new release**. Here there are a few fields to fill.

    <img width="450" alt="image" src="https://github.com/user-attachments/assets/e808d59d-e823-4744-b5e5-7175d100fcf4" />

    In the tag dropdown menu shown above, select **Create new tag**. This tag must be something like `v1.0.0` or `v2.3.4`. Write it exactly like this with no spaces.

    The **Release title** should be `SMP vX.Y.Z`.

    For **Release notes** you can copy and paste the text below. Fill it in and paste the hash you generated using SHA1_Calculator.bat in the SHA-1 field.

    ```
    Describe any change or addition. 
    
    Minecraft version: 
    SHA-1: 
    ```

    Below that, there's **Release label**. Make sure it's set to **Latest**
