# Forkert opløsning i TTY og greeter
## TTY
Min Samsung G9 OLED startede op forkert ved 3840x1080 i stedet for den korrekte 5120x1440 opløsning. Dette giver trælse "sorte skærme" ved login og ved skift til en TTY konsol med ctrl+alt+f[3-7]

Løsningen var en kernel parameter: 
>video:DP-1:5120x1440x120

Fandt denne løsning her: https://wiki.archlinux.org/title/Kernel_mode_setting#Forcing_modes

## GDM
Kopierede Gnome's monitors.xml til GDM. Dette virkede ikke. Problemet viste sig at være at jeg havde slået VRR til i Gnome. 

Dette er en experimentiel indstilling som skulle slåes til med:

> gsettings set org.gnome.mutter experimental-features "['variable-refresh-rate']"

Dette skulle også gøres i GDM ved at starte en bash shell med:

> machinectl shell gdm@ /bin/bash

*https://www.reddit.com/r/gnome/comments/1d4nbp6/comment/lbt5jlx/*
