# UE4.27 EOSPlus Project Testing
 
## Notes:
- For crossplay between EOS and another platform, perform default steps for setting up [EOS and EOS Plus](https://docs.unrealengine.com/4.27/en-US/ProgrammingAndScripting/Online/EOS/) and, in this case [Steam](https://docs.unrealengine.com/4.27/en-US/ProgrammingAndScripting/Online/Steam/).
Then, remove NetDriverDefinition for Steam. All sessions/lobbies will be handled through EOS and mirrored to Steam (Assuming you enabled EOSPlus features in Project Settings)
- [VoiceChat](https://docs.unrealengine.com/4.27/en-US/ProgrammingAndScripting/Online/EOS/#eosvoicecommunications_1) can easily be added while using lobbies API. Simply set bUseLobbiesVoiceChatIfAvailable to true (Found in FOnlineSessionSettings)
- Using the AutoLogin function and setting Type to ['accountportal'](https://github.com/EpicGames/UnrealEngine/blob/d94b38ae3446da52224bedd2568c078f828b4039/Engine/Plugins/Online/OnlineSubsystemEOS/Source/OnlineSubsystemEOS/Private/UserManagerEOS.cpp#L378) while using EOS will open a browser to login the user
- Lobbies / Sessions can be linked to how Fortnite handles Friend Parties (Menu section) and Game Sessions (Actually playing game). One or the other can be used in simple situations.
- Creating sessions is possible using built-in functions and C++ but [AdvancedSessions](https://github.com/mordentral/AdvancedSessionsPlugin) provides more options for BP users.
- Finding dedicated servers seems jank right now. The solution is to not enter query filters, like "SEARCH_DEDICATED_ONLY", "SEARCH_PRESENCE", or "SEARCH_LOBBIES"
- Dedicated servers cant have presence enabled since it requires a logged in user. How do players host dedicated servers? How to solve friends not being able to join through presence?