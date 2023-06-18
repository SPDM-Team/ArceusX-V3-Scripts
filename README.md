# Arceus UI

**Create your own exclusive Arceus X script with our UI Library in 3 steps!**

⚠️ The script will run exclusively in Arceus X executor.

---

1. Include the library in a new variable `ArceusUI` by loading the following url via loadstring:
```lua
local ArceusUI = loadstring(game:HttpGet("https://raw.githubusercontent.com/SPDM-Team/ArceusX-V3-Scripts/main/ArceusUI.lua"))()
```

2. Setup the UI with the following functions:

---

### Setting up the Title with `:SetTitle`
`rich-text ✅`
     
⚠️ No returned parameters.
     
**Parameters:**
|   | Type | Description |
| - | ---- | ----------- |
| 1 | String | The UI title |

**Example:**
```lua
ArceusUI:SetTitle("Arceus X <font color='rgb(255, 0, 0)'>|</font> MyScript")
```
      
---

### Setting up the Script logo with `:SetLogo`

⚠️ Script logo is located to the bottom-right corner when the ui is closed, this is not the arceus logo.

⚠️ This function will download and save the image as file

⚠️ No returned parameters.
      
**Parameters:**
|   | Type | Description |
| - | ---- | ----------- |
| 1 | String | Name and Extention of the file |
| 2 | String | Url of the image |
      
**Example:**
```lua
ArceusUI:SetLogo("MyLogo.png", "https://mywebsite/myimage.png")
```
      
---

### Adding a Button with `:AddButton`

⚠️ The position of the button depends on how many elements you have already added.

**Parameters:**
|   | Type | Passed arguments | Description |
| - | ---- | ---------------- | ----------- |
| 1 | String | | Text of the button |
| 2 | Function | Any ( ... ) | The code of the button |
| 3 | Any ( ... ) | | Extra arguments passed to the function when pressed |

**Returned values:**
|   | Type | Description |
| - | ---- | ----------- |
| 1 | ImageButton | Button element with its children |

**Example:**
```lua
local myButton = ArceusUI:AddButton("MyButton", function(...)
    local extraValues = {...}
    print("Pressed")
end, myExtraValues)
```
❗ Note that `myExtraValues` and `...` can be unused.

---

### Adding a Toggle button with `:AddToggle`

⚠️ The position of the Toggle button depends on how many elements you have already added.

**Parameters:**
|   | Type | Passed arguments | Description |
| - | ---- | ---------------- | ----------- |
| 1 | String | | Text of the combo box |
| 2 | Function | Boolean, Any ( ... ) | The combo box code where the first argument is the toggle status |
| 3 | Boolean | | Starter status of the toggle
| 4 | Any ( ... ) | | Extra arguments passed to the function when status changed |

**Returned values:**
|   | Type | Description |
| - | ---- | ----------- |
| 1 | ImageButton | Button element with its children |

**Example:**
```lua
local myToggle = ArceusUI:AddToggle("MyToggle", function(myStatus, ...)
    local extraValues = {...}
    print("Toggle status:", myStatus)
end, myExtraValues)
```
❗ Note that `myExtraValues` and `...` can be unused.

---

### Adding a Combo box with `:AddComboBox`

⚠️ The position of the combo box depends on how many elements you have already added.

**Parameters:**
|   | Type | Passed arguments | Description |
| - | ---- | ---------------- | ----------- |
| 1 | String | | Text of the combo box |
| 2 | Table | Array of strings | The combo box options |
| 3 | Function | String, Any ( ... ) | The combo box code where the first argument is the choosed option |
| 4 | Any ( ... ) | | Extra arguments passed to the function when an option is choosed |

**Returned values:**
|   | Type | Description |
| - | ---- | ----------- |
| 1 | ImageButton | Button element with its children |

**Example:**
```lua
local myCombo = ArceusUI:AddComboBox("MyCombo", {"MyOption1", "MyOption2"}, function(myChoice, ...)
    local extraValues = {...}
    print("Combo selection:", myChoice)
end, myExtraValues)
```
❗ Note that `myExtraValues` and `...` can be unused.

---

### Adding a Numeric Up-Down with `:AddUpDown`

⚠️ The position of the up-down depends on how many elements you have already added.

**Parameters:**
|   | Type | Passed arguments | Description |
| - | ---- | ---------------- | ----------- |
| 1 | String | | Text of the up-down |
| 2 | Function | Number, Any ( ... ) | The up-down code where the first argument is the numeric value |
| 3 | Number | | Start value, default is 1 |
| 4 | Number | | Increment value, default is 1 |
| 5 | Number | | Minimum value, default is **-math.huge** |
| 6 | Number | | Maximum value, default is **math.huge** |
| 7 | Any ( ... ) | | Extra arguments passed to the function when the value is updated |

**Returned values:**
|   | Type | Description |
| - | ---- | ----------- |
| 1 | Frame | Frame element with its children |

**Example:**
```lua
local myUpDown = ArceusUI:AddComboBox("MyUpDown", function(myNumericValue, ...)
    local extraValues = {...}
    print("UpDown value:", myNumericValue)
end, 0, 1, 0, 10, myExtraValues) -- Starts at 0, increment by 1 each time, min 0 and max 10
```
❗ Note that `myExtraValues` and `...` can be unused.

---

# 3. Manage and display the UI:

### Getting the UI path with `:Parent()`

❓ Usefull to add extra UI elements **OUTSIDE** of the Main Frame.

⚠️ No parameters.

**Returned values:**
|   | Type | Description |
| - | ---- | ----------- |
| 1 | ScreenGui | The GUI |

**Example:**
```lua
local myNewFrame = Instance.new("Frame")
myNewFrame.Parent = ArceusUI:Parent()
```

---

### Destroying the UI with `:Remove()`

❓ Usefull if you want to remove the GUI from the game.

⚠️ No returned values.

⚠️ No parameters.

**Example:**
```lua
ArceusUI:Remove()
```

---

### Start the UI with `:Start()`

❓ Required to dispaly the UI.

⚠️ No returned values.

⚠️ No parameters.

**Example:**
```lua
ArceusUI:Start()
```

---

# All credits to:
**Riky47#3355** for https://spdmteam.com/
