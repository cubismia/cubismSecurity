# Cubism Security
Cubism Security is Anti-Tamper software built into Roblox Game as part of countering exploiting on Roblox.

## Example Usage
```lua
--!strict
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")

local cubismSecurity = require(path.to.module)
local Client, Server = cubismSecurity.Client, cubismSecurity.Server

local LuaEncode = require(script.LuaEncode)
local LuaEncodeOptions = {
	Pretiffy = true
}

Client._promiseThread:await()
Server._promiseThread:await()
print(`Loader: RunState.{
	RunService:IsStudio() and "Studio" or "Server"
}`)

Server.ClientProtocolFailure:Connect(function(player: Player, ConnectionError: Enum.ConnectionError, ...)
	warn(player, ConnectionError, type(...) == "table" and LuaEncode(..., LuaEncodeOptions) or ...)
end)

Server.ClientReplicatorConnectionLoaded:Connect(function(player: Player, timeOut: number)
	print(Client.GetUserClient(player), `TimeOut: {timeOut}`)
end)

for _, player: Player in ipairs(Players:GetPlayers()) do
	task.spawn(Client.CreateUserClient, player)
end

Players.PlayerAdded:Connect(Client.CreateUserClient)
```
