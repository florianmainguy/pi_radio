# Pi Radio

Internet Radio for Raspberry PI, with MPD / Adafruit LCD Plate / Python.<br>
Based on [this project](http://www.instructables.com/id/Raspberry-Pi-Internet-Radio/)<br>
<br>
Modified to get BBC 6 Music straight on when raspberry pi turned on, and includes following radio station:
<ul>
<li>BBC 1</li>
<li>BBC 1 Extra</li>
<li>BBC 2</li>
<li>BBC 3</li>
<li>BBC 4</li>
<li>BBC 4 Extra</li>
<li>BBC 5 Live</li>
<li>BBC 5 Live Sports Extra</li>
<li>BBC 6 Music</li>
</ul>

## Instructions

To start with setup Media Player (Mpd) with the following commands:<br>
<code>
sudo apt-get install mpd mpc git 
sudo service mpd start
</code>

Download the script and install it:
<code>
git clone https://github.com/florianmainguy/pi_radio.git
</code>

Install some other things:
<code>
sudo apt-get install python-smbus
sudo apt-get install python-serial python-imaging python-unidecode
sudo cp initradio.sh /etc/init.d/radio 
sudo update-rc.d radio defaults service 
</code>

We need to update the playlist address to do this:
<code>
sudo nano //etc/mpd.conf
</code>

playlist_directory "/var/lib/mpd/playlists"
To:
playlist_directory "/home/pi/radio/playlists”<br>

Press Control O to save followed by Control X to exit.<br>

<code>
sudo service radio start
</code>