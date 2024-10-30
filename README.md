<div align="center">
<img src="Icon.png" alt="cubismSecurity.png" width=200></img>
<h1></h1>
Anti-Tamper software built into <a href="https://www.roblox.com">Roblox<a/> Game.
</div>

> [!NOTE]
> Cubism Security is under development and may not be stable!

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/cubismia/cubismSecurity/LICENSE)
[![Release](https://img.shields.io/badge/version-0.2.1-blue)](https://github.com/cubismia/cubismSecurity/releases/tag/v0.2.1)

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
Cubism Security is available under the Apache 2.0 license. See [LICENSE](LICENSE) for details.
