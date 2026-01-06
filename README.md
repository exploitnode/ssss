# ==============================
# Configuration
# ==============================
$imageUrl  = "https://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webp"
$imagePath = "$env:USERPROFILE\Pictures\wallpaper.jpg"

# ==============================
# Download image
# ==============================
Invoke-WebRequest -Uri $imageUrl -OutFile $imagePath -UseBasicParsing

# ==============================
# Set wallpaper (Windows API)
# ==============================
Add-Type @"
using System;
using System.Runtime.InteropServices;

public class Wallpaper {
    [DllImport("user32.dll", SetLastError = true)]
    public static extern bool SystemParametersInfo(
        int uAction,
        int uParam,
        string lpvParam,
        int fuWinIni
    );
}
"@

# SPI_SETDESKWALLPAPER = 20
# SPIF_UPDATEINIFILE = 0x01
# SPIF_SENDCHANGE = 0x02
[Wallpaper]::SystemParametersInfo(20, 0, $imagePath, 0x01 -bor 0x02) | Out-Null
