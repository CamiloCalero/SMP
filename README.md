<div align="center">
  <img src="https://github.com/user-attachments/assets/277f7de3-c29e-4c8d-8e2a-bba0ed00daeb"
       width="350">
</div>

## Resource pack structure

First of all, a resource pack is just a set of files —textures, fonts, sounds, etc.— that replace their corresponding game files. It must always follow this structure:

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
        │               ├── entityName.properties
        │               └── entityName.png
        └── textures/
            ├── block/
            │   └── blockName.png
            └── item/
                └── itemName.png
```

You can find the correct way to store a specific file (for example a chest texture or the Wither spawn sound) by obtaining the game files themselves (more on this below) or if you are using CreateTextures (for textures only duh), it will automatically place the files where they belong, all you have to do is copy that exact structure in the SMP resource pack folder.

If you want, you can download the SMP folder from this repository. It already has the necessary files for Minecraft to recognize this as a resource pack, these files are: `pack.mcmeta`, `pack.png` and the `assets` folder.

### Obtaining game files

Sometimes you might need to check how Minecraft names certain textures and where they are stored, or you might just want to change the name of something in the game, like for example Emerald → Pacochelín. Here's how you can do it:

1. Locate your Minecraft `.jar` file.
   
    Open your launcher folder. For example, if you use Modrinth, the launcher is located at `C:\Users\user\AppData\Roaming\ModrinthApp`. You can also use **Windows + R** and type `%appdata%` and look for the `ModrinthApp` folder.
    Go to `meta/versions/yourVersion/yourVersion.jar` and extract it into some folder. For this whole tutorial we'll call it MC_Resources, as in original resources.

3. What you can see in the extracted folder is a bunch of game assets. Here are all the files you need and the correct folder paths where Minecraft will look. Should you make any changes to an item, block or entity, they have to be placed in the exact same path. Here's a couple examples.

### To find and modify a texture for a specific item or entity

If for example you go to `MC_Resources/assets/minecraft/textures/entity/warden/`, you are actually seeing the in-game textures for the Warden and his stuff. You can copy these to make your own textures, and later, your own models.

#### 😊 Happy Warden
   
Here's a little experiment you can do. Find the Warden texture file `warden.png`, open it an edit it in Paint. Draw a big smile on the guy.

You can now save that edited texture in its corresponding folder. **Remember to keep the original structure inside your texture pack** `yourTexturePack/assets/minecraft/textures/entity/warden/warden.png`. As of now, Minecraft will be able to recognize and use this resource pack folder. You can hop in the game, enter **Resource Packs** and activate your Happy Warden. This works and it's great for quick testing, but ideally you should zip the resource pack when you're ready to share.

To do that, select all three files in the root directory of the texture pack. Always remember these are: `pack.mcmeta`, `pack.png` and the `assets` folder. Now zip them, and put whatever name you want to the ZIP, maybe `HappyWarden.zip`. This is now the finished resource pack for your Happy Warden. You can send it to other people, and it will immediately work.

> Sometimes you might want to edit a block like a chest but doesn't appear anywhere. That's because a chest is not a block but an entity because Minecraft is weird. Some blocks that are not complete blocks are entities and some are not and it's a mess. You really have to look around sometimes.

### To rename something

First, you should check what language Minecraft is set to. Even if it's just English, there's US English, Canadian English, Pirate English, so make sure which one it is.  

After that, you can head to your extracted JAR folder `MC_Resources/assets/minecraft/lang/en_us.json`, which is the file where all text in Minecraft resides if it's using US English. For example, you want to change the Wandering Trader's name to Peruvian. Open it in a text editor, use **Ctrl + F** to quickly look for `wandering` and once you find the line `"entity.minecraft.wandering_trader": "Wandering Trader",`, you can set this to `"entity.minecraft.wandering_trader": "Peruvian",`. This will make the mob itself have that name in the game. You can do this with mobs, items (Pacochelín), GUI elements, titles, etc.  

When creating a resource pack, make sure everyone in the server will be able to see the change. If everyone is using English, but some use US English and some CA English, then you have to edit both `en_us.json` and `en_ca.json`. Internally the structure isn't the same for different languages, so remember to use **Ctrl + F**.

## Creating a custom entity model

Now that you know how resource packs work, you can start with custom models. Here are the main tools to create resource packs for Minecraft. Click the image to head to the website.

### Blockbench

<a href="https://blockbench.net/">
  <img src="https://github.com/user-attachments/assets/64674a01-0643-4449-8603-df1f48e8615f"
       align="left"
       width="100"
       style="margin-right: 10px;">
</a>

Blockbench allows to create models, skins, textures, titles and animations.

This program counts with many plugins to make whatever you want really. But to create custom models for mobs or even specific mobs with a nametag, you want to install CEM Template Loader. More on this in a while.

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

Also, totems! You can have your totems look like a mini-you, a 2D or 3D you. Click **Start Creating** → **Create Custom Totem**. Remember to check whether your skin is classic or slim. ✅

<br clear="left">

Now, onto Blockbench. Here you can take any Minecraft entity and edit its 3D model and texture.

Open Blockbench, go to **File** → **Plugins**, and search for CEM Template Loader, install it. 

Either on the new file window, or with **File** → **New**, scroll down to Loaders and you will find **CEM Template Loader**. Click it.  
Here you will find a bunch of different entities you can edit. Select one, load it and start editing.

Oh boy is this complicated...

🟨⬛🟨⬛🟨⬛🟨⬛🟨⬛🟨⬛🟨⬛

Section in the works.

🟨⬛🟨⬛🟨⬛🟨⬛🟨⬛🟨⬛🟨⬛

## Updating resource pack

Once you've finished modifying the resource pack, you need to create a GitHub release by uploading the pack in a `.zip` file and provide a hash for said file. Here are the steps.

1. To create the ZIP file, remember to select all files inside the SMP folder (that is: assets, pack.mcmeta and pack.png), and zip them. **Do not zip the SMP folder**. When you open the ZIP, you want to see something like:
    
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

2. Place the ZIP in the same location as the SHA1_Calculator tool if it's not already there. Double click SHA1_Calculator.bat and it will automatically calculate and copy the hash to your clipboard. Close that window and paste that strange text in the SHA-1 field shown in the next section.

3. Go to the GitHub repository → **Releases** → **Draft a new release**. Here there are a few fields to fill.

    <img width="450" alt="image" src="https://github.com/user-attachments/assets/e808d59d-e823-4744-b5e5-7175d100fcf4" />

    In the tag dropdown menu shown above, select **Create new tag**. This tag must be something like `v1.0.0` or `v2.3.4`. Write it exactly like this with no spaces.

    The **Release title** should be `SMP vX.Y.Z`.

    For **Release notes** you can copy and paste the text below. Fill it in and paste the hash you generated using SHA1_Calculator.bat in the **SHA-1** field.

    ```
    Describe any change or addition. 
    
    Minecraft version: 
    SHA-1: 
    ```

    Below that, there's **Release label**. Make sure it's set to **Latest**

    Finally, **Publish Release**. After that, you should reach out to Andrei so he can refresh the resource pack on the server. 
