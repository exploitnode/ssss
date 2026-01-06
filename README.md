[# ssss](https://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webphttps://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webphttps://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webphttps://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webphttps://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webp\

# Replace this with your direct image URL
$url = "https://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webphttps://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webphttps://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webphttps://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webphttps://assetsio.gnwcdn.com/poznanie-panam-pasazer.jpg?width=2048&height=2048&fit=bounds&quality=85&format=jpg&auto=webp\"

# Where to save the image
$path = "$env:USERPROFILE\Pictures\wallpaper.jpg"

# Download the image
Invoke-WebRequest -Uri $url -OutFile $path

# Set wallpaper registry values
Set-ItemProperty -Path "HKCU:\Control Panel\Desktop" -Name Wallpaper -Value $path
Set-ItemProperty -Path "HKCU:\Control Panel\Desktop" -Name WallpaperStyle -Value 10  # Fill
Set-ItemProperty -Path "HKCU:\Control Panel\Desktop" -Name TileWallpaper -Value 0

# Apply the wallpaper
rundll32.exe user32.dll, UpdatePerUserSystemParameters
)
