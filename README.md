# gpm2spotify
Google Play Music to Spotify Library Migrator

Something I made in a couple of hours to celebrate Spotify's launch in India. The script is able to Migrate GPM library to Spotify. After scouring through nearly half of the internet, the seemingly reliable ways to migrate your library from GPM to Spotify either took $$$ or Credentials to the services I hold near and dear, both of which were a total no go for me anyway. So I quickly cooked up literally the first things I've ever written in python. I don't intend to maintain or update this since it has already served my purpose. But I wouldn't mind doing minor tweaks for a fellow music lover.

# What do these scripts actually do?

These scripts use wrappers for Spotify and GPM Web APIs to access and modify your libraries. 

gpm.py fetches your GPM library and Stores it in a file. spotify.py reads this file, searches for that track on spotify and adds it to your library and a playlist of your liking. To enable this to work you have to register a new App on Spotify developer account and use it to access Spotify web APIs 

All credits to creators of who made the amazing libraries which even made it possible for me to do something like this 

Spotipy [https://spotipy.readthedocs.io/en/latest/]

GMusicApi [https://unofficial-google-music-api.readthedocs.io/en/latest/]

# Instructions

## Download and Install Python and required libraries
a. Select Add Python 3.7 to Path Option 
b. Select Install Now
c. Close the installer
d. Open powershell/terminal and enter following command 
```
python3 -V
```
e. Update pip3 and install libraries
```
python3 -m pip3 install --upgrade pip
pip3 install spotipy gmusicapi
```

## Register a Spotify API client
a. Goto https://developer.spotify.com/dashboard/
b. Log In
c. Accept Developer Terms
d. Create ClientId
e. Input a Name and Description for your app (I Used GPM2Spotify)
g. Accept Terms
h. Edit Setings
i. Add "http://localhost:8080/" to the Redirect URI and click "Add"
j. Copy ClientId and ClientSecret to Config.txt
k. Goto "https://www.spotify.com/in/account/overview/" Copy Username to Config.txt

## Execution    
a. Execute `python3 gpm.py` and follow instructions. This should create a file GPMLibraryParsed.txt containing Your GPM library with eachline describing [Artist Song Title]
b. Execute `python3 spotify.py` and fill in the prompt with the playlist id as shown below:

    ```
    Enter Playlist URL : spotify:playlist:40BcMwHSJljfKTSUGkTLqb
    ```

This will import all songs from GPMLibraryParsed.txt, by looking up each song on Spotify and add the ones it finds to your playlist.
That's it. Sit back and enjoy your library being populated! Yay!
