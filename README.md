# OpenMinetopia Resourcepack
In deze repository zetten we de DusDavidGames Minetopia resourcepack om naar de nieuwste Minecraft-versie. Hierdoor is Optifine niet meer nodig en wordt er gebruikgemaakt van modernere technologieën, zoals **item models** en **custom equipment layers**.

## 📦 Hoe gebruik je deze resourcepack?
1. Controleer in de map `/assets/minecraft/items` welk item je wilt aanpassen of toevoegen.

### ✅ Voorbeelden:

**Kleding:**
```mcfunction
/give @p minecraft:diamond_chestplate[item_model="minecraft:armor/superwoman/chestplate",equippable={slot:"chest",asset_id:"minecraft:superwoman"}] 1
```

**Items:**
```mcfunction
/give @p minecraft:paper[item_model="minecraft:custom/wapens/wapens/awp/awp_forged"] 1
```

## 🛡️ Hoe werkt custom armor?
Deze resourcepack maakt gebruik van de **equipment layers** geïntroduceerd in **Minecraft 1.21.4** en is **niet compatibel** met oudere versies.

### 🧰 Nieuwe custom armor maken:

#### 1. Armor-textures toevoegen
- **`layer_1`** plaats je in:
  ```
  assets/minecraft/textures/entity/equipment/humanoid
  ```

- **`layer_2`** plaats je in:
  ```
  assets/minecraft/textures/entity/equipment/humanoid_leggings
  ```

#### 2. Equipment-layer configureren
Maak een nieuw `.json`-bestand aan in `assets/minecraft/equipment` met de volgende inhoud:

```json
{
  "layers": {
    "humanoid": [{
      "texture": "minecraft:<layer_1_naam>"
    }],
    "humanoid_leggings": [{
      "texture": "minecraft:<layer_2_naam>"
    }]
  }
}
```

✍️ **Voorbeeld:** `superwoman.json`

```json
{
  "layers": {
    "humanoid": [{
      "texture": "minecraft:superwoman_layer1"
    }],
    "humanoid_leggings": [{
      "texture": "minecraft:superwoman_layer2"
    }]
  }
}
```

#### 3. Icon-textures toevoegen
Maak icon-textures (PNG-bestanden) voor de helmet, chestplate, leggings en boots en plaats deze in:
```
assets/minecraft/textures/item/armor/<armor_naam>
```

✍️ **Bijvoorbeeld:**
```
assets/minecraft/textures/item/armor/superwoman/boots.png
```

#### 4. Icon-models maken
Maak de corresponderende `.json`-bestanden voor elk armorstuk in:
```
assets/minecraft/models/item/armor/<armor_naam>
```

✍️ **Voorbeeld:** `boots.json`

```json
{
  "parent": "minecraft:item/generated",
  "textures": {
    "layer0": "minecraft:item/armor/superwoman/boots"
  }
}
```

#### 5. Armor-items registreren
Maak voor elk armorstuk een itemmodel in:
```
assets/minecraft/items/armor/<armor_naam>
```

✍️ **Voorbeeld:** `boots.json`

```json
{
  "model": {
    "type": "minecraft:model",
    "model": "minecraft:item/armor/superwoman/boots"
  }
}
```

### 📋 Overzicht van vereiste bestanden:

| Bestandstype                     | Bestandslocatie                                            |
|----------------------------------|------------------------------------------------------------|
| Armor-textuur (`layer_1`, `layer_2`) | `assets/minecraft/textures/entity/equipment/humanoid`       |
| Equipment-layer JSON             | `assets/minecraft/equipment/<armor_naam>.json`              |
| Icon-texturen                    | `assets/minecraft/textures/item/armor/<armor_naam>`         |
| Icon-models                      | `assets/minecraft/models/item/armor/<armor_naam>`           |
| Item-models                      | `assets/minecraft/items/armor/<armor_naam>`                 |

Nu is je custom armor volledig geïntegreerd in de resourcepack! 🎉
