# super_awesome



-- showing bandwidth and catch system
https://www.youtube.com/watch?v=tV_y0w52LPI 

-- showing full lobby bandwidth, weapon skills, equipping pokemon, server error logs
https://www.youtube.com/watch?v=Yv_D01sGH78

-- game link
https://www.roblox.com/games/12790940908


# Check It Out
Press this to add 
  - 1 of every weapon.
  - 100 master balls
  - 10k gold and 10k silver

![get_abmin_inv](https://github.com/user-attachments/assets/a1ea6b45-ccd5-4f38-a6d5-51c6fc9af132)


# Ad Manager Data
Overall bad. About 3-5 minutes average playtime. 
It does have good parts but its extremely difficult to believe you will think its photoshop. Please dm I’d love to just screen share and show you.


# Error Reports
None but failed to load sound ids

# Bandwidth
For reference, single-full lobbies
Jailbreak and Strongest Battlegrounds are 10-60kB/s
mine is 5-50kB/s



![my_bandwidth](https://github.com/user-attachments/assets/385436fe-a9d8-4792-b227-9128b389d8ee)


CTRL + F7 to show those


# Event Type

“RemoteEvents” are TCP and will try to re-fire over the span of 300 ms. It took me a while to decide when to use “UnreliableRemoteEvents”. Those are UDP and my system uses those them only when firing often-rubberbanding-events. Like LMB attack or skill charges where timing is required. So if the client has bad internet connection, it wont try to re-fire.



# Asset ID
I know exactly which asset ids were not uploaded by my account. I forked open source plugins specifically for the development of my game.  

https://github.com/user-attachments/assets/8b25eb6a-b0fd-4246-b4c4-204fb913a067

```

--[[
select it. it glare over the children and anything that is NOT uploaded by you will be flagged
--]]

local _you = {
	["Myukov"] = true, -- me
	["Clazite_VFX"] = true,
	["Ieeandre"] = true,
	["Yuruzuu"] = true,
	["Midori8972"] = true,
	["eduardobrg"] = true,
	["Roblox"] = true,
	["nosekuya"] = true
}

local TLDR = {}
local _TLDR = false
local Selection = game:GetService("Selection")
--local ChangeHistoryService = game:GetService("ChangeHistoryService")
local MarketplaceService = game:GetService("MarketplaceService")

local function GetTextureData(b)
	local texture = (b:split("rbxassetid://")[2])
	if texture == nil then
		texture = b:split("http://www.roblox.com/asset/?id=")[2]
	end
	local a = MarketplaceService:GetProductInfo(tonumber(texture))
	return a.Creator.Name
end
local function TryIt(obj, masterparentname)
	if obj:IsA("ParticleEmitter") then
		--task.spawn(function()
		if obj.Texture == "" then
			warn("empty")
		else
			local namu = GetTextureData(obj.Texture)
			if _you[namu] == nil then
				print("not you!", namu)
				TLDR[namu] = true
				_TLDR = true
				print("sus...\n  ", masterparentname, "/", obj.Parent.Parent.Parent.Name, "/", obj.Parent.Parent.Name,"/",  obj.Parent.Name,"/" , obj.Name)
			end
		end
		--end)
	end
end

local mouseSelect = Selection:Get()
if #mouseSelect > 0 then
	for i = 1, #mouseSelect do
		TryIt(mouseSelect[i])
		local descendantSelection = mouseSelect[i]:GetDescendants()
		if descendantSelection then

			for ii =1, #descendantSelection do
				TryIt(descendantSelection[ii])
			end
		end
	end
else
	print("not selected error - 4858")
end

if _TLDR then
	local x = "tldr : "
	for s, _ in pairs(TLDR) do
		x = x .. "," .. s
	end
	warn(x)
else
	print("safe !")
end
print("Finished id select scan")

--ChangeHistoryService:SetWaypoint("x")
```

# asset packs and other credits

https://pixabay.com/sound-effects/energy-3-107098/
https://assetstore.unity.com/packages/audio/sound-fx/weapons/weapon-sounds-weapon-swings-sfx-pack-154537
https://assetstore.unity.com/packages/audio/sound-fx/sword-medieval-swords-sound-effects-pack-249315 

https://devforum.roblox.com/t/free-synty-asset-packs-released-in-the-marketplace/1283755

https://assetstore.unity.com/packages/audio/sound-fx/melee-attack-magic-spells-sound-effects-and-music-pack-224922
https://assetstore.unity.com/packages/3d/characters/creatures/rpg-monster-bundle-pbr-260493
https://assetstore.unity.com/packages/audio/sound-fx/anime-sci-fi-sound-effects-pack-aaa-268616

https://elvgames.itch.io/magic-wizardry-4-rpg-music

https://pixabay.com/sound-effects/splash-6213/
https://pixabay.com/sound-effects/water-splash-199583/

https://pixabay.com/music/world-arabic-desert-196240/ 1
https://pixabay.com/music/trap-explore-japan-199943/
https://pixabay.com/music/ambient-medieval-abbey-182197/
https://pixabay.com/music/main-title-pirate-tavern-full-version-167990/
https://pixabay.com/music/main-title-calm-fantasy-harp-and-strings-197736/



