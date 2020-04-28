Rush Setup Guide – By Coomzy
1.	Download the latest rush version from https://github.com/Coomzy/Pavlov-Rush
2.	Open the downloaded project
3.	In the content browser right click and Migrate the rush UGC folder to your project’s content folder
4.	Close the rush project and open your rush map project
5.	Move the RSH folder to the UGC folder of your project
6.	Fix up redirectors in migrated UGC folder
7.	Move PMF folder across to the UGC folder
8.	Fix up redirectors in migrated UGC folder
9.	Delete previous GameLogic in level if there is one
10.	Inside your UGC folder right click on the content browser and click Blueprint Class, expand All Classes and type “RSH_GameLogic”
11.	Select RSH_GameLogic and then click the Select button
12.	Drag your newly create RSH_GameLogic child into the level select it in the World Outliner and click “Spawn CORE Actors” in the Setup category in the Details panel
13.	Link your definition to your GameLogic under the details pannel
14.	Put your Map Name in the Config – Map category (On the RSH_GameLogic child in level)
15.	In the Config – Admin category add any roled players (admin = 1)  to the PlayerRoleList and any blacklisted players to the PlayerBlacklist variable (add their SteamID’s in the boxes on the RSH_GameLogic child in level) You can find steam ID here: https://steamidfinder.com/ 
16.	Go to \CustomMaps\#YOUR UGC#\RSH\Blueprints\LevelActors and place RSH_MCOM in the areas you want MCOM stations, make sure to set their MCOM Index’s accordingly (A = 0, B = 1, etc.) and use MCOMManager’s “Check for Errors” button on the Details panel for troubleshooting
17.	Next place RSH_BattlefieldPlacement’s where you want attacking and defend to be able to spawn during a given set of objectives (specific attacking and defend spawns in step 19)
18.	Add the actor ‘RSH_MCOMGroup‘ to your level as many times as you have grouped objectives (if you had A&B then C&D that would be two, one for each group)
19.	For each group populate the three config fields as needed, Battlefield Placements (spawns when this is the active group of objectives), MCOMs (the actual MCOMs used for this group) and Return To Battlefield (This is technically optional but this is the bounds to stop players going out the map)
20.	Select RSH_MCOMManager in the World Outliner and in the Details panel under the Config – RSH category add all your RSH_MCOMGroup actors (in the order you want them to be activated)
21.	Next we need to do the role rooms, first off you need player spawns, doesn’t really matter how many as it’s the role room so not a big deal if people spawn on top of each other but you use the RSH_PlayerSpawn blueprint in the \CustomMaps\#YOUR UGC#\RSH\Blueprints\LevelActors folder to do this
22.	Set the variable on the spawn for the right team team
23.	Next in the role room place the RSH_RoleTeleport’s if you are using the preset roles (Solider, Sniper, Support, Commando) the go into the RoleTeleportPresets and place one of each
24.	Each RoleTeleporter needs a TeleportPoint so just place an empty actor where you want players to be teleported to and link the reference in the Details panel.
25.	In each Armory place a RSH_BattlefieldTeleporter, RSH_RoleRoomReturner & any weapon spawns you want for that armoury (you can use the regular Pavlov one or the PMF_LootSpawnerProxy one which has an enum list for items so you don’t need to know the names)
26.	I’d also recommend placing a PMF_ShotBlocker over the Armory’s as players will probably troll and just constantly shoot, you are invincible and don’t lose respawn tickets for dying in the armoury so this isn’t a major issue
27.	Make sure you do steps 19-22 for both sides
28.	Place a PMF_MapEntrySpawn in the level where you want players to spawn as a spectator when the match hasn’t started yet
29.	Look at the RSH_Test folder for examples on how to set stuff up and feel free to delete it.
