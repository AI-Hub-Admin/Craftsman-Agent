---
name: "shoes-designer"
description: "Agentic AI Shoes Designer generates customized shoes designs for manufacturing on demand (MOD), including Custom Print and Design Shoes, Sneakers, Running Shoes, Basketball Shoes, High Heels, Boots, Loafers, Sandals, Flats and more. "
env:
  DEEPNLP_ONEKEY_ROUTER_ACCESS:
    required: true
    description: OneKey Gateway Registered API and Usage access key
dependencies:
  node: []
  python: []
---

# AI Shoes Designer Skills from Craftsman Agent

Agentic AI Shoes Designer generates customized shoes designs for manufacturing on demand (MOD), including Custom Print and Design Shoes, Sneakers, Running Shoes, Basketball Shoes, High Heels, Boots, Loafers, Sandals, Flats and more.

The designer can use natural-language prompts, structured shoes parameters, and reference images to generate customized designs with materials, fits, silhouettes, dimensions, closures, decorations, prints, text, logos, and other design details.

After the design, you can also use the Craftsman Agent Manufacturing Platform to find suppliers of Craftsman of all kinds.

https://craftsman-agent.aiagenta2z.com/app/shoes-designer

The typical Clothing designer workflow such as T-Shirt POD include:

```commandline
[Text/Image Prompt of your Clothing Type, Texture, ]
        ->
[Define Customized Text or Logo Printing, Dimensions]
        ->
[Generate 3D Interactive Viewer] or [Generate final 3D Models.g. ]        
        ->
[Generate Preview Images From Multiple Views]
        ->
[Manufacturing on Demand Send Designs to Factory]
```

| API                          | Description                                                                                   |
|------------------------------|-----------------------------------------------------------------------------------------------|
| shoes_generator_design_draft | Generate Design Draft of your preferred Shoes type,Design Shoes, Sneakers, Running Shoes, Basketball Shoes, High Heels, Boots, Loafers, Sandals, Flats  , Change color on each parts of the shoes |


### OneKey Agent Gateway

The Bag Designer APIs are registered under:
unique_id: craftsman-agent/craftsman-agent
Gateway endpoint:
```commandline
https://agent.deepnlp.org/agent_router

```
Set the registered OneKey Gateway access key:

```
export DEEPNLP_ONEKEY_ROUTER_ACCESS=your_access_key
```

| Section                                 | Description                                               |
|-----------------------------------------|-----------------------------------------------------------|
| Craftsman Shoes Designer App Online     | https://craftsman-agent.aiagenta2z.com/app/shoes-designer |
| Craftsman Website                       | https://craftsman-agent.aiagenta2z.com                    |
| Craftsman App                           | https://craftsman-agent.aiagenta2z.com/app                |
| Craftsman Gallery                       | https://craftsman-agent.aiagenta2z.com/gallery            |
| Craftsman Workspace                     | https://craftsman-agent.aiagenta2z.com/workspace          |
| Craftsman Marketplace                   | https://craftsman-agent.aiagenta2z.com/marketplace        |
| Craftsman Manufacturing on Demand Store | https://craftsman-agent.aiagenta2z.com/store              |


