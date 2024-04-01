# 1 Desktop Enviroment

## 1.1 i3wm

> ~/.config/i3/config

```bash
# i3 config file (v4)

# Set the mod key
set $mod Mod1

# Font for window titles. Will also be used by the bar unless a different font
# is used in the bar {} block below.
font pango:monospace 8

# Start XDG autostart .desktop files using dex. See also
# https://wiki.archlinux.org/index.php/XDG_Autostart
# exec --no-startup-id dex --autostart --environment i3

exec_always flameshot
exec_always fcitx5
exec_always copyq

# exec_always nm-applet

# exec_always xinput disable 9

# picom
exec_always picom

# wallpappers
exec --no-startup-id nitrogen --restore

# polybar
# exec_always ~/.config/polybar/launch.sh

# screenkey
# exec_always killall screenkey
# exec_always sleep 1; screenkey

# new_window none
new_window none
new_float none

gaps inner 6
gaps outer 3

# The combination of xss-lock, nm-applet and pactl is a popular choice, so
# they are included here as an example. Modify as you see fit.

# xss-lock grabs a logind suspend inhibit lock and will use i3lock to lock the
# screen before suspend. Use loginctl lock-sessin to lock your screen.
exec --no-startup-id xss-lock --transfer-sleep-lock -- i3lock --nofork

# NetworkManager is the most popular way to manage wireless networks on Linux,
# and nm-applet is a desktop environment-independent system tray GUI for it.
# exec --no-startup-id nm-applet

# Use pactl to adjust volume in PulseAudio.
# set $refresh_i3status killall -SIGUSR1 i3status
# bindsym XF86AudioRaiseVolume exec --no-startup-id pactl set-sink-volume @DEFAULT_SINK@ +10% && $refresh_i3status
# bindsym XF86AudioLowerVolume exec --no-startup-id pactl set-sink-volume @DEFAULT_SINK@ -10% && $refresh_i3status
# bindsym XF86AudioMute exec --no-startup-id pactl set-sink-mute @DEFAULT_SINK@ toggle && $refresh_i3status
# bindsym XF86AudioMicMute exec --no-startup-id pactl set-source-mute @DEFAULT_SOURCE@ toggle && $refresh_i3status

bindsym $mod+F2 exec --no-startup-id amixer set Master playback 1-
bindsym $mod+F3 exec --no-startup-id amixer set Master playback 1+
bindsym $mod+F4 exec --no-startup-id amixer set Master toggle

# Use Mouse+$mod to drag floating windows to their wanted position
floating_modifier $mod

# move tiling windows via drag & drop by left-clicking into the title bar,
# or left-clicking anywhere into the window while holding the floating modifier.
# tiling_drag modifier titlebar

# start a terminal
# bindsym $mod+Return exec i3-sensible-terminal
bindsym $mod+Return exec alacritty

bindsym $mod+c exec chromium

# bindsym $mod+m exec thunderbird

bindsym F1 exec flameshot gui

# kill focused window
bindsym $mod+Shift+q kill

# start dmenu (a program launcher)
# bindsym $mod+d exec --no-startup-id dmenu_run
bindsym $mod+d exec --no-startup-id rofi -show drun
# A more modern dmenu replacement is rofi:
# bindcode $mod+40 exec "rofi -modi drun,run -show drun"
# There also is i3-dmenu-desktop which only displays applications shipping a
# .desktop file. It is a wrapper around dmenu, so you need that installed.
# bindcode $mod+40 exec --no-startup-id i3-dmenu-desktop

# change focus
bindsym $mod+h focus left
bindsym $mod+j focus down
bindsym $mod+k focus up
bindsym $mod+l focus right

# alternatively, you can use the cursor keys:
bindsym $mod+Left focus left
bindsym $mod+Down focus down
bindsym $mod+Up focus up
bindsym $mod+Right focus right

# move focused window
bindsym $mod+Shift+h move left
bindsym $mod+Shift+j move down
bindsym $mod+Shift+k move up
bindsym $mod+Shift+l move right

# alternatively, you can use the cursor keys:
bindsym $mod+Shift+Left move left
bindsym $mod+Shift+Down move down
bindsym $mod+Shift+Up move up
bindsym $mod+Shift+Right move right

# split in horizontal orientation
bindsym $mod+semicolon split h

# split in vertical orientation
bindsym $mod+v split v

# enter fullscreen mode for the focused container
bindsym $mod+f fullscreen toggle

# change container layout (stacked, tabbed, toggle split)
bindsym $mod+s layout stacking
bindsym $mod+w layout tabbed
bindsym $mod+e layout toggle split

# toggle tiling / floating
bindsym $mod+Shift+space floating toggle

# change focus between tiling / floating windows
bindsym $mod+space focus mode_toggle

# focus the parent container
bindsym $mod+a focus parent

# focus the child container
#bindsym $mod+d focus child

# Define names for default workspaces for which we configure key bindings later on.
# We use variables to avoid repeating the names in multiple places.
set $ws1 "1"
set $ws2 "2"
set $ws3 "3"
set $ws4 "4"
set $ws5 "5"
set $ws6 "6"
set $ws7 "7"
set $ws8 "8"
set $ws9 "9"
set $ws10 "10"

# switch to workspace
bindsym $mod+1 workspace number $ws1
bindsym $mod+2 workspace number $ws2
bindsym $mod+3 workspace number $ws3
bindsym $mod+4 workspace number $ws4
bindsym $mod+5 workspace number $ws5
bindsym $mod+6 workspace number $ws6
bindsym $mod+7 workspace number $ws7
bindsym $mod+8 workspace number $ws8
bindsym $mod+9 workspace number $ws9
bindsym $mod+0 workspace number $ws10

# move focused container to workspace
bindsym $mod+Shift+1 move container to workspace number $ws1
bindsym $mod+Shift+2 move container to workspace number $ws2
bindsym $mod+Shift+3 move container to workspace number $ws3
bindsym $mod+Shift+4 move container to workspace number $ws4
bindsym $mod+Shift+5 move container to workspace number $ws5
bindsym $mod+Shift+6 move container to workspace number $ws6
bindsym $mod+Shift+7 move container to workspace number $ws7
bindsym $mod+Shift+8 move container to workspace number $ws8
bindsym $mod+Shift+9 move container to workspace number $ws9
bindsym $mod+Shift+0 move container to workspace number $ws10

# reload the configuration file
bindsym $mod+Shift+c reload
# restart i3 inplace (preserves your layout/session, can be used to upgrade i3)
bindsym $mod+Shift+r restart
# exit i3 (logs you out of your X session)
bindsym $mod+Shift+e exec "i3-nagbar -t warning -m 'You pressed the exit shortcut. Do you really want to exit i3? This will end your X session.' -B 'Yes, exit i3' 'i3-msg exit'"

# resize window (you can also use the mouse for that)
mode "resize" {
        # These bindings trigger as soon as you enter the resize mode

        # Pressing left will shrink the window’s width.
        # Pressing right will grow the window’s width.
        # Pressing up will shrink the window’s height.
        # Pressing down will grow the window’s height.
        bindsym h resize shrink width 10 px or 10 ppt
        bindsym j resize grow height 10 px or 10 ppt
        bindsym k resize shrink height 10 px or 10 ppt
        bindsym l resize grow width 10 px or 10 ppt

        # same bindings, but for the arrow keys
        bindsym Left resize shrink width 10 px or 10 ppt
        bindsym Down resize grow height 10 px or 10 ppt
        bindsym Up resize shrink height 10 px or 10 ppt
        bindsym Right resize grow width 10 px or 10 ppt

        # back to normal: Enter or Escape or $mod+r
        bindsym Return mode "default"
        bindsym Escape mode "default"
        bindsym $mod+r mode "default"
}
bindsym $mod+r mode "resize"

for_window [instance="kitty"] floating enable
for_window [instance="zathura"] floating enable

for_window [instance="audacity"] floating enable
for_window [instance="kicad"] floating enable
for_window [instance="wireshark"] floating enable
for_window [instance="virt-manager"] floating enable
for_window [instance="nitrogen"] floating enable

# for_window [instance="gerberview"] floating enable
# for_window [instance="vlc"] floating enable
# for_window [instance="mirage"] floating enable

for_window [instance="flameshot"] floating enable
for_window [instance="fcitx5-config-qt"] floating enable
for_window [instance="copyq"] floating enable

# for_window [instance="ImageMagick"] floating enable
# for_window [instance="Eclipse"] floating enable
# for_window [instance="DBeaver"] floating enable

# for_window [instance="kicad"] floating enable
# for_window [instance="bash /usr/bin/minecraft"] floating enable

# Start i3bar to display a workspace bar (plus the system information i3status
# finds out, if available)
bar {
    status_command i3status
	position top
	colors{
		focused_workspace	#F9FAF9 #61AFEF #292F34
		active_workspace	#595B5B #353836 #FDF6E3
		inactive_workspace	#595B5B #222D31 #EEE8D5
	}	
}
```

