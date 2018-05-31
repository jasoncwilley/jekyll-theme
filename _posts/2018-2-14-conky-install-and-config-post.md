---
layout: post
title: "Conky Setup"
description: "My Conkyrc Files"
tags: [conky, themes, examples, scripts, install, configuration]
comments: true
image:
  background: hexagon.jpg
author: "Jason C. Willey"
---



Conky is a system monitor software for the X Window System. It is available for GNU/Linux and FreeBSD. It is used to monitor system variables including CPU, memory, swap, disk space, temperature, top, upload, download, system messages, and much more.  Conky is extremely configurable, however, the configuration can be a little hard to understand.

<a

## Download the Theme
Navigate to your Desktop directory (Feel free to use any directory you want)

```
userone@laptop:~/Development/tutorials$mkdir -p ~/.config/conky
userone@laptop:~/Development/tutorials$
yaourt -S conky
userone@laptop:~/Desktop$
conky -C > ~/.config/conky/conky.conf
```
/a>

<a
One of the nice features of conky is to pipe to your desktop some /var/log/ files to read all kinds of log messages. Most of these files can only be read by root, but running conky as root is not recommended, so you will need to add username to the log group:
/a>
```
userone@laptop:~/Desktop$
usermod -aG log username
```
Use the conkyrc files to configure your desktop.

```
cd ~/.config/conky/conkyrc
```

You can run multiple conkyrc files simultaneously.  I decided to create one for each side of the desktop.  

```
nano ~/.config.conky/mintypc-leftside-conkyrc

background yes
double_buffer yes
no_buffers yes
text_buffer_size 2048
imlib_cache_size 0
update_interval 1
cpu_avg_samples 1nano ~/.config.conky/mintypc-leftside-conkyrc
format_human_readable

alignment top_left
gap_x 0
gap_y 0
minimum_size 240 1080
maximum_width 250

own_window yes
own_window_type desktop	# options are: normal/override/dock/desktop/panel
own_window_class Conky
own_window_hints undecorated,below,sticky,skip_taskbar,skip_pager
own_window_transparent yes
own_window_colour 333333
own_window_argb_visual no
own_window_argb_value 0

border_inner_margin 0
border_outer_margin 0

default_bar_size 100 6
draw_shades no
default_shade_color 000000
draw_outline no
default_outline_color 000000
draw_borders no
draw_graph_borders yes
default_graph_size 40,220
show_graph_scale no
show_graph_range no

override_utf8_locale yes
use_xft yes
xftalpha 1
uppercase no
max_text_width 41

default_color ffffff
color1 ffffff
color2 FF5A45
color3 81CAE0
color4 FF5A45
TEXT
# $sysname
${goto 10}${color4}${font DejaVu Sans Mono:size=20} System Info${color}${font}
${goto 10}
${goto 10}${color4}${alignc}${font DejaVu Sans Mono:size=16}Kernel${color}${font}
${goto 10}         $kernel${color}
${goto 10}
${goto 10}${color4}System Uptime:${color}   $uptime${color}
${goto 10}
          Desktop
 ${goto 10}          ${color2}${desktop} of ${desktop_number}${color}
#

# cpu load/temp/graph
${goto 10}${font DejaVu Sans Mono:size=11}${voffset 5}${color2}     CPU 1: ${cpu cpu1}%${alignr 10}${exec sensors|grep 'Core 0'|awk '{print $3}'}
${goto 10}${voffset -5}${color2}${cpugraph cpu1 20,210 FFFFFF FF5A45}
${goto 10}${voffset 0}${color2}     CPU 2: ${cpu cpu2}%${alignr 10}${exec sensors|grep 'Core 1'|awk '{print $3}'}
${goto 10}${voffset -5}${color2}${cpugraph cpu3 20,210 66241C FF5A45}
${goto 10}${voffset 5}${color2}     CPU 3: ${cpu cpu3}%${alignr 10}${exec sensors|grep 'Core 2'|awk '{print $3}'}
${goto 10}${voffset -5}${color2}${cpugraph cpu3 20,210 66241C FF5A45}
${goto 10}${voffset 0}${color2}     CPU 4: ${cpu cpu4}%${alignr 10}${exec sensors|grep 'Core 3'|awk '{print $3}'}
${goto 10}${voffset -5}${color2}${cpugraph cpu4 20,210 66241C FF5A45}
${goto 10}${voffset 5}${color2}     CPU 5: ${cpu cpu5}%${alignr 10}${exec sensors|grep 'Core 4'|awk '{print $3}'}
${goto 10}${voffset -5}${color2}${cpugraph cpu5 20,210 66241C FF5A45}
${goto 10}${voffset 0}${color2}     CPU 6: ${cpu cpu6}%${alignr 10}${exec sensors|grep 'Core 5'|awk '{print $3}'}
${goto 10}${voffset -5}${color2}${cpugraph cpu6 20,210 66241C FF5A45}
${goto 10}${voffset 5}${color2}     CPU 7: ${cpu cpu7}%${alignr 10}${exec sensors|grep 'Core 6'|awk '{print $3}'}
${goto 10}${voffset -5}${color2}${cpugraph cpu7 20,210 66241C FF5A45}
${goto 10}${voffset 0}${color2}     CPU 8: ${cpu cpu8}%${alignr 10}${exec sensors|grep 'Core 7'|awk '{print $3}'}
${goto 10}${voffset -5}${color2}${cpugraph cpu8 20,210 66241C FF5A45}${font}
# top processes
${goto 10}
${voffset -5}${color4}${alignc}${font DejaVu Sans Mono:size=16}Top Processes ${font}${color}
${voffset 4}${color1}${goto 10}${top name 1}${alignr 10}${top cpu 1}%
${goto 10}${voffset -2}${top name 2}${alignr 10}${top cpu 2}%
${goto 10}${voffset -2}${top name 3}${alignr 10}${top cpu 3}%
${goto 10}${voffset -2}${top name 4}${alignr 10}${top cpu 4}%${color}
${goto 10}
# top memory
${voffset -5}${color4}${alignc}${font DejaVu Sans Mono:size=16}Memory Usage ${font}${color}
${goto 10}${voffset 10}${color2}${goto 70}${color2}$membar${alignr 10}${color1}$memperc%
${goto 10}${color1}${voffset -2}${font}${top_mem name 1}${alignr 10}${top mem 1}%
${goto 10}${voffset -2}${top_mem name 2}${alignr 10}${top mem 2}%
${goto 10}${voffset -2}${top_mem name 3}${alignr 10}${top mem 3}%
${goto 10}${voffset -2}${top_mem name 4}${alignr 10}${top mem 4}%

#network${font DejaVu Sans Mono:size=20}
${voffset -2}${color4}${alignc}${font DejaVu Sans Mono:size=15}Network Information ${font}${color}
${goto 10}
${goto 10}${color1} LAN IP:   ${addr enp3s0}
${goto 10}WAN IP:  ${execi 300 curl http://icanhazip.com}
${goto 10} EXT IP:   ${execi 300 curl http://ipinfo.io/ip}${color}

```
Now you need to create a conf file for the right side.

