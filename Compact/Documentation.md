This tutorial will guide you through using the **Compact UI Library** for creating a simple user interface with various interactive elements like toggles, sliders, selections, and dropdowns. It will show you how to add elements, customize their behaviors, and handle callbacks effectively.

### Prerequisites
Before you start, you need the **Compact UI Library**. You can load it into your script with the following line:

```lua
local UI = loadstring(game:HttpGet("https://raw.githubusercontent.com/Pezokee/UI-Libraries/refs/heads/main/Source"))()
```

## Getting Started

To initialize the UI, you need to call the `init` method with parameters for your UI's title, version, and description. Here’s an example:

```lua
UI = UI.init("Showcase", "v1.0.0", "SHOWCASE")
```

### Add Tabs and Sections

In the UI, you can add multiple tabs and sections. Each tab can contain several sections that group related elements together.

```lua
local AimOne, AimTwo = UI:AddTab("Aim", "Silent Aim")
```

Here, we're adding two tabs: **Aim** and **Silent Aim**.

### Adding Seperators

To organize your UI, you can use **separators** to divide sections within a tab:

```lua
local Section = AimOne:AddSeperator("Silent Aim")
```

This separates the elements within the **Aim** tab and groups them under the **Silent Aim** header.

## Interactive UI Elements

### 1. **Toggles**

A **Toggle** allows the user to switch between two states (on or off). You can add a toggle with a callback function that is triggered when the toggle changes.

Example:

```lua
local masterToggle = Section:AddToggle({
    title = "Enabled",
    desc = "This is a small tip which will appear when the user hovers over this toggle.",
    callback = function(state)
        print("Toggled: ", state)
    end
})
```

In this example, when the toggle is switched, the `state` (either `true` or `false`) will be printed to the console.

### 2. **Sliders**

Sliders allow users to select a value within a specific range. You can create a slider to adjust values like the **Field of View (FOV)**.

Example:

```lua
local slider = Section:AddSlider({
    title = "Field of view",
    values = {min=0, max=250, default=50},
    callback = function(set)
        print("FOV has been set to: ", set)
    end,
})
```

This slider lets users adjust the **Field of View**, with values between `0` and `250`. The `callback` function will print the selected value when the slider is moved.

### 3. **Color Pickers**

Some elements, like the **Field of View** (FOV) display, may include a color picker that allows users to select a color.

Example:

```lua
local fovColor = Section:AddToggle({
    title = "Display field of view",
    checked = true,
    callback = function(state)
        print("FOV display toggled", state)
        print("FOV color", fovColor.colorpicker.getColor())
    end,
    colorpicker = {
        default = Color3.new(0,0.5,1),
        callback = function(color)
            print("New FOV color selected: ", color)
        end
    }
})
```

This code sets the default color of the FOV display to **blue** and prints the selected color when the user changes it.

### 4. **Selections**

A **Selection** element lets users choose from multiple options. This is particularly useful for selecting body parts, items, or other predefined choices.

Example:

```lua
local bodyparts = { "Head", "Torso", "Left Arm", "Right Arm", "Left Leg", "Right Arm" }
local selection = Section:AddSelection({
    title = "Bodyparts",
    options = bodyparts,
    callback = function(selected)
        print("Selected the following:")
        for _, i in pairs(selected) do print(" -", bodyparts[i]) end
    end
})
```

This creates a list of body parts for the user to select from. The callback function prints the selected options.

### 5. **Dropdowns**

Dropdowns allow users to select from a list of options. You can add a dropdown like this:

```lua
local fruit = {"lime", "lemon", "mango", "nut"}
local dropdown = Section:AddDropdown({
    title = "Demonstrative dropdown",
    options = fruit,
    callback = function(selected, actual)
        print(selected, fruit[selected], actual)
    end
})
```

In this example, users can select a fruit from a dropdown menu. The `callback`
