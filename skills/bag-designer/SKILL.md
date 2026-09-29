---
name: "bag-designer"
description: "Agentic AI Bag Designer generates customized Bags for print and manufacturing for all kinds, including Luxury Bags, Flap Bags, Top Handle Bags, Totes, Shoulder Bags, Canvas bag, Crossbody Bags, Clutches and more."
env:
  DEEPNLP_ONEKEY_ROUTER_ACCESS:
    required: true
    description: OneKey Gateway Registered API and Usage access key
dependencies:
  node: []
  python: []
---

# AI Bag Designer Skills from Craftsman Agent

Agentic AI Bag Designer generates customized Bags for print and manufacturing for all kinds, including Luxury Bags, Flap Bags, Top Handle Bags, Totes, Shoulder Bags, Canvas bag, Crossbody Bags, Clutches and more.

https://craftsman-agent.aiagenta2z.com/app/bag-designer

The typical bag designer workflow include:

```commandline
[Text/Image Prompt of your Preferred Bag Type, Texture]
        ->
[Define Customized Bags Text or Logo Printing]
        ->
[Bag Design 3D Generation Interactive Viewer of the Design] or [Bag Design 3D Models e.g. ]        
        ->
[Preview Images From Multiple Views]
        ->
[Manufacturing on Demand Send Designs to Factory]
```

| API                        | Description                                                                                         |
|----------------------------|-----------------------------------------------------------------------------------------------------|
| bag_generator_design_draft | Generate Design Draft of your preferred bag type, size dimensions, customization text or logo print |


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

| Section                                 | Description                                             |
|-----------------------------------------|---------------------------------------------------------|
| Craftsman Bag Designer App Online       | https://craftsman-agent.aiagenta2z.com/app/bag-designer |
| Craftsman Website                       | https://craftsman-agent.aiagenta2z.com                  |
| Craftsman App                           | https://craftsman-agent.aiagenta2z.com/app              |
| Craftsman Gallery                       | https://craftsman-agent.aiagenta2z.com/gallery          |
| Craftsman Workspace                     | https://craftsman-agent.aiagenta2z.com/workspace        |
| Craftsman Marketplace                   | https://craftsman-agent.aiagenta2z.com/marketplace      |
| Craftsman Manufacturing on Demand Store | https://craftsman-agent.aiagenta2z.com/store            |


