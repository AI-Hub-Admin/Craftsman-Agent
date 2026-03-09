## Craftsman-Agent
[GitHub]() | [Open Source AI Agent Marketplace DeepNLP](https://www.deepnlp.org/store/ai-agent)|[Agent RL Dataset](https://www.deepnlp.org/store/dataset) | [Deploy & Live URL](https://deepnlp.org/doc/agent_mcp_deployment) | [ProductHunt](https://www.producthunt.com/products/craftsman-agent?launch=craftsman-agent)

<img src="https://static.aiagenta2z.com/scripts/img/comment/80e65ff34838c544f9560047f34a3834.jpg" alt="Craftsman" width="48" height="48" /> Craftsman Agent is an AI assistant that transforms your text prompts into 3D build instructions — creating things from LEGO sets and Minecraft worlds to figurines and modular designs. Get detailed, step-by-step assembly charts and bring your ideas to life, faster and smarter than ever.
Now Supported Skills, MCP and Use in Agent Router Playground to turn your creative ideas to a 3D build instruction plans.

(Still in WIP, Please welcome to star the repo and will notify you latest update)

### Example 

prompt: Build a blue and white yacht with 5 decks

Final 3D Rendering Image From 4 angles

![Four Angle Charts](https://raw.githubusercontent.com/AI-Hub-Admin/Craftsman-Agent/refs/heads/main/docs/craftsman_agent_1.jpg)

Step by Step Assembly Charts
![Step by Step](https://raw.githubusercontent.com/AI-Hub-Admin/Craftsman-Agent/refs/heads/main/docs/craftsman_agent_2.jpg)

Detailed Charts
![Detailed Charts](https://raw.githubusercontent.com/AI-Hub-Admin/Craftsman-Agent/refs/heads/main/docs/craftsman_agent_3.jpg)


## Usage

### Skills

We have prepared skills to two functions `generate_lego_build_plan` and `generate_minecraft_build_plan` in both typescript and python.

| function | description |
| --- | ---- |
| generate_lego_build_plan | Call Craftsman Agent OneKey Router to generate a LEGO build plan. |
| generate_minecraft_build_plan | Call Craftsman Agent OneKey Router to generate a Minecraft build plan. |


Add Skills Using `agtm` or vercel `skills`
```commandline
agtm add --github https://github.com/AI-Hub-Admin/Craftsman-Agent --skill craftsman-agent-skills
```

```commandline
npx skills add https://github.com/ai-hub-admin/craftsman-agent --skill craftsman-agent-skills
```

### MCP

Usage in your AI Clients
```json
{
    "mcpServers": {
        "craftsman-agent": {
            "url": "https://craftsman-agent.aiagenta2z.com/craftsman-agent/mcp"
        }
    }
}
```


### Agent URL Playground

Visit the Agent Router PlayGround to Use the Craftsman Live at [Agent Router Playground](https://agent.deepnlp.org/agent/craftsman-agent/craftsman-agent)


#### Direct API Calling

Note that the each workflow runs involve calling of Gemini Nano Banana 2 Image generation and 3D Rendering APIs.
So New Registered User will enjoy free trials, and please upgrade to [pro subscription](https://deepnlp.org/pricing) to explore more.

Get Your DeepNLP Router [Access Key](https://www.deepnlp.org/workspace/keys) ``

```
curl -X POST "https://agent.deepnlp.org/agent?onekey={your_access_key}" \
-H "Content-Type: application/json" \
-d '{
  "unique_id": "craftsman-agent/craftsman-agent",
  "api_id": "generate_lego_build_plan",
  "data": {
    "prompt": "pink lego phone",
    "ref_image_url": [],
    "mode": "basic"
  }
}'
```

And you can use the beta key for demo illustration purpose 

```
curl -X POST "https://agent.deepnlp.org/agent?onekey=BETA_TEST_KEY_MARCH_2026" \
-H "Content-Type: application/json" \
-d '{
  "unique_id": "craftsman-agent/craftsman-agent",
  "api_id": "generate_lego_build_plan",
  "data": {
    "prompt": "Generate a blue and white yacht for 5 decks",
    "ref_image_url": [],
    "mode": "basic"
  }
}'
```

```
{"success":true,"inventory_list":[{"color":"bright_blue","size":[1,1,1],"position":[4,0,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,1,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,2,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,3,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,3,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,3,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,4,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,4,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,4,0]},{"color":"bright_blue","size":[1,1,1],"position":[2,5,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,5,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,5,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,5,0]},{"color":"bright_blue","size":[1,1,1],"position":[6,5,0]},{"color":"bright_blue","size":[1,1,1],"position":[2,6,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,6,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,6,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,6,0]},{"color":"bright_blue","size":[1,1,1],"position":[6,6,0]},{"color":"bright_blue","size":[1,1,1],"position":[1,7,0]},{"color":"bright_blue","size":[1,1,1],"position":[2,7,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,7,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,7,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,7,0]},{"color":"bright_blue","size":[1,1,1],"position":[6,7,0]},{"color":"bright_blue","size":[1,1,1],"position":[7,7,0]},{"color":"bright_blue","size":[1,1,1],"position":[1,8,0]},{"color":"bright_blue","size":[1,1,1],"position":[2,8,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,8,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,8,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,8,0]},{"color":"bright_blue","size":[1,1,1],"position":[6,8,0]},{"color":"bright_blue","size":[1,1,1],"position":[7,8,0]},{"color":"bright_blue","size":[1,1,1],"position":[1,9,0]},{"color":"bright_blue","size":[1,1,1],"position":[2,9,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,9,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,9,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,9,0]},{"color":"bright_blue","size":[1,1,1],"position":[6,9,0]},{"color":"bright_blue","size":[1,1,1],"position":[7,9,0]},{"color":"bright_blue","size":[1,1,1],"position":[1,10,0]},{"color":"bright_blue","size":[1,1,1],"position":[2,10,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,10,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,10,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,10,0]},{"color":"bright_blue","size":[1,1,1],"position":[6,10,0]},{"color":"bright_blue","size":[1,1,1],"position":[7,10,0]},{"color":"bright_blue","size":[1,1,1],"position":[1,11,0]},{"color":"bright_blue","size":[1,1,1],"position":[2,11,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,11,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,11,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,11,0]},{"color":"bright_blue","size":[1,1,1],"position":[6,11,0]},{"color":"bright_blue","size":[1,1,1],"position":[7,11,0]},{"color":"bright_blue","size":[1,1,1],"position":[2,12,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,12,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,12,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,12,0]},{"color":"bright_blue","size":[1,1,1],"position":[6,12,0]},{"color":"bright_blue","size":[1,1,1],"position":[2,13,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,13,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,13,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,13,0]},{"color":"bright_blue","size":[1,1,1],"position":[6,13,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,14,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,14,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,14,0]},{"color":"bright_blue","size":[1,1,1],"position":[3,15,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,15,0]},{"color":"bright_blue","size":[1,1,1],"position":[5,15,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,16,0]},{"color":"bright_blue","size":[1,1,1],"position":[4,17,0]},{"color":"bright_red","size":[1,1,1],"position":[4,0,1]},{"color":"bright_red","size":[1,1,1],"position":[4,1,1]},{"color":"bright_red","size":[1,1,1],"position":[3,2,1]},{"color":"bright_red","size":[1,1,1],"position":[4,2,1]},{"color":"bright_red","size":[1,1,1],"position":[5,2,1]},{"color":"bright_red","size":[1,1,1],"position":[3,3,1]},{"color":"bright_red","size":[1,1,1],"position":[4,3,1]},{"color":"bright_red","size":[1,1,1],"position":[5,3,1]},{"color":"bright_red","size":[1,1,1],"position":[2,4,1]},{"color":"bright_red","size":[1,1,1],"position":[3,4,1]},{"color":"bright_red","size":[1,1,1],"position":[4,4,1]},{"color":"bright_red","size":[1,1,1],"position":[5,4,1]},{"color":"bright_red","size":[1,1,1],"position":[6,4,1]},{"color":"bright_red","size":[1,1,1],"position":[2,5,1]},{"color":"bright_red","size":[1,1,1],"position":[3,5,1]},{"color":"bright_red","size":[1,1,1],"position":[4,5,1]},{"color":"bright_red","size":[1,1,1],"position":[5,5,1]},{"color":"bright_red","size":[1,1,1],"position":[6,5,1]},{"color":"bright_red","size":[1,1,1],"position":[1,6,1]},{"color":"bright_red","size":[1,1,1],"position":[2,6,1]},{"color":"bright_red","size":[1,1,1],"position":[3,6,1]},{"color":"bright_red","size":[1,1,1],"position":[4,6,1]},{"color":"bright_red","size":[1,1,1],"position":[5,6,1]},{"color":"bright_red","size":[1,1,1],"position":[6,6,1]},{"color":"bright_red","size":[1,1,1],"position":[7,6,1]},{"color":"bright_red","size":[1,1,1],"position":[1,7,1]},{"color":"bright_red","size":[1,1,1],"position":[2,7,1]},{"color":"bright_red","size":[1,1,1],"position":[3,7,1]},{"color":"bright_red","size":[1,1,1],"position":[4,7,1]},{"color":"bright_red","size":[1,1,1],"position":[5,7,1]},{"color":"bright_red","size":[1,1,1],"position":[6,7,1]},{"color":"bright_red","size":[1,1,1],"position":[7,7,1]},{"color":"bright_red","size":[1,1,1],"position":[0,8,1]},{"color":"bright_red","size":[1,1,1],"position":[1,8,1]},{"color":"bright_red","size":[1,1,1],"position":[2,8,1]},{"color":"bright_red","size":[1,1,1],"position":[3,8,1]},{"color":"bright_red","size":[1,1,1],"position":[4,8,1]},{"color":"bright_red","size":[1,1,1],"position":[5,8,1]},{"color":"bright_red","size":[1,1,1],"position":[6,8,1]},{"color":"bright_red","size":[1,1,1],"position":[7,8,1]},{"color":"bright_red","size":[1,1,1],"position":[8,8,1]},{"color":"bright_red","size":[1,1,1],"position":[0,9,1]},{"color":"bright_red","size":[1,1,1],"position":[1,9,1]},{"color":"bright_red","size":[1,1,1],"position":[2,9,1]},{"color":"bright_red","size":[1,1,1],"position":[3,9,1]},{"color":"bright_red","size":[1,1,1],"position":[4,9,1]},{"color":"bright_red","size":[1,1,1],"position":[5,9,1]},{"color":"bright_red","size":[1,1,1],"position":[6,9,1]},{"color":"bright_red","size":[1,1,1],"position":[7,9,1]},{"color":"bright_red","size":[1,1,1],"position":[8,9,1]},{"color":"bright_red","size":[1,1,1],"position":[0,10,1]},{"color":"bright_red","size":[1,1,1],"position":[1,10,1]},{"color":"bright_red","size":[1,1,1],"position":[2,10,1]},{"color":"bright_red","size":[1,1,1],"position":[3,10,1]},{"color":"bright_red","size":[1,1,1],"position":[4,10,1]},{"color":"bright_red","size":[1,1,1],"position":[5,10,1]},{"color":"bright_red","size":[1,1,1],"position":[6,10,1]},{"color":"bright_red","size":[1,1,1],"position":[7,10,1]},{"color":"bright_red","size":[1,1,1],"position":[8,10,1]},{"color":"bright_red","size":[1,1,1],"position":[1,11,1]},{"color":"bright_red","size":[1,1,1],"position":[2,11,1]},{"color":"bright_red","size":[1,1,1],"position":[3,11,1]},{"color":"bright_red","size":[1,1,1],"position":[4,11,1]},{"color":"bright_red","size":[1,1,1],"position":[5,11,1]},{"color":"bright_red","size":[1,1,1],"position":[6,11,1]},{"color":"bright_red","size":[1,1,1],"position":[7,11,1]},{"color":"bright_red","size":[1,1,1],"position":[1,12,1]},{"color":"bright_red","size":[1,1,1],"position":[2,12,1]},{"color":"bright_red","size":[1,1,1],"position":[3,12,1]},{"color":"bright_red","size":[1,1,1],"position":[4,12,1]},{"color":"bright_red","size":[1,1,1],"position":[5,12,1]},{"color":"bright_red","size":[1,1,1],"position":[6,12,1]},{"color":"bright_red","size":[1,1,1],"position":[7,12,1]},{"color":"bright_red","size":[1,1,1],"position":[2,13,1]},{"color":"bright_red","size":[1,1,1],"position":[3,13,1]},{"color":"bright_red","size":[1,1,1],"position":[4,13,1]},{"color":"bright_red","size":[1,1,1],"position":[5,13,1]},{"color":"bright_red","size":[1,1,1],"position":[6,13,1]},{"color":"bright_red","size":[1,1,1],"position":[2,14,1]},{"color":"bright_red","size":[1,1,1],"position":[3,14,1]},{"color":"bright_red","size":[1,1,1],"position":[4,14,1]},{"color":"bright_red","size":[1,1,1],"position":[5,14,1]},{"color":"bright_red","size":[1,1,1],"position":[6,14,1]},{"color":"bright_red","size":[1,1,1],"position":[3,15,1]},{"color":"bright_red","size":[1,1,1],"position":[4,15,1]},{"color":"bright_red","size":[1,1,1],"position":[5,15,1]},{"color":"bright_red","size":[1,1,1],"position":[3,16,1]},{"color":"bright_red","size":[1,1,1],"position":[4,16,1]},{"color":"bright_red","size":[1,1,1],"position":[5,16,1]},{"color":"bright_red","size":[1,1,1],"position":[4,17,1]},{"color":"trans_blue","size":[1,1,1],"position":[3,4,2]},{"color":"trans_blue","size":[1,1,1],"position":[4,4,2]},{"color":"trans_blue","size":[1,1,1],"position":[5,4,2]},{"color":"trans_blue","size":[1,1,1],"position":[3,5,2]},{"color":"trans_blue","size":[1,1,1],"position":[4,5,2]},{"color":"trans_blue","size":[1,1,1],"position":[5,5,2]},{"color":"trans_blue","size":[1,1,1],"position":[3,6,2]},{"color":"trans_blue","size":[1,1,1],"position":[4,6,2]},{"color":"trans_blue","size":[1,1,1],"position":[5,6,2]},{"color":"trans_blue","size":[1,1,1],"position":[2,7,2]},{"color":"trans_blue","size":[1,1,1],"position":[3,7,2]},{"color":"trans_blue","size":[1,1,1],"position":[4,7,2]},{"color":"trans_blue","size":[1,1,1],"position":[5,7,2]},{"color":"trans_blue","size":[1,1,1],"position":[6,7,2]},{"color":"trans_blue","size":[1,1,1],"position":[2,8,2]},{"color":"trans_blue","size":[1,1,1],"position":[3,8,2]},{"color":"trans_blue","size":[1,1,1],"position":[4,8,2]},{"color":"trans_blue","size":[1,1,1],"position":[5,8,2]},{"color":"trans_blue","size":[1,1,1],"position":[6,8,2]},{"color":"trans_blue","size":[1,1,1],"position":[2,9,2]},{"color":"trans_blue","size":[1,1,1],"position":[3,9,2]},{"color":"trans_blue","size":[1,1,1],"position":[4,9,2]},{"color":"trans_blue","size":[1,1,1],"position":[5,9,2]},{"color":"trans_blue","size":[1,1,1],"position":[6,9,2]},{"color":"trans_blue","size":[1,1,1],"position":[2,10,2]},{"color":"trans_blue","size":[1,1,1],"position":[3,10,2]},{"color":"trans_blue","size":[1,1,1],"position":[4,10,2]},{"color":"trans_blue","size":[1,1,1],"position":[5,10,2]},{"color":"trans_blue","size":[1,1,1],"position":[6,10,2]},{"color":"trans_blue","size":[1,1,1],"position":[2,11,2]},{"color":"trans_blue","size":[1,1,1],"position":[3,11,2]},{"color":"trans_blue","size":[1,1,1],"position":[4,11,2]},{"color":"trans_blue","size":[1,1,1],"position":[5,11,2]},{"color":"trans_blue","size":[1,1,1],"position":[6,11,2]},{"color":"trans_blue","size":[1,1,1],"position":[3,12,2]},{"color":"trans_blue","size":[1,1,1],"position":[4,12,2]},{"color":"trans_blue","size":[1,1,1],"position":[5,12,2]},{"color":"trans_blue","size":[1,1,1],"position":[3,13,2]},{"color":"trans_blue","size":[1,1,1],"position":[4,13,2]},{"color":"trans_blue","size":[1,1,1],"position":[5,13,2]},{"color":"trans_blue","size":[1,1,1],"position":[2,5,3]},{"color":"trans_blue","size":[1,1,1],"position":[3,5,3]},{"color":"trans_blue","size":[1,1,1],"position":[4,5,3]},{"color":"trans_blue","size":[1,1,1],"position":[5,5,3]},{"color":"trans_blue","size":[1,1,1],"position":[6,5,3]},{"color":"trans_blue","size":[1,1,1],"position":[2,6,3]},{"color":"trans_blue","size":[1,1,1],"position":[3,6,3]},{"color":"trans_blue","size":[1,1,1],"position":[4,6,3]},{"color":"trans_blue","size":[1,1,1],"position":[5,6,3]},{"color":"trans_blue","size":[1,1,1],"position":[6,6,3]},{"color":"trans_blue","size":[1,1,1],"position":[2,7,3]},{"color":"trans_blue","size":[1,1,1],"position":[3,7,3]},{"color":"trans_blue","size":[1,1,1],"position":[4,7,3]},{"color":"trans_blue","size":[1,1,1],"position":[5,7,3]},{"color":"trans_blue","size":[1,1,1],"position":[6,7,3]},{"color":"trans_blue","size":[1,1,1],"position":[2,8,3]},{"color":"trans_blue","size":[1,1,1],"position":[3,8,3]},{"color":"trans_blue","size":[1,1,1],"position":[4,8,3]},{"color":"trans_blue","size":[1,1,1],"position":[5,8,3]},{"color":"trans_blue","size":[1,1,1],"position":[6,8,3]},{"color":"trans_blue","size":[1,1,1],"position":[2,9,3]},{"color":"trans_blue","size":[1,1,1],"position":[3,9,3]},{"color":"trans_blue","size":[1,1,1],"position":[4,9,3]},{"color":"trans_blue","size":[1,1,1],"position":[5,9,3]},{"color":"trans_blue","size":[1,1,1],"position":[6,9,3]},{"color":"trans_blue","size":[1,1,1],"position":[2,10,3]},{"color":"trans_blue","size":[1,1,1],"position":[3,10,3]},{"color":"trans_blue","size":[1,1,1],"position":[4,10,3]},{"color":"trans_blue","size":[1,1,1],"position":[5,10,3]},{"color":"trans_blue","size":[1,1,1],"position":[6,10,3]},{"color":"trans_blue","size":[1,1,1],"position":[2,11,3]},{"color":"trans_blue","size":[1,1,1],"position":[3,11,3]},{"color":"trans_blue","size":[1,1,1],"position":[4,11,3]},{"color":"trans_blue","size":[1,1,1],"position":[5,11,3]},{"color":"trans_blue","size":[1,1,1],"position":[6,11,3]},{"color":"trans_blue","size":[1,1,1],"position":[3,8,4]},{"color":"trans_blue","size":[1,1,1],"position":[4,8,4]},{"color":"trans_blue","size":[1,1,1],"position":[5,8,4]},{"color":"trans_blue","size":[1,1,1],"position":[3,9,4]},{"color":"trans_blue","size":[1,1,1],"position":[4,9,4]},{"color":"trans_blue","size":[1,1,1],"position":[5,9,4]},{"color":"trans_blue","size":[1,1,1],"position":[3,10,4]},{"color":"trans_blue","size":[1,1,1],"position":[4,10,4]},{"color":"trans_blue","size":[1,1,1],"position":[5,10,4]},{"color":"white","size":[0.2,0.2,2],"position":[4,9,5]}],"overall_image":{"iso":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/view_iso.png","top":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/view_top.png","front":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/view_front.png","side":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/view_side.png"},"inventory_image":{"inventory_parts":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/inventory_parts.png","description":["Color bright_red, Size 1 x 1 x 1, Quantity 90","Color trans_blue, Size 1 x 1 x 1, Quantity 84","Color bright_blue, Size 1 x 1 x 1, Quantity 72","Color white, Size 0 x 0 x 2, Quantity 1"]},"assembly_step_image":{"0":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/step_0.png","1":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/step_1.png","2":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/step_2.png","3":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/step_3.png","4":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/step_4.png","5":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/step_5.png","6":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/step_6.png","7":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/step_7.png","8":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/step_8.png","9":"https://craftsman-agent.aiagenta2z.com/craftsman-agent/static/TEMP_c0b498a3/lego_plan/step_9.png"}}
```


### Community Software

3D Motion Animation: Cinema 4D (Paid/Not Free), 
Blender: 3D Software
3D Model Creation: Build in LDD, Studio, or CAD.
Step Decomposition/ Exploded View Rendering / Annotation /  Export/Publish/  Inventory Listing: Generate automatic parts list per step or total.


### Related
[AI Agent Marketplace](https://www.deepnlp.org/store/ai-agent)    
[AI Agent A2Z Deployment](https://www.deepnlp.org/workspace/deploy)    
[PH AI Agent Router](https://www.producthunt.com/products/deepnlp-ai-agent-marketplace-router)    
[PH AI Agent A2Z Infra](https://www.producthunt.com/products/ai-agent-a2z-infra-deployment-platform)    
[GitHub AI Agent Marketplace](https://github.com/aiagenta2z/ai-agent-marketplace)    


