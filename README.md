README.txt — Cleaner Module
===========================

🎯 Purpose:
-----------
Cleaner is a Luau module designed to help manage and clean up resources in Roblox projects.  
It lets you track and remove:
- Custom variables
- Event connections
- Roblox instances

📦 Installation:
----------------
1. Place `Cleaner.lua` in your Modules folder (e.g., ReplicatedStorage).
2. Load the module using: `local Cleaner = require(path.To.Cleaner)`
3. Create a cleaner object: `local cleaner = Cleaner.new()`

🛠️ Main Functions:
------------------
• AddVariable(name, value)       → Add a custom variable  
• SetVariable(name, value)       → Update an existing variable  
• GetVariable(name)              → Retrieve a variable’s value  
• Clean()                        → Clear all stored variables  

• AddConnection(name, connection) → Store a connection (e.g., from :Connect())  
• Disconnect(name?)              → Remove a specific or all connections  

• AddInstance(instance, name?)   → Add a Roblox Instance to track  
• Destroy(name?)                 → Destroy a specific or all stored instances  

• CleanUp()                      → Global cleanup: variables, connections, and instances

📌 Quick Example:
------------------
local cleaner = Cleaner.new()

-- Variables
cleaner:AddVariable("Username", "Copilot")

-- Connections
local conn = part.Touched:Connect(function()
    print("Touched!")
end)
cleaner:AddConnection("TouchConn", conn)

-- Instances
local gui = Instance.new("ScreenGui", player.PlayerGui)
cleaner:AddInstance(gui, "MainGui")

-- Cleanup
cleaner:CleanUp()

👤 Author:
----------
Built by flashy3467dieux  


🧼 Cleaner is efficient, readable, and easy to integrate into any Roblox project.