## 1.2 polybar

# 2 Terminal

## 2.1 alacritty

> ~/.config/alacritty/alacritty.toml

```toml
[colors.bright]
black = "#5c6370"
blue = "#61afef"
cyan = "#56b6c2"
green = "#98c379"
magenta = "#c678dd"
red = "#e06c75"
white = "#ECEFF4"
yellow = "#d19a66"

[colors.normal]
black = "#1e2127"
blue = "#11b5f6"
cyan = "#88C0D0"
green = "#90ff00"
magenta = "#B48EAD"
red = "#ff0000"
white = "#ffffff"
yellow = "#Ebdf8B"

[colors.primary]
background = "#000000"
foreground = "#D8DEE9"

[font]
size = 8.0

[font.bold]
family = "Source Code Pro"
style = "Bold"

[font.bold_italic]
family = "Source Code Pro"
style = "Bold Italic"

[font.italic]
family = "Source Code Pro"
style = "Italic"

[font.normal]
family = "Source Code Pro"
style = "Regular"

[window]
dynamic_title = true
padding = {x = 0, y = 0}
dimensions = {columns = 100, lines = 30}
decorations = "Full"
decorations_theme_variant = "Dark"
```

> ~/.config/alacritty/alacritty.yml

```yml
colors:
  primary:
    background: "#000000"
    # background: "#1e2127"
    # background: "#2E3440"
    foreground: "#D8DEE9"

  normal:
    black: "#1e2127"
    blue: '#11b5f6'
    red: '#ff0000'
    green: "#90ff00"
    yellow: "#Ebdf8B"
    magenta: "#B48EAD"
    cyan: "#88C0D0"
    white: "#ffffff"

  bright:
    black: "#5c6370"
    red: "#e06c75"
    green: "#98c379"
    yellow: "#d19a66"
    blue: "#61afef"
    magenta: "#c678dd"
    cyan: "#56b6c2"
    white: "#ECEFF4"
  
font:
  normal:
    family: "Source Code Pro"
    style: Regular
  bold:
    family: "Source Code Pro"
    style: Bold
  italic:
    family: "Source Code Pro"
    style: Italic
  bold_italic:
    family: "Source Code Pro"
    style: Bold Italic
  size: 10.0 

window:
  padding:
    x: 0
    y: 0
```

# 3 NeoVim