```
nano ~/.config.conky/mintypc-rightside-conkyrc
background yes
double_buffer yes
no_buffers yes
text_buffer_size 2048
imlib_cache_size 0
update_interval 1
cpu_avg_samples 1
format_human_readable

alignment top_right
gap_x 0
gap_y 0
minimum_size 240 1080
maximum_width 250

own_window yes
own_window_type desktop	# options are: normal/override/dock/desktop/panel
own_window_class Conky
own_window_hints undecorated,below,sticky,skip_taskbar,skip_pager
own_window_transparent yes
own_window_colour 333333
own_window_argb_visual no
own_window_argb_value 0

border_inner_margin 0
border_outer_margin 0

default_bar_size 100 6
draw_shades no
default_shade_color 000000
draw_outline no
default_outline_color 000000
draw_borders no
draw_graph_borders yes
default_graph_size 40,220
show_graph_scale no
show_graph_range no

override_utf8_locale yes
use_xft yes
xftalpha 1
uppercase no
max_text_width 41

default_color ffffff   
color1 ffffff
color2 FF5A45
color3 81CAE0
color4 FF5A45

TEXT
${color2}
${color2}
${color2}
${color2}${goto 10}${font DejaVu Sans Mono:size=44}${time %H}${font DejaVu Sans Mono:size=24}${voffset -25}'${time %M}${font DejaVu Sans Mono:size=12}${voffset -12}${time %S}
${color2}
${color2}${goto 85}${voffset 10}${font :size=10}${time %A}
${color2}${goto 85}${voffset 1}${font :size=10}${time %d %B %Y}
${color2}
${color}${font RsbillsDng:size=16}${font}${font DejaVu Sans Mono:size=10}${execpi 3600 DJS=`date +%_d`; cal -m | sed '1d' | sed '/./!d' | sed 's/$/                     /' | fold -w 21 | sed -n '/^.\{21\}/p' | sed 's/^/${alignc} /' | sed /" $DJS "/s/" $DJS "/" "'${color2}'"$DJS"'${color}'" "/}${font}
${color2}${font DejaVu Sans Mono:size=16} Music Player:${font}
${color2}
${color2}
${color2}
${color2}
${color2}
${color2}
${color2}
 ${color2}Artist : ${color}${execi 5 python2 /home/minty/.config/conky/anowplaying.py -a}
 ${color2}Title  : ${color}${execi 5 python2 /home/minty/.config/conky/anowplaying.py -t}
 ${color2}Album  : ${color}${execi 5 python2 /home/minty/.config/conky/anowplaying.py -l}
 ${color2}Year   : ${color}${execi 5 python2 /home/minty/.config/conky/anowplaying.py -y}
 ${color2}Bitrate: ${color}${execi 5 /home/minty/.config/conky/anowplaying.py  -b}kbit/s
 ${execi 5 python2 /home/minty/.config/conky/anowplaying.py -c /tmp/cover.jpg}${image /tmp/cover.jpg -p 80,425 -s 110x110 -n}


${color2}${font DejaVu Sans Mono:size=16} Updates Available:${font}${execi 3600 checkupdates | wc -l}

```


If you did everything correctly you should now have a copy of Neo-HPSTR on in a folder called hpstr-jekyll-theme-master on your desktop.  The next section of the tutorial deals with configuring theme.  if you have not already installed jekyll and it's dependencies please do that before preceeding. Link to [Jekyll Install Tutorial]( http://localhost:4000/neo-hipster-theme-configuration-post/)


## Running the conkyrc files

After creating the conkyrc conf files you can run them load the desktop.  To run the files enter the following commands into the terminal.  

```
userone@laptop:~/Desktop$ cd ~/.config/conky/
userone@laptop:~/.config/conky/$ conky -c mintypc-leftside-conkyrc
```
The left side should appear and now run the conkyrc file for the rightside of the screen.

```
userone@laptop:~/.config/conky/$ conky -c mintypc-rightside-conkyrc
```

Good Job!  You can now enjoy this conky setup or change the conkyrc conf files to meet your needs!

Information should be free not trademarked and copy written.  


{% if page.comments %}
<div id="disqus_thread"></div>
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/
/*
var disqus_config = function () {
this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = '//jajb.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %}
