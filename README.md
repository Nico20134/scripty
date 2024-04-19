-- Check game
if game.PlaceId == 12996550309 then
    local CurrentVersion = "Runstars script - annoymous0ws V1"

    -- Call the library
    local Mercury = loadstring(game:HttpGet("https://raw.githubusercontent.com/deeeity/mercury-lib/master/src.lua"))()

    -- Main Frame
    local GUI = Mercury:Create{
        Name = "urrentVersion,
        Size = UDim2.fromOffset(600, 400),
        Theme = Mercury.Themes.Dark,
        Link = "https://github.com/deeeity/mercury-lib"
    }

    -- Local var
    local isFarmingWins = false
    local SelectTreadmillValue = nil
    local isFarmingTread

    -- local lists
    local TreadList = {
        -- World 1ioio
        ["+1/s Treadmill"] = "1",
        ["+5/s Treadmill"] = "2",
        ["+10/s Treadmill"] = "3",
        ["+20/s Treadmill"] = "4",
        ["+25/s Treadmill"] = "5",
        ["+30/s Treadmill"] = "6",
        -- world 2
        ["+40/s Treadmill"] = "8",
        ["+60/s Treadmill"] = "9",
        ["+80/s Treadmill"] = "10",
        ["+100/s Treadmill"] = "11",
        ["+150/s Treadmill"] = "12",
        ["+200/s Treadmill"] = "13",
        -- world 3
        ["+1000/s Treadmill"] = "15",
        ["+1400/s Treadmill"] = "16",
        ["+1800/s Treadmill"] = "17",
        ["+2200/s Treadmill"] = "18",
        ["+2600/s Treadmill"] = "19",
        ["+3000/s Treadmill"] = "20",
        -- vip
        ["+30/s VIP Treadmill"] = "7",
        ["+129/s VIP Treadmill"] = "14",
        ["+2000/s VIP Treadmill"] = "21",
    }

    -- FarmTab creation
    local FarmTab= GUI:Tab{
        Name = "Auto Farm"
        Icon = "rbxassetid://2047155756"
    }
    
    local infWinsLabel= FarmTab:Label{
        Text = "",
        Description = "You must have the treadmill unlocked " .."\nif the farm doesnt work enterthe treadmill manually then leave the treadmill and try again"
    }


    FarmTab:Dropdown{
        Name = "Sellect Treadmill",
        StartingText = "Select...",
        Description = "IT has to be an unlocked treadmill",
        Items = {
            "WORLD 1 (PLACEHOLDER DONT SELLECT)",
            "+1/s Treadmill",
            "+5/s Treadmill",
            "+10/s Treadmill",
            "+20/s Treadmill",
            "+25/s Treadmill",
            "+30/s Treadmill",
            "WORLD 2 (PLACEHOLDER DONT SELLECT)",
            "+40/s Treadmill",
            "+60/s Treadmill",
            "+80/s Treadmill",
            "+100/s Treadmill",
            "+150/s Treadmill",
            "+200/s Treadmill",
            "WORLD 3 (PLACEHOLDER DONT SELLECT)",
            "1000/s Treadmill",
            "1400/s Treadmill",
            "1800/s Treadmill",
            "2200/s Treadmill",
            "2600/s Treadmill",
            "3000/s Treadmill",
            "VIP TREADS (PLACEHOLDER DONT SELLECT | MUST HAVE GAMEPASS)",
            "+30/s VIP Treadmill",
            "+120/s VIP Treadmill",
            "+2000/s VIP Treadmill",   
        },
        Callback = function(item)
        SelectedTreadmillValue = TreadList[item]
        print("Selected:".. SelectedTreadmillValue)
        end
    }

    FarmTab:Toggle{
        Name = "Start Farming",
        StartingState = false,
        Description = "Farms the selected treadmill",
        Callback = function(state) 
        isFarmingTread = state
        while isFarmingTread do
        if SelectedTreadmillValue then
            local args = {
                [1] = SelectedTreadmillValue,
            }
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Train"):WaitForChild("AddSpeed"):FireServer(unpack(args))
        end
        wait()
        end
    end
    }

    local infWinsLabel = FarmTab:Label{
        Text = "inf Wins Warning:",
        Description = "Only use the method from your world ⬇ Scroll down ⬇"
    }

    FarmTab:Toggle{
        Name = "INF WINS",
        StartingState = false,
        Description = "World 1",
        Callback = function(state) 
        isFarmingWins = state
        while isFarmingWins do
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Race"):WaitForChild("RacePrepare"):InvokeServer()
        wait()
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Race"):WaitForChild("RaceStart"):InvokeServer()
        wait()
        local args = {
            [1] = 1
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Race"):WaitForChild("RaceStart"):InvokeServer()
        wait()
        local args= {
            [1] = true
            [2] = 1,
            [3] = 1,
        }

        game:GetService("ReplicatedStorage").Remotes.Race.RaceRewards:FireServer(unpack(args))
        wait()

        end

    end
    }
    FarmTab:Toggle{
        Name = "INF WINS",
        StartingState = false,
        Description = "World 2",
        Callback = function(state) 
        isFarmingWins = state
        while isFarmingWins do
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Race"):WaitForChild("RacePrepare"):InvokeServer()
        wait()
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Race"):WaitForChild("RaceStart"):InvokeServer()
        wait()
        local args = {
            [1] = 1
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Race"):WaitForChild("RaceStart"):InvokeServer()
        wait()
        local args= {
            [1] = true
            [2] = 2,
            [3] = 1,
        }

        game:GetService("ReplicatedStorage").Remotes.Race.RaceRewards:FireServer(unpack(args))
        wait()

        end

    end
    }
    FarmTab:Toggle{
        Name = "INF WINS",
        StartingState = false,
        Description = "World 3",
        Callback = function(state) 
        isFarmingWins = state
        while isFarmingWins do
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Race"):WaitForChild("RacePrepare"):InvokeServer()
        wait()
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Race"):WaitForChild("RaceStart"):InvokeServer()
        wait()
        local args = {
            [1] = 1
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Race"):WaitForChild("RaceStart"):InvokeServer()
        wait()
        local args= {
            [1] = true
            [2] = 3,
            [3] = 1,
        }

        game:GetService("ReplicatedStorage").Remotes.Race.RaceRewards:FireServer(unpack(args))
        wait()

        end

    end
    }


end