## Quick Start
Set the registered OneKey Gateway access key `DEEPNLP_ONEKEY_ROUTER_ACCESS` from AI Agent Marketplace at the [Website](https://www.deepnlp.org/workspace/keys).

```bash
export DEEPNLP_ONEKEY_ROUTER_ACCESS=your_access_key
```

### Prompt Examples:

For each template_id and related prompt

* **sneakers**: Design sporty mesh sneakers with a rubber sole. The color of the stripe is black.
* **running-shoes**: Create knit running shoes with a cushioned sole and laces.
* **basketball-shoes**: Design high-top leather basketball shoes with a grip sole.
* **high-heels**: Suede high heels featuring a stiletto heel and pointed toe.
* **boots**: Design leather ankle boots with a block heel.
* **loafers**: Create flat suede loafers decorated with a tassel.
* **sandals**: Strappy leather sandals with a buckle closure.
* **flats**: Design solid canvas flats with a round toe.
* **slippers**: Open-toe fleece slippers with a soft sole.
* **childrens-shoes**: Design canvas slip-on children's shoes with velcro closure.


# 1. API: Shoes Designer Design Draft

### 1.1 REST API Requests Usage
```
shoes_generator_design_draft
```

Generate a shoes design draft with an interactive 3D model and multi-view images from:

Generate a shoes design draft with an interactive 3D model and multi-view images from:
* User text prompts
* Reference images
* Structured shoes parameters
* Shoes template IDs
* Customized print, text, logo, and decoration requirements

The resulting design draft can contain an online interactive 3D model viewer for future modification.

#### Requests Input Parameter


| Parameter           | Description                                                                                                                                                                   |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `prompt`            | Text description of the desired shoes style, material, fit, dimensions, decoration, printing, personalization, or manufacturing intent                                        |
| `images`            | Array of source image URLs used as visual references                                                                                                                          |
| `template_id`       | Shoes template ID such as `sneakers`, `running-shoes`, `basketball-shoes`, `high-heels`, `boots`, `loafers`, `sandals`, `flats`, `slippers`, or `childrens-shoes`               |
| `options`           | Structured customization parameters defined by the selected shoes template                                                                                                    |
| `provider_model_id` | Shoes design provider/model identifier; `default` is supported                                                                                                              |
| `session_name`      | Name of the generated workspace session                                                                                                                                       |
| `tag_list`          | Optional tags associated with the generation                                                                                                                                  |
| `mode`              | Generation mode: `basic`, `standard`, `advanced`, or `demo`                                                                                                                   |

#### Input Parameter Options

**template_id**: The template reference model to generate 

#### Supported Jewelry Category Template IDs

Supported `template_id` include

| Template ID         | Shoes Type        |
| ------------------- | ----------------- |
| `sneakers`          | Sneakers          |
| `running-shoes`     | Running Shoes     |
| `basketball-shoes`  | Basketball Shoes  |
| `high-heels`        | High Heels        |
| `boots`             | Boots             |
| `loafers`           | Loafers           |
| `sandals`           | Sandals           |
| `flats`             | Flats             |
| `slippers`          | Slippers          |
| `childrens-shoes`   | Children's Shoes  |


**Always use the exact template ID when constructing a request.**

**mode**: The mode as complexity of design for each generation task


| ID         | Description                                                                                                  |
| ---------- | ------------------------------------------------------------------------------------------------------------ |
| `basic`    | Basic complexity for design                                                                                  |
| `standard` | Standard complexity for design                                                                               |
| `advanced` | Advanced complexity for design                                                                               |
| `demo`     | Demo mode for predefined/debug API results; use `basic`, `standard`, or `advanced` for production generation |

#### Requests Input Example
```commandline
export DEEPNLP_ONEKEY_ROUTER_ACCESS=your_access_key

curl -X POST "https://agent.deepnlp.org/agent_router" \
  -H "Content-Type: application/json" \
  -H "X-OneKey: $DEEPNLP_ONEKEY_ROUTER_ACCESS" \
  -d '{
      "prompt": "Design sporty mesh sneakers with a rubber sole. The color of the stripe is black.",
      "images": [],
      "template_id": "sneakers",
      "provider_model_id": "default",
      "options": {
        "gender": "unisex",
        "material": "mesh",
        "asset_size": "standard",
        "size_system": "us",
        "shoe_size": "medium",
        "shoe_width": "standard",
        "sole_type": "rubber",
        "closure": "lace",
        "style": "sporty",
        "decoration": "none"
      },
      "session_name": "Sporty Mesh Sneakers",
      "tag_list": "sneakers,sporty,pod",
      "mode": "demo"
    }'
```

This example use the 'demo' mode for debug purpose, for real example, please use 'basic' instead.

#### Output Keys Definition

| Key                    | Description                                                    |
| ---------------------- | -------------------------------------------------------------- |
| `success`              | Whether the design draft generation succeeded                  |
| `share_url`            | URL of the workspace containing the generated design           |
| `blueprint`            | Generated clothing design blueprint data, when available       |
| `reference_images`     | Generated reference or multi-view image URLs                   |
| `final_image_url`      | URL of the generated multi-view design sheet                   |
| `overall_image`        | Overall generated design image information, when available     |
| `options`              | Structured clothing options generated or applied to the design |
| `prompt`               | Prompt used for the generation                                 |
| `session_id`           | Workspace/session identifier                                   |
| `title`                | Generated session title                                        |
| `workspace_session_id` | Workspace session identifier                                   |
| `tag_list`             | Tags associated with the generation                            |


#### Output Example

```json
{
  "success": true,
  "blueprint": {},
  "reference_images": [],
  "final_image_url": "",
  "overall_image": {},
  "session_id": "31d57eb9-9a37-4808-9c5b-1bfbb2abf5fb",
  "title": "T-Shirt Designer",
  "workspace_session_id": "",
  "tag_list": "t-shirt,graphic,pod",
  "options": {
    "gender": "unisex",
    "sub_category": "graphic",
    "material": "cotton",
    "asset_size": "m",
    "fit": "regular",
    "neckline": "crew",
    "sleeve": "short",
    "length": "hip",
    "hem_style": "straight"
  },
  "prompt": "Design a white cotton graphic T-shirt with a regular fit.",
  "share_url": "https://craftsman-agent.aiagenta2z.com/app/sessions/share/31d57eb9-9a37-4808-9c5b-1bfbb2abf5fb?pwd=de06"
}
```

**Note**:
`share_url`: After the Jewelry Design generation task finished, a `share_url` value contains URL of the canvas workspace will be returned.
This is the website to view the progress of the generation and the multiview sheets, the front view, side view, backview.
Please notify user the `share_url` link to view the Jewelry Design generation task status and results online!


### 1.2 CLI Usage

```shell
npx onekey agent craftsman-agent/craftsman-agent shoes_generator_design_draft '{"prompt":"Design sporty mesh sneakers with a rubber sole. The color of the stripe is black.","images":[],"template_id":"sneakers","provider_model_id":"default","options":{"gender":"unisex","material":"mesh","asset_size":"standard","size_system":"us","shoe_size":"medium","shoe_width":"standard","sole_type":"rubber","closure":"lace","style":"sporty","decoration":"none"},"session_name":"Sporty Mesh Sneakers","tag_list":"sneakers,sporty,pod","mode":"demo"}'
```

**Note**:
demo mode will return demo results for debug purpose, when production, change to 'basic' or other modes.

#### 1.3 Detailed Bag Designer Options


Below are all template IDs and their full options configurations (`option_parameters`) used by the Shoes Designer API.

### 1.3.1 Sneakers (`sneakers`)
- **Template ID:** sneakers
- **Options:**
  - `gender`: Male (`male`), Female (`female`), Unisex (`unisex`)
  - `material`: Mesh (`mesh`), Knit (`knit`), Leather (`leather`), Synthetic Leather (`synthetic_leather`), Suede (`suede`), Canvas (`canvas`), Textile (`textile`), Recycled Material (`recycled_material`)
  - `asset_size`: Standard Shoe (`standard`), High Top (`high_top`), Low Top (`low_top`)
  - `size_system`: US (`us`), UK (`uk`), EU (`eu`), CM (`cm`)
  - `shoe_size`: US 4–6 (`small`), US 6.5–9 (`medium`), US 9.5–12 (`large`), US 12.5–16 (`xlarge`)
  - `shoe_width`: Narrow (`narrow`), Standard (`standard`), Wide (`wide`), Extra Wide (`extra_wide`)
  - `sole_type`: Rubber (`rubber`), EVA Foam (`eva`), Phylon (`phylon`), Air Cushion (`air_cushion`), Platform (`platform`)
  - `closure`: Lace-Up (`lace`), Slip-On (`slip_on`), Velcro (`velcro`), Elastic (`elastic`)
  - `style`: Minimal (`minimal`), Sporty (`sporty`), Streetwear (`streetwear`), Retro (`retro`), Futuristic (`futuristic`), Luxury (`luxury`)
  - `decoration`: Logo (`logo`), Embroidery (`embroidery`), Color Blocking (`color_blocking`), Reflective Details (`reflective`), None (`none`)

### 1.3.2 Running Shoes (`running-shoes`)
- **Template ID:** running-shoes
- **Options:**
  - `gender`: Male (`male`), Female (`female`), Unisex (`unisex`)
  - `material`: Engineered Mesh (`engineered_mesh`), Knit (`knit`), Synthetic (`synthetic`), Textile (`textile`), Recycled Mesh (`recycled_mesh`)
  - `asset_size`: Road Running (`road`), Trail Running (`trail`), Racing (`racing`), Daily Trainer (`daily`)
  - `size_system`: US (`us`), UK (`uk`), EU (`eu`), CM (`cm`)
  - `shoe_size`: US 4–6 (`small`), US 6.5–9 (`medium`), US 9.5–12 (`large`), US 12.5–16 (`xlarge`)
  - `shoe_width`: Narrow (`narrow`), Standard (`standard`), Wide (`wide`), Extra Wide (`extra_wide`)
  - `cushioning`: Minimal (`minimal`), Moderate (`moderate`), Maximum (`maximum`)
  - `support`: Neutral (`neutral`), Stability (`stability`), Motion Control (`motion_control`)
  - `sole_type`: EVA (`eva`), PEBA Foam (`peba`), Carbon Plate (`carbon_plate`), Rubber (`rubber`), Trail Lugged (`lugged`)
  - `drop`: 0 mm (`zero`), 4–6 mm (`low`), 7–9 mm (`medium`), 10–12 mm (`high`)
  - `purpose`: Daily Training (`daily_training`), Long Distance (`long_distance`), Racing (`racing`), Trail (`trail`), Walking (`walking`)

### 1.3.3 Basketball Shoes (`basketball-shoes`)
- **Template ID:** basketball-shoes
- **Options:**
  - `gender`: Male (`male`), Female (`female`), Unisex (`unisex`)
  - `material`: Mesh (`mesh`), Synthetic (`synthetic`), Leather (`leather`), Knit (`knit`), Engineered Textile (`engineered_textile`)
  - `asset_size`: Low Top (`low`), Mid Top (`mid`), High Top (`high`)
  - `size_system`: US (`us`), UK (`uk`), EU (`eu`), CM (`cm`)
  - `shoe_size`: US 4–6 (`small`), US 6.5–9 (`medium`), US 9.5–12 (`large`), US 12.5–16 (`xlarge`)
  - `shoe_width`: Narrow (`narrow`), Standard (`standard`), Wide (`wide`), Extra Wide (`extra_wide`)
  - `ankle_support`: Low (`low`), Medium (`medium`), High (`high`)
  - `traction`: Indoor Court (`indoor`), Outdoor Court (`outdoor`), All Court (`all_court`)
  - `cushioning`: Responsive (`responsive`), Balanced (`balanced`), Maximum (`maximum`)
  - `sole_type`: Rubber (`rubber`), EVA (`eva`), Foam (`foam`), Air Cushion (`air`)
  - `style`: Performance (`performance`), Retro (`retro`), Streetwear (`streetwear`), Luxury (`luxury`)

### 1.3.4 High Heels (`high-heels`)
- **Template ID:** high-heels
- **Options:**
  - `gender`: Female (`female`), Unisex (`unisex`)
  - `material`: Leather (`leather`), Suede (`suede`), Patent Leather (`patent_leather`), Satin (`satin`), Velvet (`velvet`), Mesh (`mesh`), Synthetic (`synthetic`)
  - `asset_size`: Pump (`pump`), Slingback (`slingback`), Stiletto (`stiletto`), Platform (`platform`), Peep Toe (`peep_toe`)
  - `size_system`: US (`us`), UK (`uk`), EU (`eu`), CM (`cm`)
  - `shoe_size`: US 4–6 (`small`), US 6.5–9 (`medium`), US 9.5–12 (`large`), US 12.5–14 (`xlarge`)
  - `shoe_width`: Narrow (`narrow`), Standard (`standard`), Wide (`wide`)
  - `heel_height`: Kitten 1–2 in (`kitten`), Low 2–3 in (`low`), Mid 3–4 in (`mid`), High 4–5 in (`high`), Extreme 5+ in (`extreme`)
  - `heel_type`: Stiletto (`stiletto`), Block (`block`), Kitten (`kitten`), Cone (`cone`), Wedge (`wedge`)
  - `toe_shape`: Pointed (`pointed`), Round (`round`), Square (`square`), Almond (`almond`), Open Toe (`open`)
  - `decoration`: Crystal (`crystal`), Pearl (`pearl`), Bow (`bow`), Metal Hardware (`metal`), Embroidery (`embroidery`), None (`none`)

### 1.3.5 Boots (`boots`)
- **Template ID:** boots
- **Options:**
  - `gender`: Male (`male`), Female (`female`), Unisex (`unisex`)
  - `material`: Leather (`leather`), Suede (`suede`), Nubuck (`nubuck`), Rubber (`rubber`), Synthetic (`synthetic`), Canvas (`canvas`)
  - `asset_size`: Ankle Boot (`ankle`), Mid-Calf (`mid_calf`), Knee High (`knee_high`), Thigh High (`thigh_high`)
  - `size_system`: US (`us`), UK (`uk`), EU (`eu`), CM (`cm`)
  - `shoe_size`: US 4–6 (`small`), US 6.5–9 (`medium`), US 9.5–12 (`large`), US 12.5–16 (`xlarge`)
  - `shoe_width`: Narrow (`narrow`), Standard (`standard`), Wide (`wide`), Extra Wide (`extra_wide`)
  - `boot_style`: Chelsea (`chelsea`), Combat (`combat`), Hiking (`hiking`), Cowboy (`cowboy`), Work Boot (`work`), Riding (`riding`), Fashion (`fashion`)
  - `closure`: Lace-Up (`lace`), Zipper (`zipper`), Pull-On (`pull_on`), Buckle (`buckle`), Elastic (`elastic`)
  - `heel_type`: Flat (`flat`), Block (`block`), Stacked (`stacked`), Wedge (`wedge`)
  - `sole_type`: Rubber (`rubber`), Lugged (`lugged`), Platform (`platform`), Crepe (`crepe`)

### 1.3.6 Loafers (`loafers`)
- **Template ID:** loafers
- **Options:**
  - `gender`: Male (`male`), Female (`female`), Unisex (`unisex`)
  - `material`: Leather (`leather`), Suede (`suede`), Patent Leather (`patent_leather`), Synthetic (`synthetic`), Textile (`textile`)
  - `asset_size`: Classic (`classic`), Penny Loafer (`penny`), Tassel Loafer (`tassel`), Horsebit Loafer (`horsebit`), Platform (`platform`)
  - `size_system`: US (`us`), UK (`uk`), EU (`eu`), CM (`cm`)
  - `shoe_size`: US 4–6 (`small`), US 6.5–9 (`medium`), US 9.5–12 (`large`), US 12.5–16 (`xlarge`)
  - `shoe_width`: Narrow (`narrow`), Standard (`standard`), Wide (`wide`), Extra Wide (`extra_wide`)
  - `toe_shape`: Round (`round`), Almond (`almond`), Square (`square`), Pointed (`pointed`)
  - `sole_type`: Leather Sole (`leather`), Rubber (`rubber`), Lugged (`lugged`), Platform (`platform`)
  - `decoration`: Horsebit (`horsebit`), Tassel (`tassel`), Buckle (`buckle`), Chain (`chain`), Embroidery (`embroidery`), None (`none`)

### 1.3.7 Sandals (`sandals`)
- **Template ID:** sandals
- **Options:**
  - `gender`: Male (`male`), Female (`female`), Unisex (`unisex`)
  - `material`: Leather (`leather`), Suede (`suede`), Rubber (`rubber`), Textile (`textile`), Synthetic (`synthetic`), Cork (`cork`)
  - `asset_size`: Flat Sandal (`flat`), Sport Sandal (`sport`), Slide (`slide`), Gladiator (`gladiator`), Wedge (`wedge`), Heeled Sandal (`heeled`)
  - `size_system`: US (`us`), UK (`uk`), EU (`eu`), CM (`cm`)
  - `shoe_size`: US 4–6 (`small`), US 6.5–9 (`medium`), US 9.5–12 (`large`), US 12.5–16 (`xlarge`)
  - `shoe_width`: Narrow (`narrow`), Standard (`standard`), Wide (`wide`)
  - `strap_style`: Single Strap (`single`), Multi Strap (`multi`), Cross Strap (`cross`), Ankle Strap (`ankle`), Toe Loop (`toe_loop`)
  - `closure`: Buckle (`buckle`), Velcro (`velcro`), Slip-On (`slip_on`), Lace (`lace`)
  - `sole_type`: Flat (`flat`), Platform (`platform`), Wedge (`wedge`), Rubber (`rubber`), Cork (`cork`)
  - `style`: Casual (`casual`), Sport (`sport`), Beach (`beach`), Luxury (`luxury`), Bohemian (`bohemian`)

### 1.3.8 Flats (`flats`)
- **Template ID:** flats
- **Options:**
  - `gender`: Female (`female`), Unisex (`unisex`)
  - `material`: Leather (`leather`), Suede (`suede`), Canvas (`canvas`), Textile (`textile`), Synthetic (`synthetic`), Mesh (`mesh`)
  - `asset_size`: Ballet Flat (`ballet`), Mary Jane (`mary_jane`), Moccasin (`moccasin`), D'Orsay (`d_orsay`), Pointed Flat (`pointed_flat`)
  - `size_system`: US (`us`), UK (`uk`), EU (`eu`), CM (`cm`)
  - `shoe_size`: US 4–6 (`small`), US 6.5–9 (`medium`), US 9.5–12 (`large`), US 12.5–14 (`xlarge`)
  - `shoe_width`: Narrow (`narrow`), Standard (`standard`), Wide (`wide`)
  - `toe_shape`: Round (`round`), Pointed (`pointed`), Square (`square`), Almond (`almond`)
  - `closure`: Slip-On (`slip_on`), Buckle (`buckle`), Strap (`strap`), Lace-Up (`lace`)
  - `heel_height`: Flat 0–1 in (`flat`), Low 1–2 in (`low`), Mid 2–3 in (`mid`)
  - `decoration`: Bow (`bow`), Buckle (`buckle`), Crystal (`crystal`), Pearl (`pearl`), Embroidery (`embroidery`), None (`none`)

### 1.3.9 Slippers (`slippers`)
- **Template ID:** slippers
- **Options:**
  - `gender`: Male (`male`), Female (`female`), Unisex (`unisex`)
  - `material`: Cotton (`cotton`), Wool (`wool`), Fleece (`fleece`), Leather (`leather`), Suede (`suede`), Memory Foam (`memory_foam`), Rubber (`rubber`)
  - `asset_size`: Open Toe (`open_toe`), Closed Toe (`closed_toe`), Mule (`mule`), Bootie (`bootie`), Slide (`slide`)
  - `size_system`: US (`us`), UK (`uk`), EU (`eu`), CM (`cm`)
  - `shoe_size`: US 4–6 (`small`), US 6.5–9 (`medium`), US 9.5–12 (`large`), US 12.5–16 (`xlarge`)
  - `shoe_width`: Narrow (`narrow`), Standard (`standard`), Wide (`wide`)
  - `sole_type`: Rubber (`rubber`), EVA (`eva`), Memory Foam (`memory_foam`), Leather (`leather`)
  - `warmth`: Light (`light`), Medium (`medium`), Warm (`warm`), Extra Warm (`extra_warm`)
  - `style`: Home (`home`), Hotel (`hotel`), Luxury (`luxury`), Casual (`casual`), Novelty (`novelty`)

### 1.3.10 Children's Shoes (`childrens-shoes`)
- **Template ID:** childrens-shoes
- **Options:**
  - `gender`: Boy (`boy`), Girl (`girl`), Unisex (`unisex`)
  - `material`: Mesh (`mesh`), Canvas (`canvas`), Leather (`leather`), Synthetic (`synthetic`), Textile (`textile`), Rubber (`rubber`)
  - `asset_size`: Baby (`baby`), Toddler (`toddler`), Little Kids (`little_kids`), Big Kids (`big_kids`)
  - `size_system`: US Kids (`us`), UK Kids (`uk`), EU (`eu`), CM (`cm`)
  - `shoe_size`: US 0–4 (`baby`), US 4–10 (`toddler`), US 10.5–3 (`little_kids`), US 3.5–7 (`big_kids`)
  - `shoe_width`: Narrow (`narrow`), Standard (`standard`), Wide (`wide`)
  - `closure`: Velcro (`velcro`), Elastic (`elastic`), Lace-Up (`lace`), Slip-On (`slip_on`), Buckle (`buckle`)
  - `sole_type`: Rubber (`rubber`), EVA (`eva`), Flexible Sole (`flexible`), Non-Slip (`non_slip`)
  - `style`: School (`school`), Sport (`sport`), Casual (`casual`), Cute (`cute`), Character (`character`), Outdoor (`outdoor`)
  - `decoration`: Character Graphics (`character`), Light-Up (`light_up`), Embroidery (`embroidery`), Colorful Details (`colorful`), None (`none`)

