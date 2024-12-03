<div align="center">
<img src="icon.png" alt="cubismSecurity.png" width=200></img>
<h1></h1>
Anti-Tamper software built into <a href="https://www.roblox.com">Roblox<a/> Game.
</div>

> [!WARNING]
> Cubism Security is under development and may not be stable!

[![License](https://img.shields.io/badge/License-Apache%202.0-red.svg)](https://github.com/cubismia/cubismSecurity/blob/main/LICENSE)
[![Release](https://img.shields.io/badge/version-0.2.1-blue)](https://github.com/cubismia/cubismSecurity/releases/tag/v0.2.1)
[![Language](https://img.shields.io/badge/language-Luau-blue.svg)](https://luau.org)

## Get Started
https://www.roblox.com/games/17447723961/testez-cubismSecurity

##
```luau
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
