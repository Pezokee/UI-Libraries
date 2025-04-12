Here’s your complete `documentation.md` file, all in one, fully formatted and clear:

---

```markdown
# 📘 Informant.WTF Script Documentation

> **Credits:**  
> 👤 Original Developers: `@xz`, `@goof`  
> 🔗 Discord Invite: `informant.wtf`  
> 🛠️ UI Library by [drillygzzly](https://github.com/drillygzzly)

---

## ⚙️ Global Configuration

```lua
getgenv().Config = {
    Invite = "informant.wtf",
    Version = "0.0",
}

getgenv().luaguardvars = {
    DiscordName = "username#0000",
}
```

- `Config.Invite`: Sets default Discord invite.  
- `Config.Version`: Version string for your loader.  
- `luaguardvars.DiscordName`: Set to your Discord tag.

---

## 🧱 Library Initialization

```lua
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/drillygzzly/Other/main/1"))()
library:init()
```

- Loads the custom UI library.
- `library:init()` must be called or the UI won't work.

---

## 🪟 Window Creation

```lua
local Window = library.NewWindow({
    title = "Informant.Wtf",
    size = UDim2.new(0, 525, 0, 650)
})
```

- `title`: Text displayed on top.
- `size`: Sets UI size (X, Y).

---

## 🗂️ Tabs & Sections

```lua
local tabs = {
    Tab1 = Window:AddTab("Tab1"),
    Settings = library:CreateSettingsTab(Window),
}

local sections = {
    Section1 = tabs.Tab1:AddSection("Section1", 1), -- Left side
    Section2 = tabs.Tab1:AddSection("Section2", 2), -- Right side
}
```

- **Tabs** organize major features.
- **Sections** split content into left (1) and right (2).

---

## 🧩 UI Components

### ✅ Toggle

```lua
sections.Section1:AddToggle({
    enabled = true,
    text = "Toggle1",
    flag = "Toggle_1",
    tooltip = "Tooltip1",
    risky = true,
    callback = function(state)
        print("Toggle Is Now Set To : ".. tostring(state))
    end
})
```

- Creates a switch with on/off state.
- `risky = true`: Colors label red.
- `callback`: Runs when toggled.

---

### 🖱️ Button

```lua
sections.Section1:AddButton({
    text = "Button1",
    flag = "Button_1",
    tooltip = "Tooltip1",
    confirm = false,
    callback = function(v)
        print(v)
    end
})
```

- Adds a clickable button.
- `confirm = true`: Requires confirmation click.

---

### 📏 Slider

```lua
sections.Section1:AddSlider({
    text = "Slider",
    flag = 'Slider_1',
    value = 0.000,
    min = 0.1,
    max = 0.999,
    increment = 0.001,
    tooltip = "Tooltip1",
    callback = function(v)
        print("Slider Value Is Now : ".. v)
    end
})
```

- Adjustable value bar.
- Range and increment defined via `min`, `max`, `increment`.

---

### ⌨️ Keybind

```lua
sections.Section1:AddBind({
    text = "Keybind",
    flag = "Key_1",
    nomouse = true,
    noindicator = true,
    tooltip = "Tooltip1",
    mode = "toggle",
    bind = Enum.KeyCode.Q,
    keycallback = function()
        print("Keybind Changed!")
    end
})
```

- Assigns a keyboard shortcut.
- `mode = "toggle"` or `"hold"`.

---

### 📋 Dropdown List

```lua
sections.Section1:AddList({
    text = "List",
    flag = "List_1",
    multi = false,
    value = "1",
    values = { "1", "2", "3" },
    tooltip = "Tooltip1",
    callback = function(v)
        print("List Value Is Now : ".. v)
    end
})
```

- Simple drop-down selection.
- `multi = true`: Allows multiple selections.

---

### 📝 TextBox

```lua
sections.Section1:AddBox({
    text = "TextBox1",
    input = "PlaceHolder1",
    flag = "Text_1",
    focused = true,
    callback = function(v)
        print(v)
    end
})
```

- Allows custom text input.
- `focused = true`: Starts focused on load.

---

### 📄 Static Text Label

```lua
sections.Section1:AddText({
    text = "Text1",
    flag = "Text_1"
})
```

- Displays static UI text for info or branding.

---

### 🎨 Color Picker

```lua
sections.Section1:AddColor({
    text = "ColorPicker1",
    flag = "Color_1",
    tooltip = "ToolTip1",
    color = Color3.new(255, 255, 255),
    trans = 0,
    open = false,
    callback = function() end
})
```

- Lets users select colors (RGB + transparency).
- Optional `callback` runs when changed.

---

### 🔖 Separator

```lua
sections.Section1:AddSeparator({
    text = "Separator"
})
```

- Adds a visual divider between UI elements.

---

## 🔔 Notifications

```lua
library:SendNotification("Notification", 5, Color3.new(255, 0, 0))
```

- Shows an in-game popup for `5` seconds.
- Customize message and color.

---

## 🧷 Flags Reference

Each UI component includes a `flag`, which acts as a unique identifier to:
- Save/load values.
- Reference UI elements in external scripts.
- Dynamically modify states.

---

## 🪟 Controlling the Window

```lua
Window:SetOpen(true) -- Opens the GUI
Window:SetOpen(false) -- Closes the GUI
```

- Programmatically toggle the UI visibility.

---

## ❗ Notes

- This UI system is modular—add new elements by duplicating the pattern inside `AddSection()`.
- Use `library:SaveConfig()` and `library:LoadConfig()` to persist user settings (if supported in the base library).
- All risky toggles or features should be clearly labeled to warn users.

---

## ⚠️ Disclaimer

This tool is provided for **educational purposes** only.  
Misuse may violate Roblox Terms of Service and could result in account suspension or permanent bans.  
Use responsibly and at your own risk.

---
```

Let me know if you want:
- A second page for advanced dev features.
- Exported `.pdf` or `.txt` versions.
- A version formatted for GitHub README or Notion.
