<div align="center">
<img src="Icon.png" alt="cubismSecurity.png" width=200></img>
<h1></h1>
Anti-Tamper software built into Roblox Game.
</div>

> [!NOTE]
> Cubism Security is under development and may not be stable!

# Demo

## Example Usage
```lua
local cubismSecurity = require(path.to.module)
local Client, Server = cubismSecurity.Client, cubismSecurity.Server

Client._promiseThread:await()
Server._promiseThread:await()

Server.ClientProtocolFailure:Connect(function(player: Player, ConnectionError: Enum.ConnectionError?, ...)
	warn(player, ConnectionError, ...)
end)

Players.PlayerAdded:Connect(function(player: Player)
	print(Client.CreateUserClient(player))
end)
```

## License
cubismSecurity is available under the MIT license. See [LICENSE](LICENSE) for details.
