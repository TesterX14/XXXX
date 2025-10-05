local Chloex = loadstring(game:HttpGet("https://raw.githubusercontent.com/TesterX14/XXXX/refs/heads/main/Library"))()

local Window = Chloex:Window({
    Title   = "Chloe X |",
    Footer  = "Example",
    Image   = "132435516080103",
    Color   = Color3.fromRGB(0, 208, 255),
    Theme   = 9542022979,
    Version = 2,
})

if Window then
    chloex("Window loaded!")
end

-- Tab
local ExampleTab = Window:AddTab({
    Name = "Example",
    Icon = "scan"
})

-- Section
local Example = ExampleTab:AddSection("Section Example", true)

-- Paragraph
Example:AddParagraph({
    Title = "Chloe X Alert!",
    Content = [[
This script is still under development!
There is a possibility it may get detected if used in public servers!
If you have suggestions or found bugs, please report them to <font color="rgb(0,170,255)">Discord Chloe X</font>!<br/>
<b>Use at your own risk!</b>
]],
    Icon = "water"
})


Example:AddParagraph({
    Title = "CHLOE X Discord",
    Content = "Official link discord Chloe X!",
    Icon = "discord",
    ButtonText = "COPY LINK DISCORD",
    ButtonCallback = function()
        if setclipboard then
            setclipboard("https://discord.gg/J5KdfSHD")
            chloex("Succesfully copied link!")
        end
    end
})

Example:AddDivider()

local Players = game:GetService("Players")
local TeleportService = game:GetService("TeleportService")
local LocalPlayer = Players.LocalPlayer

local thumb, _ = Players:GetUserThumbnailAsync(
    LocalPlayer.UserId,
    Enum.ThumbnailType.HeadShot,
    Enum.ThumbnailSize.Size100x100
)

local currentJobId = "CHX-" .. tostring(game.JobId)

Example:AddParagraph({
    Title = "JobID Server",
    Content = currentJobId,
    Icon = thumb,
    ButtonText = "Copy JobID",
    ButtonCallback = function()
        if setclipboard then
            setclipboard(currentJobId)
            chloex("Succesfully Copied!")
        end
    end
})

local InputJobId = ""
Example:AddInput({
    Title = "Input JobID",
    Default = "",
    Callback = function(value)
        InputJobId = value
    end
})

Example:AddButton({
    Title = "Join JobID",
    Callback = function()
        if InputJobId ~= "" then
            local realJobId = InputJobId:gsub("^CHX%-", "")
            TeleportService:TeleportToPlaceInstance(game.PlaceId, realJobId, LocalPlayer)
        else
            chloex("Input Job Id!")
        end
    end
})

-- 1. Lengkap (Input + 2 Button)
Example:AddPanel({
    Title = "JobID Server",
    Content = "Masukkan JobID target",
    Placeholder = "Input JobID",
    Button = "Copy JobID", -- tombol kiri
    Callback = function(text)
        if setclipboard then
            setclipboard(text)
            print("JobID dicopy:", text)
        else
            warn("Clipboard tidak tersedia")
        end
    end,
    SubButton = "Join JobID", -- tombol kanan
    SubCallback = function(text)
        if text and text ~= "" then
            local TeleportService = game:GetService("TeleportService")
            local Players = game:GetService("Players")
            local PlaceId = game.PlaceId

            print("Mencoba join ke JobID:", text)
            TeleportService:TeleportToPlaceInstance(PlaceId, text, Players.LocalPlayer)
        else
            warn("JobID kosong, tidak bisa join")
        end
    end
})


-- 2. Input + 1 Button
Example:AddPanel({
    Title = "Change Name",
    Content = "Masukkan nama baru",
    Placeholder = "Input nama",
    ButtonText = "Save",
    ButtonCallback = function(text)
        print("Nama diganti jadi:", text)
    end
})

-- 3. 2 Button aja (tanpa input)
Example:AddPanel({
    Title = "Server Control",
    Content = "Pilih aksi server",
    ButtonText = "Restart",
    ButtonCallback = function()
        print("Server di-restart")
    end,
    SubButtonText = "Shutdown",
    SubButtonCallback = function()
        print("Server dimatikan")
    end
})

-- 4. 1 Button aja (tanpa input)
Example:AddPanel({
    Title = "Teleport",
    Content = "Klik untuk teleport ke Lobby",
    ButtonText = "Teleport",
    ButtonCallback = function()
        print("Teleport ke Lobby")
    end
})

-- 5. Input aja (tanpa button)
Example:AddPanel({
    Title = "Note",
    Content = "Catatan pribadi",
    Placeholder = "Tulis sesuatu...",
    Default = ""
})
