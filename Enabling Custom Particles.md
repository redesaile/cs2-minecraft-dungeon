# Enabling Custom Particles
Below is a description of how to enable [custom particles](#adding-a-particle-file-type-to-the-asset-browser) and their [editor](#adding-a-particle-editor-to-the-toolbar).

## Adding a Particle File Type to the Asset Browser
1. Find `assettypes_common.txt` by path `..\Steam\steamapps\common\Counter-Strike Global Offensive\game\bin`
2. Open it and find this code:
    ```ini
		particle_asset = 
		{
			_class = "CResourceAssetTypeInfo"
			m_FriendlyName = "Particle System"
			m_Ext = "vpcf"
			m_IconLg = "game:tools/images/assettypes/particles_lg.png"
			m_IconSm = "game:tools/images/assettypes/particles_sm.png"
			m_CompilerIdentifier = "CompileParticle"
			m_bPrefersLivePreview = true
			m_bUnrecognizedReferencesAreErrors = true
			m_Blocks = 
			[
				{
					m_BlockID = "DATA"
					m_Encoding = "RESOURCE_ENCODING_KV3"
				},
			]
			m_HideForRetailMods = 
			[
				"csgo",
			]
		}
    ```
3. Add the characters of the one-line comment (`//`) to the left of `csgo,` to enable custom particles:
    ```ini
		particle_asset = 
		{
			_class = "CResourceAssetTypeInfo"
			m_FriendlyName = "Particle System"
			m_Ext = "vpcf"
			m_IconLg = "game:tools/images/assettypes/particles_lg.png"
			m_IconSm = "game:tools/images/assettypes/particles_sm.png"
			m_CompilerIdentifier = "CompileParticle"
			m_bPrefersLivePreview = true
			m_bUnrecognizedReferencesAreErrors = true
			m_Blocks = 
			[
				{
					m_BlockID = "DATA"
					m_Encoding = "RESOURCE_ENCODING_KV3"
				},
			]
			m_HideForRetailMods = 
			[
			//	"csgo",
			]
		}
    ```

## Adding a Particle Editor to the toolbar
1. Find `sdkenginetools.txt` by path `..\Steam\steamapps\common\Counter-Strike Global Offensive\game\bin`
2. Open it and find this code:
    ```ini
		{
			m_Name = "pet"
			m_FriendlyName = "Particle Editor"
			m_Library = "tools/pet.dll"
			m_ToolIcon = "game:tools/images/pet/appicon.ico"
			m_AssetTypes = 
			[
				"particle_asset",
			]
			m_ExcludeFromMods = 
			[
				"csgo",
			]			
		},
    ```
3. Add the characters of the one-line comment (`//`) to the left of `csgo,` to enable the Particle Editor:
    ```ini
		{
			m_Name = "pet"
			m_FriendlyName = "Particle Editor"
			m_Library = "tools/pet.dll"
			m_ToolIcon = "game:tools/images/pet/appicon.ico"
			m_AssetTypes = 
			[
				"particle_asset",
			]
			m_ExcludeFromMods = 
			[
			//	"csgo",
			]			
		},
    ```
