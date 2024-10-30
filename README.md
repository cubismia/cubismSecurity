<div align="center">
<img src="Icon.png" alt="cubismSecurity.png" width=200></img>
<h1></h1>
Anti-Tamper software built into <a href="https://www.roblox.com">Roblox<a/> Game.
</div>

> [!NOTE]
> Cubism Security is under development and may not be stable!

# Demo
https://www.roblox.com/games/17447723961/testez-cubismSecurity

## Example Usage
```lua
--!strict
local cubismSecurity = require(path.to.module)
local Client, Server = cubismSecurity.Client, cubismSecurity.Server

-- # waiting for loading to prevent unexpected problems
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
