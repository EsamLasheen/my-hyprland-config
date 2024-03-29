# My Hyprland Config

<details>
<summary>العربية</summary>

**ملاحظة:** هذه الإعدادات لا تزال في مرحلة التطوير، وسأقوم بإضافة المزيد من الميزات بصورة مستمرة عندما يتاح لدي وقت أكثر.

### برامج ضرورية
- [Hyprland](https://wiki.hyprland.org/Getting-Started/Installation/)
- [AGS](https://github.com/Aylur/ags/wiki/installation)
- Wofi
- network-manager-applet
- playerctl
- polkit-kde-agent
- ttf-font-awesome-5
- ttf-jetbrains-mono-nerd
- ttf-fantasque-nerd
- qt5ct
- qt6ct
- Dolphin
- brightnessctl
- gammastep
- wl-clipboard
- hyprpicker
- sysstat
- bc
- kitty
- sassc
- systemsettings
- ttf-font-awesome-5
- acpi
- fish
- kde-powerdevil
- [KDE Material You Colors](https://github.com/luisbocanegra/kde-material-you-colors)

### برامج اختيارية
- strawberry
- easyeffects
- nwg-look
- blueman
- telegram-desktop
- discord
- kvantum
- konsole
- firefox

## التثبيت

### تثبيت البرامج لمستخدمي Arch:
```bash
yay -S base-devel strawberry brightnessctl network-manager-applet telegram-desktop wofi konsole blueman ark dolphin ffmpegthumbs playerctl kvantum polkit-kde-agent ttf-font-awesome-5 jq gufw qt5ct tar gammastep wl-clipboard nwg-look-bin visual-studio-code-bin firefox easyeffects hyprpicker discord hyprshot-git bc sysstat kitty sassc systemsettings ttf-font-awesome-5 orchis-theme-git acpi fish kde-material-you-colors plasma5support plasma5-integration plasma-framework5 aylurs-gtk-shell-git ttf-jetbrains-mono-nerd ttf-fantasque-nerd powerdevil
```

**ملاحطة:** إذا كنت تستخدم نظام تشغيل آخر غير أرش فسوف تحتاج إلى تثبيت جميع البرامج الضرورية. قد تختلف الخطوات بناءً على نوع توزيعتك.

#### مثلا:

- بالنسبة للتوزيعات القائمة على **دبيان/أوبونتو**، يمكنك تثبيت البرامج باستخدام ```apt install``` او البحث عن طريق ```apt search hyprland```.
- في **Fedora/RHEL**, استخدم ```dnf install``` او ```yum install```
- بالنسبة لبرامج ادارة الحزم الاخرى، قم بالبحث عن كل برنامج وتثبيته عبر مدير حزم نظامك.

### اعداد الملفات:

	git clone https://github.com/AhmedSaadi0/my-hyprland-config.git

	# عمل نسخة احتياطية لملفاتك الاصلية
	mv ~/.config/hypr/ ~/.config/hypr-old
	mv ~/.config/ags/ ~/.config/ags-old
	mv ~/.config/wofi/ ~/.config/wofi-old
	cp ~/.config/fish/config.fish ~/.config/fish/config.back.fish

	# نسخ الملفات
	cp -r my-hyprland-config ~/.config/hypr
	cp -r ~/.config/hypr/config/ags ~/.config/ags
	cp -r ~/.config/hypr/config/wofi ~/.config/wofi
	cp ~/.config/hypr/config/config.fish ~/.config/fish/config.fish

	# اعداد الصلاحيات للملفات التنفيذية
	sudo chmod +x ~/.config/hypr/scripts/*
	sudo chmod +x ~/.config/ags/scripts/*

	# اعداد بيئة النظام
	sudo cp /etc/environment /etc/environmentOLD
	echo 'QT_QPA_PLATFORMTHEME=qt5ct' | sudo tee -a /etc/environment

	# نسخ ملفات الثيمات
	mkdir ~/.local/share/color-schemes/
	mkdir ~/.config/Kvantum/
	cp -r ~/.config/hypr/config/plasma-colors/* ~/.local/share/color-schemes/
	cp -r ~/.config/hypr/config/kvantum-themes/* ~/.config/Kvantum/
	cp ~/.config/hypr/config/qt5ct.conf ~/.config/qt5ct/
	cp ~/.config/hypr/config/qt6ct.conf ~/.config/qt6ct/

	mkdir ~/.fonts
	cp -r ~/.config/hypr/config/.fonts/* ~/.fonts

	mkdir ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/BeautySolar.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Delight-brown-dark.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Gradient-Dark-Icons.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Infinity-Dark-Icons.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/kora-grey-light-panel.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Magma.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/NeonIcons.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/la-capitaine-icon-theme.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/oomox-aesthetic-dark.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Vivid-Dark-Icons.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Windows11-red-dark.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Zafiro-Nord-Dark-Black.tar.gz -C ~/.local/share/icons

	mkdir ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Cabinet-Light-Orange.tar.gz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Kimi-dark.tar.gz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Nordic-darker-standard-buttons.tar.gz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Orchis-Green-Dark-Compact.tar.gz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Shades-of-purple.tar.xz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Tokyonight-Dark-BL.tar.gz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Dracula.tar.gz -C ~/.themes


### بامكانك تغير خط الجهاز الى 'JF Flat' اذا اردت ان تحصل على نفس الخط الذي لدي


### انشاء كرون تاب لتحسين استخدام البطارية باستخدام قاعدة الشحن 40-80
    VISUAL=/usr/bin/nano crontab -e
    * * * * * ~/.config/hypr/scripts/battery.sh
#### تغيير مسار ملف صوت اشعارات البطارية في الملف `hypr/scripts/battery.sh`
	home_path="/home/ahmed"

### تغيير منطقة الطقس واوقات الصلاة ومراقب سرعة النت
- قم بتغيير الاعدادت من ملف الاعدادات `.configs/ags/modules/settings.js`
```javascript
weather:{
	// provider is 'ar.wttr.in'
	language: 'ar', // Not implemented yot - only arabic is supported
	location: 'sanaa',
	format: 'j1',
},
prayerTimes:{
	// provider is 'api.aladhan.com'
	city: 'sanaa',
	country: 'yemen',
},
hardware: {
	network: {
		rx_path: '/sys/class/net/wlp0s20f3/statistics/tx_bytes',
		tx_path: '/sys/class/net/wlp0s20f3/statistics/tx_bytes',
	},
},
```

### اعداد الثيم التلقائي M3 من قوقل
#### قم بتثبيت [KDE Material You Colors](https://github.com/luisbocanegra/kde-material-you-colors) في نظامك

اذا كنت تستخدم ارش بامكانك تثبيت [KDE Material You Colors](https://github.com/luisbocanegra/kde-material-you-colors) بهذا الامر
```Arch
yay -S kde-material-you-colors
```

- تغيير مسار مجلد الخلفيات في الملف ``` .config/ags/modules/theme/themes.js ```
- ```wallpaper_path: "path/to/folder"```
- ```interval: الوقت_بالملي_ثانية```
```javascript
const dynamicM3Dark = {
    wallpaper_path: `path/to/my/wallpapers`,
	interval: 15 * 60 * 1000,
    ...other_settings
}
const dynamicM3Light = {
    wallpaper_path: `path/to/my/wallpapers`,
	interval: 15 * 60 * 1000,
    ...other_settings
}
```
</details>

<details> 

<summary>English</summary>

**Note:** This configuration is a work in progress, and I will continue to add more features as time permits.

### Required dependencies:
- [Hyprland](https://wiki.hyprland.org/Getting-Started/Installation/)
- [AGS](https://github.com/Aylur/ags/wiki/installation)
- Wofi
- network-manager-applet
- playerctl
- polkit-kde-agent
- ttf-font-awesome-5
- ttf-jetbrains-mono-nerd
- qt5ct
- qt6ct
- Dolphin
- brightnessctl
- gammastep
- wl-clipboard
- hyprpicker
- sysstat
- bc
- kitty
- sassc
- systemsettings
- ttf-font-awesome-5
- acpi
- fish
- kde-powerdevil
- [KDE Material You Colors](https://github.com/luisbocanegra/kde-material-you-colors)

### Optional dependencies:
- strawberry
- easyeffects
- nwg-look
- blueman
- telegram-desktop
- discord
- kvantum
- konsole
- firefox

## Installing:

### Installing dependencies for Arch Users:
```bash
yay -S base-devel strawberry brightnessctl network-manager-applet telegram-desktop wofi konsole blueman ark dolphin ffmpegthumbs playerctl kvantum polkit-kde-agent ttf-font-awesome-5 jq gufw qt5ct tar gammastep wl-clipboard nwg-look-bin visual-studio-code-bin firefox easyeffects hyprpicker discord hyprshot-git bc sysstat kitty sassc systemsettings ttf-font-awesome-5 orchis-theme-git acpi fish kde-material-you-colors plasma5support plasma5-integration plasma-framework5 aylurs-gtk-shell-git ttf-jetbrains-mono-nerd ttf-fantasque-nerd powerdevil
```

**Note:** If you use an operating system other than Arch, you will need to install all required dependencies. The specific steps may vary depending on your distro. 

#### Example:

- For **Debian/Ubuntu-based** systems, you can install dependencies using ```apt install``` or search using ```apt search hyprland```.
- On **Fedora/RHEL**, use ```dnf install``` or ```yum install```
- For other package managers, search for each dependency and install using your system's package manager.

### Setting up files:

	git clone git@github.com:AhmedSaadi0/my-hyprland-config.git

	# backup your files
	mv ~/.config/hypr/ ~/.config/hypr-old
	mv ~/.config/ags/ ~/.config/ags-old
	mv ~/.config/wofi/ ~/.config/wofi-old
	cp ~/.config/fish/config.fish ~/.config/fish/config.back.fish

	# copy files
	cp -r my-hyprland-config ~/.config/hypr
	cp -r ~/.config/hypr/config/ags ~/.config/ags
	cp -r ~/.config/hypr/config/wofi ~/.config/wofi
	cp ~/.config/hypr/config/config.fish ~/.config/fish/config.fish

	# set permissions for scripts
	sudo chmod +x ~/.config/hypr/scripts/*
	sudo chmod +x ~/.config/ags/scripts/*

	# setup environment
	sudo cp /etc/environment /etc/environmentOLD
	echo 'QT_QPA_PLATFORMTHEME=qt5ct' | sudo tee -a /etc/environment

	# copy theme files
   	mkdir ~/.local/share/color-schemes/
	mkdir ~/.config/Kvantum/
	cp -r ~/.config/hypr/config/plasma-colors/* ~/.local/share/color-schemes/
	cp -r ~/.config/hypr/config/kvantum-themes/* ~/.config/Kvantum/
	cp ~/.config/hypr/config/qt5ct.conf ~/.config/qt5ct/
	cp ~/.config/hypr/config/qt6ct.conf ~/.config/qt6ct/

	mkdir ~/.fonts
	cp -r ~/.config/hypr/config/.fonts/* ~/.fonts

	mkdir ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/BeautySolar.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Delight-brown-dark.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Gradient-Dark-Icons.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Infinity-Dark-Icons.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/kora-grey-light-panel.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Magma.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/NeonIcons.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/la-capitaine-icon-theme.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/oomox-aesthetic-dark.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Vivid-Dark-Icons.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Windows11-red-dark.tar.gz -C ~/.local/share/icons
	tar xvf ~/.config/hypr/config/icons/Zafiro-Nord-Dark-Black.tar.gz -C ~/.local/share/icons

	mkdir ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Cabinet-Light-Orange.tar.gz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Kimi-dark.tar.gz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Nordic-darker-standard-buttons.tar.gz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Orchis-Green-Dark-Compact.tar.gz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Shades-of-purple.tar.xz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Tokyonight-Dark-BL.tar.gz -C ~/.themes
	tar xvf ~/.config/hypr/config/gtk-themes/Dracula.tar.gz -C ~/.themes


### You can change system fonts if you want to 'JF Flat' to have the same font I had


### Creating crontab for battery 40-80 rule:
    VISUAL=/usr/bin/nano crontab -e
    * * * * * ~/.config/hypr/scripts/battery.sh
#### Change home path for battery script in `hypr/scripts/battery.sh`
	home_path="/home/ahmed"

### Change weather, prayer times location, and network speed monitors
- From the settings file in `.configs/ags/modules/settings.js`
```javascript
weather:{
	// provider is 'ar.wttr.in'
	language: 'ar', // Not implemented yot - only arabic is supported
	location: 'sanaa',
	format: 'j1',
},
prayerTimes:{
	// provider is 'api.aladhan.com'
	city: 'sanaa',
	country: 'yemen',
},
hardware: {
	network: {
		rx_path: '/sys/class/net/wlp0s20f3/statistics/tx_bytes',
		tx_path: '/sys/class/net/wlp0s20f3/statistics/tx_bytes',
	},
},
```

### Setting up Material 3 theme
- You need to have [KDE Material You Colors](https://github.com/luisbocanegra/kde-material-you-colors) installed on your system

*If you use Arch you can install it from aur*
```Arch
yay -S kde-material-you-colors
```

- Change wallpapers paths for dark & light themes in ``` modules/theme/themes.js ```
- ```wallpaper_path: "path/to/folder"```
- ```interval: time_in_millisecond``` 
```javascript
const dynamicM3Dark = {
    wallpaper_path: `/media/shared/Pictures/wallpapers/dark`,
	interval: 15 * 60 * 1000,
    ...other_settings
}
const dynamicM3Light = {
    wallpaper_path: `/media/shared/Pictures/wallpapers/light`,
	interval: 15 * 60 * 1000,
    ...other_settings
}
```
</details>

# Screenshots - لقطات
<p align='center'>
	<img alt='screenshot 1' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/1.png'/>
</p>
<p align='center'>
	<img alt='screenshot 10' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/10.png'/>
</p>
<p align='center'>
	<img alt='screenshot 2' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/2.png'/>
</p>
<p align='center'>
	<img alt='screenshot 3' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/3.png'/>
</p>
<p align='center'>
	<img alt='screenshot 4' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/4.png'/>
</p>
<p align='center'>
	<img alt='screenshot 5' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/5.png'/>
</p>
<p align='center'>
	<img alt='screenshot 6' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/6.png'/>
</p>
<p align='center'>
	<img alt='screenshot 11' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/11.png'/>
</p>
<p align='center'>
	<img alt='screenshot 7' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/7.png'/>
</p>
<p align='center'>
	<img alt='screenshot 8' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/8.png'/>
</p>
<p align='center'>
	<img alt='screenshot 9' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/9.png'/>
</p>
<p align='center'>
	<img alt='screenshot 12' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/12.png'/>
</p>
<p align='center'>
	<img alt='screenshot 13' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/13.png'/>
</p>
<p align='center'>
	<img alt='screenshot 14' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/14.png'/>
</p>
<p align='center'>
	<img alt='screenshot 15' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/15.png'/>
</p>
<p align='center'>
	<img alt='screenshot 16' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/16.png'/>
</p>
<p align='center'>
	<img alt='screenshot 17' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/17.png'/>
</p>

### Material 3 
#### Dark
<p align='center'>
	<img alt='M3 Dark screenshot' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/18.png'/>
</p>

#### Light
<p align='center'>
	<img alt='M3 Light screenshot' src='https://github.com/AhmedSaadi0/my-hyprland-config/blob/main/screenshots/19.png'/>
</p>
