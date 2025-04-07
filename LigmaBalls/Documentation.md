```lua
-- Load the Paradox UI library
local paradox = loadstring(game:HttpGet("https://raw.githubusercontent.com/paradoxroblox/paradox/refs/heads/discord.gg/paradoxroblox/library"))()

-- Create the main window
local window = paradox:window({
    currentgame = "MyGame",  -- You can rename this
    version = "v1.0"
})

-- Create a tab inside the window
paradox:tab({
    name = "Main",  -- Tab name
    image = "rbxassetid://10723407389"  -- Optional icon
})

-- Add a toggle to the "Main" tab
paradox:toggle({
    name = "Enable Feature",  -- Toggle name
    parent = "Main",          -- Parent tab
    callback = function(state)
        print("hello world!")  -- Placeholder function
    end,
})

-- Add first button
paradox:button({
    name = "Click Me",        -- Button name
    parent = "Main",          -- Parent tab
    callback = function()
        print("hello world!")  -- Placeholder function
    end,
})

-- Add second button
paradox:button({
    name = "Stay Active",     -- Button name
    parent = "Main",          -- Parent tab
    callback = function()
        print("hello world!")  -- Placeholder function
    end,
})