## Quick Start
Set the registered OneKey Gateway access key `DEEPNLP_ONEKEY_ROUTER_ACCESS` from AI Agent Marketplace at the [Website](https://www.deepnlp.org/workspace/keys).

```bash
export DEEPNLP_ONEKEY_ROUTER_ACCESS=your_access_key
```

### Prompt Examples:
  Template ID: `flap-bag`
  Prompt: Design a quilted flap bag using lambskin leather with a diamond quilting pattern and gold hardware finish.

  Template ID: `top-handle-bag`
  Prompt: Create a structured top handle bag made of calfskin leather with a detachable shoulder strap.

  Template ID: `tote-bag`
  Prompt: Design a canvas tote bag as a souvenir for a conference hosted by "AI Agent A2Z". Print "AI Agent A2Z" on the bag using color `#51be95` with Craftsman Agent logos.

  Template ID: `shoulder-bag`
  Prompt: Create a suede shoulder bag featuring a chain strap and magnetic closure.

  Template ID: `crossbody-bag`
  Prompt: Design a nylon crossbody bag with an adjustable strap and a front zipper pocket.

  Template ID: `hobo-bag`
  Prompt: Create a highly slouchy hobo bag in cowhide leather with a curved bottom shape.

  Template ID: `bucket-bag`
  Prompt: Design a leather drawstring bucket bag with a round base.

  Template ID: `clutch-evening-bag`
  Prompt: Create an evening clutch made of satin with crystal decorations and a frame closure.

  Template ID: `mini-bag-pochette`
  Prompt: Design a mini patent leather pochette with a 100cm chain and three interior card slots.

  Template ID: `satchel-structured-bag`
  Prompt: Design a structured satchel in full-grain leather with a lock closure and a 13-inch laptop compartment.


# 1. API: Bag Designer Design Draft

### 1.1 REST API Requests Usage
```
bag_generator_design_draft
```
Generate a bag design draft with a 3D model and multi-view images from the user's text prompt, reference images, and structured bag parameters.

The design draft can contain an online interactive 3D model viewer for future modification.

#### Requests Input Parameter


| Parameter | Description |
|---|---|
| `prompt` | Text description of the desired bag design, style, material, dimensions, decoration, hardware, printing, or manufacturing intent |
| `images` | Array of source image URLs used as visual references |
| `template_id` | Bag template ID such as `flap-bag`, `top-handle-bag`, `tote-bag`, `shoulder-bag`, `crossbody-bag`, `hobo-bag`, `bucket-bag`, `clutch-evening-bag`, `mini-bag-pochette`, or `satchel-structured-bag` |
| `options` | Structured customization parameters defined by the selected bag template |
| `provider_model_id` | Bag design provider/model identifier; `default` is supported |
| `session_name` | Name of the generated workspace session |
| `tag_list` | Optional tags associated with the generation |
| `mode` | Generation mode: `basic`, `standard`, `advanced`, or `demo` |


#### Input Parameter Options

**template_id**: The template of the bag to generate

#### Supported Jewelry Category Template IDs

Supported `template_id` include


| Template ID | Bag Type |
|---|---|
| `flap-bag` | Flap Bag |
| `top-handle-bag` | Top Handle Bag |
| `tote-bag` | Tote Bag |
| `shoulder-bag` | Shoulder Bag |
| `crossbody-bag` | Crossbody Bag |
| `hobo-bag` | Hobo Bag |
| `bucket-bag` | Bucket Bag |
| `clutch-evening-bag` | Clutch / Evening Bag |
| `mini-bag-pochette` | Mini Bag / Pochette |
| `satchel-structured-bag` | Structured Satchel |


**mode**: The mode as complexity of design for each generation task

| mode     | Description                                                                                                           |
|----------|-----------------------------------------------------------------------------------------------------------------------|
| basic    | Basic Complexity for Design                                                                                           |
| standard | Standard Complexity for Design                                                                                        |
| advanced | Advanced Complexity for Design                                                                                        |
| demo     | Demo mode will only return predefined results for debug and APIs purposes, for production, please use other settings. |

#### Requests Input Example
```commandline
export DEEPNLP_ONEKEY_ROUTER_ACCESS=your_access_key

curl -X POST "https://agent.deepnlp.org/agent_router" \
  -H "Content-Type: application/json" \
  -H "X-OneKey: $DEEPNLP_ONEKEY_ROUTER_ACCESS" \
  -d '{
    "unique_id": "craftsman-agent/craftsman-agent",
    "api_id": "bag_generator_design_draft",
    "data": {
      "prompt": " Design a canvas shopping tote bag as souvenir for conference hosted by www.aiagenta2z.com. The print on the bag contains text 'AI Agent A2Z' using color #51be95 and logos of Craftsman Agent.",
      "images": [],
      "template_id": "tote-bag",
      "provider_model_id": "default",
      "options": {
        "sub_category": "shopping-tote",
        "material": "canvas"
      },
      "session_name": "Tote Bag Design for Conference",
      "tag_list": "",
      "mode": "demo"
    }
  }'

```

This example use the demo mode for debug purpose, for real example, please use 'basic' instead.

#### Output Keys Definition
| Key                  | Description                                                             |
|----------------------|-------------------------------------------------------------------------|
| success              | Whether the design draft generation succeeded                           |
| share_url            | The URL of workspace containing the canvas to view the design           |
| blueprint            | Jewelry design blueprint data, when available                               |
| reference_images     | Generated reference image URLs                                          |
| final_image_url      | URL of the generated multi-view design sheet                            |
| options              | The options AI designer generated to display on the base bag models |
| session_id           | Workspace/session identifier                                            |
| title                | Generated session title                                                 |
| workspace_session_id | Workspace session identifier                                            |
| tag_list             | Tags associated with the generation                                     |


#### Output Example
```commandline
{
  "success": true,
  "blueprint": {},
  "reference_images": [],
  "final_image_url": "",
  "overall_image": {},
  "session_id": "31d57eb9-9a37-4808-9c5b-1bfbb2abf5fb",
  "title": "Bag Designer",
  "workspace_session_id": "",
  "tag_list": "",
  "options": {
     "count": 15,
     "material": "aqua"
  },
  "prompt": "Crystl Beaded Bracelet Chain of 12 Aqua stones",
  "share_url": "https://craftsman-agent.aiagenta2z.com/app/sessions/share/31d57eb9-9a37-4808-9c5b-1bfbb2abf5fb?pwd=de06"
}
```


**Note**:
`share_url`: After the Jewelry Design generation task finished, a `share_url` value contains URL of the canvas workspace will be returned.
This is the website to view the progress of the generation and the multiview sheets, the front view, side view, backview.
Please notify user the `share_url` link to view the Jewelry Design generation task status and results online!


### 1.2 CLI Usage

```shell
npx onekey agent craftsman-agent/craftsman-agent bag_generator_design_draft '{"prompt":" Design a canvas shopping tote bag as souvenir for conference hosted by www.aiagenta2z.com. The print on the bag contains text 'AI Agent A2Z' using color #51be95 and logos of Craftsman Agent.","images":[],"template_id":"tote-bag","provider_model_id":"default","options":{"sub_category":"shopping-tote","material":"canvas"},"session_name":"Tote Bag Design for Conference","tag_list":"","mode":"demo"}'
```
**Note**:
demo mode will return demo results for debug purpose, when production, change to 'basic' or other modes.


#### 1.3 Detailed Bag Designer Options

The following sections are generated directly from the Bag Designer JSON configuration. **Use option IDs, not display names, when constructing `options`.** Scalar values such as dimensions are documented as defaults from the configuration.

## 1.3.1. Flap Bag

`template_id`: `flap-bag`


### Main Parameters


| Parameter | Supported IDs |
|---|---|
| `sub_category` | `classic-flap`, `quilted-flap`, `chain-flap`, `mini-flap`, `double-flap`, `envelope-flap`, `square-flap`, `rounded-flap` |
| `material` | `default`, `calfskin`, `lambskin`, `cowhide`, `full-grain`, `top-grain`, `nappa`, `patent`, `suede`, `vegan-leather`, `canvas`, `cotton`, `linen`, `denim`, `nylon`, `polyester`, `velvet`, `satin`, `jacquard`, `tweed` |
| `asset_size` | `default`, `mini`, `small`, `medium`, `large` |
| `flap_shape` | `straight`, `rounded`, `square`, `envelope`, `curved` |
| `flap_size` | `small`, `medium`, `large` |
| `quilting_pattern` | `none`, `diamond`, `chevron`, `horizontal`, `geometric` |
| `closure_type` | `turn-lock`, `magnetic`, `push-lock`, `clasp` |
| `hardware_finish` | `gold`, `silver`, `rose-gold`, `gunmetal`, `black`, `antique-brass`, `antique-silver`, `stainless-steel` |

### Other Parameters / Defaults


| Parameter | Default / Value |
|---|---|
| `size` | `Medium` |
| `width` | `28cm` |
| `height` | `20cm` |
| `depth` | `9cm` |
| `chain_length` | `120cm` |
| `strap_length` | `110cm` |
| `strap_width` | `2cm` |

### Asset Size Metadata

| Asset Size ID | Width | Height | Depth | Unit |
|---|---|---|---|---|
| `mini` | `18cm` | `12cm` | `6cm` | `cm` |
| `small` | `22cm` | `15cm` | `7cm` | `cm` |
| `medium` | `28cm` | `20cm` | `9cm` | `cm` |
| `large` | `34cm` | `24cm` | `11cm` | `cm` |

### Example `options`

```json
{
    "sub_category": "classic-flap",
    "material": "default",
    "asset_size": "default",
    "flap_shape": "straight",
    "flap_size": "small",
    "quilting_pattern": "none",
    "closure_type": "turn-lock",
    "hardware_finish": "gold"
}
```

## 1.3.2. Top Handle Bag

`template_id`: `top-handle-bag`

### Main Parameters


| Parameter | Supported IDs |
|---|---|
| `sub_category` | `structured-top-handle`, `lady-bag`, `box-bag`, `frame-bag`, `mini-top-handle`, `doctor-bag`, `trapezoid-bag` |
| `material` | `default`, `calfskin`, `lambskin`, `cowhide`, `full-grain`, `top-grain`, `nappa`, `patent`, `suede`, `vegan-leather`, `canvas`, `jacquard` |
| `asset_size` | `default`, `small`, `medium`, `large` |
| `handle_material` | `leather`, `metal`, `acrylic`, `wood`, `bamboo` |
| `detachable_shoulder_strap` | `yes`, `no` |
| `bag_structure` | `soft`, `semi-structured`, `structured`, `rigid` |
| `base_shape` | `rectangle`, `square`, `trapezoid`, `rounded` |
| `closure` | `zipper`, `turn-lock`, `push-lock`, `magnetic`, `frame` |
| `feet` | `none`, `four-feet`, `six-feet` |

### Other Parameters / Defaults


| Parameter | Default / Value |
|---|---|
| `size` | `Medium` |
| `width` | `28cm` |
| `height` | `23cm` |
| `depth` | `12cm` |
| `handle_drop` | `10cm` |
| `handle_thickness` | `2cm` |
| `interior_compartments` | `2` |

### Asset Size Metadata


| Asset Size ID | Width | Height | Depth | Unit |
|---|---|---|---|---|
| `small` | `22cm` | `18cm` | `10cm` | `cm` |
| `medium` | `28cm` | `23cm` | `12cm` | `cm` |
| `large` | `35cm` | `28cm` | `14cm` | `cm` |

### Example `options`

```json
{
    "sub_category": "structured-top-handle",
    "material": "default",
    "asset_size": "default",
    "handle_material": "leather",
    "detachable_shoulder_strap": "yes",
    "bag_structure": "soft",
    "base_shape": "rectangle",
    "closure": "zipper",
    "feet": "none"
}
```


## 1.3.3. Tote Bag

`template_id`: `tote-bag`


### Main Parameters


| Parameter | Supported IDs |
|---|---|
| `sub_category` | `luxury-tote`, `shopping-tote`, `structured-tote`, `open-tote`, `zip-tote`, `large-tote`, `mini-tote`, `book-tote` |
| `material` | `default`, `leather`, `canvas`, `cotton`, `linen`, `denim`, `nylon`, `polyester`, `velvet`, `satin`, `jacquard`, `tweed` |
| `asset_size` | `default`, `small`, `medium`, `large`, `xl` |
| `size` | `small`, `medium`, `large`, `xl` |
| `open_or_closed_top` | `open`, `closed` |
| `zipper` | `none`, `single`, `double` |
| `magnetic_closure` | `none`, `single`, `double` |
| `gusset` | `flat`, `small`, `medium`, `large` |
| `laptop_compartment` | `none`, `13-inch`, `14-inch`, `15-inch`, `16-inch` |
| `reinforced_bottom` | `yes`, `no` |

### Other Parameters / Defaults

| Parameter | Default / Value |
|---|---|
| `width` | `35cm` |
| `height` | `28cm` |
| `depth` | `14cm` |
| `handle_drop` | `25cm` |
| `handle_width` | `2.5cm` |
| `interior_pocket` | `2` |

### Asset Size Metadata


| Asset Size ID | Width | Height | Depth | Unit |
|---|---|---|---|---|
| `small` | `28cm` | `22cm` | `10cm` | `cm` |
| `medium` | `35cm` | `28cm` | `14cm` | `cm` |
| `large` | `42cm` | `32cm` | `17cm` | `cm` |
| `xl` | `50cm` | `38cm` | `20cm` | `cm` |

### Example `options`

```json
{
    "sub_category": "luxury-tote",
    "material": "default",
    "asset_size": "default",
    "size": "small",
    "open_or_closed_top": "open",
    "zipper": "none",
    "magnetic_closure": "none",
    "gusset": "flat",
    "laptop_compartment": "none",
    "reinforced_bottom": "yes"
}
```

## 1.3.4. Shoulder Bag

`template_id`: `shoulder-bag`


### Main Parameters


| Parameter | Supported IDs |
|---|---|
| `sub_category` | `classic-shoulder`, `chain-shoulder`, `hobo-shoulder`, `flap-shoulder`, `crescent-shoulder`, `east-west` |
| `material` | `default`, `calfskin`, `lambskin`, `cowhide`, `suede`, `vegan-leather`, `canvas`, `nylon`, `velvet` |
| `asset_size` | `default`, `small`, `medium`, `large` |
| `strap_type` | `single`, `double` |
| `detachable_strap` | `yes`, `no` |
| `strap_material` | `leather`, `chain`, `fabric`, `webbing`, `braided` |
| `closure` | `zipper`, `magnetic`, `flap`, `turn-lock` |
| `bag_shape` | `rectangle`, `square`, `crescent`, `rounded`, `east-west` |

### Other Parameters / Defaults

| Parameter | Default / Value |
|---|---|
| `size` | `Medium` |
| `width` | `28cm` |
| `height` | `20cm` |
| `depth` | `9cm` |
| `shoulder_strap_length` | `70cm` |
| `strap_width` | `3cm` |
| `chain_length` | `100cm` |

### Asset Size Metadata


| Asset Size ID | Width | Height | Depth | Unit |
|---|---|---|---|---|
| `small` | `22cm` | `16cm` | `7cm` | `cm` |
| `medium` | `28cm` | `20cm` | `9cm` | `cm` |
| `large` | `35cm` | `25cm` | `12cm` | `cm` |

### Example `options`

```json
{
    "sub_category": "classic-shoulder",
    "material": "default",
    "asset_size": "default",
    "strap_type": "single",
    "detachable_strap": "yes",
    "strap_material": "leather",
    "closure": "zipper",
    "bag_shape": "rectangle"
}
```

## 1.3.5. Crossbody Bag

`template_id`: `crossbody-bag`

### Main Parameters

| Parameter | Supported IDs |
|---|---|
| `sub_category` | `camera-bag`, `saddle-bag`, `flap-crossbody`, `box-crossbody`, `messenger-crossbody`, `small-crossbody`, `mini-crossbody` |
| `material` | `default`, `leather`, `vegan-leather`, `canvas`, `nylon`, `denim`, `fabric` |
| `asset_size` | `default`, `mini`, `small`, `medium` |
| `adjustable_strap` | `yes`, `no` |
| `flap` | `none`, `small`, `medium`, `large` |
| `zipper` | `none`, `single`, `double` |
| `magnetic_closure` | `yes`, `no` |
| `front_pocket` | `none`, `single`, `double` |
| `back_pocket` | `none`, `single` |

### Other Parameters / Defaults

| Parameter | Default / Value |
|---|---|
| `size` | `Medium` |
| `width` | `28cm` |
| `height` | `20cm` |
| `depth` | `9cm` |
| `crossbody_strap_length` | `120cm` |
| `strap_width` | `3cm` |
| `gusset_depth` | `7cm` |
| `interior_compartments` | `2` |

### Asset Size Metadata

| Asset Size ID | Width | Height | Depth | Unit |
|---|---|---|---|---|
| `mini` | `18cm` | `13cm` | `6cm` | `cm` |
| `small` | `22cm` | `16cm` | `7cm` | `cm` |
| `medium` | `28cm` | `20cm` | `9cm` | `cm` |

### Example `options`

```json
{
    "sub_category": "camera-bag",
    "material": "default",
    "asset_size": "default",
    "adjustable_strap": "yes",
    "flap": "none",
    "zipper": "none",
    "magnetic_closure": "yes",
    "front_pocket": "none",
    "back_pocket": "none"
}
```

## 1.3.6. Hobo Bag

`template_id`: `hobo-bag`

### Main Parameters


| Parameter | Supported IDs |
|---|---|
| `sub_category` | `classic-hobo`, `soft-hobo`, `crescent-hobo`, `mini-hobo`, `large-hobo`, `slouchy-hobo` |
| `material` | `default`, `lambskin`, `nappa`, `suede`, `cowhide`, `vegan-leather`, `canvas`, `velvet` |
| `asset_size` | `default`, `small`, `medium`, `large` |
| `curvature` | `low`, `medium`, `high`, `crescent` |
| `slouch_level` | `structured`, `semi-soft`, `soft`, `slouchy` |
| `handle_construction` | `fixed`, `detachable`, `integrated` |
| `opening` | `zipper`, `magnetic`, `open` |
| `zipper` | `none`, `top-zipper` |
| `bottom_shape` | `flat`, `rounded`, `oval` |

### Other Parameters / Defaults

| Parameter | Default / Value |
|---|---|
| `size` | `Medium` |
| `width` | `35cm` |
| `height` | `28cm` |
| `depth` | `13cm` |
| `shoulder_strap_length` | `65cm` |
| `strap_width` | `5cm` |
| `interior_pockets` | `2` |

### Asset Size Metadata


| Asset Size ID | Width | Height | Depth | Unit |
|---|---|---|---|---|
| `small` | `25cm` | `20cm` | `10cm` | `cm` |
| `medium` | `35cm` | `28cm` | `13cm` | `cm` |
| `large` | `42cm` | `34cm` | `16cm` | `cm` |

### Example `options`

```json
{
    "sub_category": "classic-hobo",
    "material": "default",
    "asset_size": "default",
    "curvature": "low",
    "slouch_level": "structured",
    "handle_construction": "fixed",
    "opening": "zipper",
    "zipper": "none",
    "bottom_shape": "flat"
}
```



## 1.3.7. Bucket Bag

`template_id`: `bucket-bag`

### Main Parameters


| Parameter | Supported IDs |
|---|---|
| `sub_category` | `classic-bucket`, `drawstring-bucket`, `structured-bucket`, `mini-bucket`, `large-bucket`, `chain-bucket` |
| `material` | `default`, `leather`, `suede`, `canvas`, `nylon`, `woven`, `vegan-leather` |
| `asset_size` | `default`, `mini`, `small`, `medium`, `large` |
| `crossbody_strap` | `none`, `fixed`, `adjustable`, `detachable` |
| `handle_type` | `leather`, `chain`, `fabric`, `rope` |
| `base_shape` | `round`, `oval`, `square`, `structured` |
| `closure` | `drawstring`, `magnetic`, `zipper`, `open` |
| `interior_pouch` | `none`, `single`, `zipper`, `detachable` |

### Other Parameters / Defaults


| Parameter | Default / Value |
|---|---|
| `size` | `Medium` |
| `diameter` | `25cm` |
| `width` | `25cm` |
| `height` | `30cm` |
| `depth` | `25cm` |
| `opening_size` | `20cm` |
| `drawstring_length` | `80cm` |
| `shoulder_strap_length` | `100cm` |

### Asset Size Metadata

| Asset Size ID | Width | Height | Depth | Unit |
|---|---|---|---|---|
| `mini` | `16cm` | `20cm` | `16cm` | `cm` |
| `small` | `20cm` | `25cm` | `20cm` | `cm` |
| `medium` | `25cm` | `30cm` | `25cm` | `cm` |
| `large` | `30cm` | `35cm` | `30cm` | `cm` |

### Example `options`

```json
{
    "sub_category": "classic-bucket",
    "material": "default",
    "asset_size": "default",
    "crossbody_strap": "none",
    "handle_type": "leather",
    "base_shape": "round",
    "closure": "drawstring",
    "interior_pouch": "none"
}
```



## 2.8. Clutch / Evening Bag

`template_id`: `clutch-evening-bag`


### Main Parameters


| Parameter | Supported IDs |
|---|---|
| `sub_category` | `envelope-clutch`, `box-clutch`, `frame-clutch`, `foldover-clutch`, `chain-clutch`, `minaudiere`, `evening-pouch` |
| `material` | `default`, `satin`, `velvet`, `patent-leather`, `leather`, `crystal`, `metal-mesh`, `beaded`, `sequin` |
| `asset_size` | `default`, `mini`, `small`, `standard`, `large` |
| `wrist_strap` | `none`, `short`, `long` |
| `handle` | `none`, `top-handle`, `chain`, `metal` |
| `closure` | `clasp`, `magnetic`, `frame`, `zipper` |
| `frame` | `none`, `metal`, `decorative` |
| `crystal_decoration` | `none`, `subtle`, `medium`, `heavy` |
| `pearl_decoration` | `none`, `subtle`, `medium`, `heavy` |
| `embellishment_density` | `minimal`, `medium`, `dense`, `fully-covered` |

### Other Parameters / Defaults


| Parameter | Default / Value |
|---|---|
| `width` | `25cm` |
| `height` | `15cm` |
| `depth` | `6cm` |
| `chain_length` | `110cm` |
| `interior_compartment` | `1` |

### Asset Size Metadata


| Asset Size ID | Width | Height | Depth | Unit |
|---|---|---|---|---|
| `mini` | `16cm` | `9cm` | `4cm` | `cm` |
| `small` | `20cm` | `12cm` | `5cm` | `cm` |
| `standard` | `25cm` | `15cm` | `6cm` | `cm` |
| `large` | `30cm` | `18cm` | `7cm` | `cm` |

### Example `options`

```json
{
    "sub_category": "envelope-clutch",
    "material": "default",
    "asset_size": "default",
    "wrist_strap": "none",
    "handle": "none",
    "closure": "clasp",
    "frame": "none",
    "crystal_decoration": "none",
    "pearl_decoration": "none",
    "embellishment_density": "minimal"
}
```


## 1.3.9. Mini Bag / Pochette

`template_id`: `mini-bag-pochette`

### Main Parameters


| Parameter | Supported IDs |
|---|---|
| `sub_category` | `mini-handbag`, `mini-flap`, `mini-crossbody`, `mini-pochette`, `phone-bag`, `card-holder-bag`, `micro-bag` |
| `material` | `default`, `leather`, `lambskin`, `patent`, `canvas`, `satin`, `velvet`, `crystal`, `beaded` |
| `asset_size` | `default`, `micro`, `mini`, `small` |
| `capacity` | `card`, `phone`, `phone-wallet`, `essentials` |
| `handle` | `none`, `short`, `top-handle`, `chain` |
| `closure` | `zipper`, `magnetic`, `flap`, `snap` |
| `phone_compartment` | `yes`, `no` |
| `interior_pocket` | `none`, `single`, `double` |
| `decorative_elements` | `none`, `logo`, `charm`, `crystal`, `chain`, `embroidery` |

### Other Parameters / Defaults


| Parameter | Default / Value |
|---|---|
| `width` | `14cm` |
| `height` | `10cm` |
| `depth` | `4cm` |
| `strap_length` | `110cm` |
| `chain_length` | `100cm` |
| `card_slots` | `4` |


### Asset Size Metadata


| Asset Size ID | Width | Height | Depth | Unit |
|---|---|---|---|---|
| `micro` | `10cm` | `7cm` | `3cm` | `cm` |
| `mini` | `14cm` | `10cm` | `4cm` | `cm` |
| `small` | `18cm` | `12cm` | `5cm` | `cm` |


### Example `options`

```json
{
    "sub_category": "mini-handbag",
    "material": "default",
    "asset_size": "default",
    "capacity": "card",
    "handle": "none",
    "closure": "zipper",
    "phone_compartment": "yes",
    "interior_pocket": "none",
    "decorative_elements": "none"
}
```



## 2.10. Satchel / Structured Bag

`template_id`: `satchel-structured-bag`


### Main Parameters

| Parameter | Supported IDs |
|---|---|
| `sub_category` | `structured-satchel`, `classic-satchel`, `frame-satchel`, `doctor-bag`, `box-satchel`, `top-handle-satchel`, `business-satchel` |
| `material` | `default`, `full-grain`, `top-grain`, `calfskin`, `cowhide`, `nappa`, `patent`, `suede`, `vegan-leather`, `canvas` |
| `asset_size` | `default`, `small`, `medium`, `large`, `business` |
| `structure` | `semi-structured`, `structured`, `rigid` |
| `frame` | `none`, `metal`, `internal`, `external` |
| `gusset` | `flat`, `small`, `medium`, `large` |
| `closure` | `zipper`, `turn-lock`, `push-lock`, `clasp`, `magnetic` |
| `lock` | `none`, `turn-lock`, `key-lock`, `combination` |
| `shoulder_strap` | `none`, `fixed`, `detachable`, `adjustable` |
| `laptop_compartment` | `none`, `13-inch`, `14-inch`, `15-inch`, `16-inch` |
| `bottom_feet` | `none`, `four`, `six` |

### Other Parameters / Defaults


| Parameter | Default / Value |
|---|---|
| `width` | `32cm` |
| `height` | `25cm` |
| `depth` | `13cm` |
| `handle_drop` | `12cm` |
| `handle_thickness` | `2.5cm` |
| `interior_compartments` | `3` |


### Asset Size Metadata


| Asset Size ID | Width | Height | Depth | Unit |
|---|---|---|---|---|
| `small` | `26cm` | `20cm` | `10cm` | `cm` |
| `medium` | `32cm` | `25cm` | `13cm` | `cm` |
| `large` | `40cm` | `30cm` | `16cm` | `cm` |
| `business` | `42cm` | `31cm` | `15cm` | `cm` |


### Example `options`

```json
{
    "sub_category": "structured-satchel",
    "material": "default",
    "asset_size": "default",
    "structure": "semi-structured",
    "frame": "none",
    "gusset": "flat",
    "closure": "zipper",
    "lock": "none",
    "shoulder_strap": "none",
    "laptop_compartment": "none",
    "bottom_feet": "none"
}
```


# 4. Bag Design Parameter Rules

1. Always use the exact `template_id` from the supported template list.
4. Scalar dimensions and defaults shown under `Other Parameters / Defaults` are configuration defaults; they accept real values, such as length, height, depth.
5. Do not pass an option from another template unless the selected template explicitly defines that parameter.
6. When a user provides natural-language requirements, map them to the closest supported IDs and preserve any additional design intent in `prompt`.
7. Reference images may be supplied through `images`; use the prompt to describe the desired material, construction, printing, decoration, hardware, and manufacturing intent.
8. For custom text or logo printing, describe the exact text, logo, placement, and color in `prompt` unless a dedicated structured parameter is available in the selected template.
