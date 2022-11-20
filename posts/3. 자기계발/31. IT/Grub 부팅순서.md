![[Pasted image 20221014170000.png]]
sudo nano /etc/default/grub


GRUB_DEFAULT=0 (이부분 수정)

GRUB_TIMEOUT=10 (이부분 수정)

save 후 sudo update-grub



Check Kodi tonight. I think, that could be your solution.

When i install Batocera for the first time Alsamixer shows my Sound-Device as muted, too.

After i get into Kodi and select the correct Audio Device for Kodi, Alsamixer shows it unmuted and the only thing to do then, is to select the same audio device in Batocera sound options too.

Kodi does something that Batocera does not.

To unmute devices in Alsamixer you should press "," on the device as far as i remember. But since i know these Kodi-trick i have never used alsamixer again.