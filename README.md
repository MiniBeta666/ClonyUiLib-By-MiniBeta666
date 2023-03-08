# ClonyUiLib-By-MiniBeta666
## Booting Ui
```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/MiniBeta666/ClonyUiLib-By-MiniBeta666/main/ClonyUiLib.source", true))()
```
## Create Window
```lua
local Library = Update:Window("Clony","",Enum.KeyCode.RightControl);
```
## Create Tab
```lua
Main = Library:Tab("Main")
```
## Create Line
```lua
Main:Line()
```
## Create Label
```lua
Main:Label("Example Label")
--<TabName>, string --<LabelSource>, string
```
## Execute Time
```lua
local Time = Main:Label("Executor Time");spawn(function() getgenv().Time = true;while true do wait(.1) UpdateTime() end end);function UpdateTime() local date = os.date("*t");local hour = (date.hour) % 24;local ampm = hour < 12 and "AM" or "PM";local timezone = string.format("%02i:%02i:%02i %s", ((hour -1) % 12) + 1, date.min, date.sec, ampm);local datetime = string.format("%02d/%02d/%04d", date.day, date.month, date.year);local LocalizationService = game:GetService("LocalizationService");local Players = game:GetService("Players");local player = Players.LocalPlayer;local name = player.Name;local result, code = pcall(function()   return LocalizationService:GetCountryRegionForPlayerAsync(player)  end);Time:Set(" : " .. timezone);Time:Set("Executor Time: " .. datetime .. " [ " .. code .. " ]");spawn(function() if getgenv().Time then pcall(function()  while wait() do  Time()  end end) end end) end
```
## Create Seperator
```lua
Main:Seperator("Seperator")
```
## Create Button
```lua
Main:Button("Button",function()
	print("Button")
end)

```
## Create Toggle
```lua
Main:Toggle("Toggle",false,function(value)
	print(value)
end)

```
## Create Dropdown
```lua
local Choice = {
 "1",
 "2",
 "3"
}

local Dropdown = Main:Dropdown("Dropdown",Choice,function(value)
	print(value)
end)
```
## Refresh Dropdown
```lua
Main:Button("Refresh Dropdown",function()
	Dropdown:Clear()
	Dropdown:Add(Choice)
end)
```
## Create Slider
```lua
Main:Slider("Slider",1,100,10,function(value)
	print(value)
end)

```
## Create Textbox
```lua
Main:Textbox("Textbox",true,function(value)
    print(value)
end)

```




