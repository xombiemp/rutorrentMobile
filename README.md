## ruTorrent Mobile Plugin

### Prereqs
This plugin requires ruTorrent v4.3 or newer (it uses the core's Bootstrap 5 assets and category list) and the httprpc plugin.

### Installation
Place all the plugin files in a directory called mobile in the rutorrent/plugins directory.
To clone directly from this git repository, run this command in the rutorrent/plugins directory:
```
git clone https://github.com/xombiemp/rutorrentMobile.git mobile

```

> **Note:** It is important that the plugin directory is named 'mobile' so that the supporting files are loaded correctly.

Optional plugins that add additional functionality:
* _getdir: Allows you to browse directories from your server when adding a torrent or moving torrent data.
* erasedata: Allows you to delete with data when deleting a torrent.
* seedingtime: Adds the fields Added and Finished to the torrent details page, and the addtime and seedingtime sort options.
* ratio: Allows you to see and set the ratio group for a torrent.
* throttle: Allows you to see and set the channel for a torrent.
* datadir: Adds a Save to... page for moving a torrent's data, from the edit button on the save path field.
* diskspace: Shows a disk usage meter on the settings page.
* check_port: Shows the IP address and port reachability status on the settings page.
* geoip: Shows country flags and names in the peers table.
* tracklabels: Shows label icons and tracker favicons on the filter page.

### Configuration
There are three configurable boolean options and two multi-value options that you may set at the top of init.js.
#### plugin.enableAutodetect
true by default. This option sets whether mobile devices will be autodetected to enable the plugin.

#### plugin.tabletsDetect
true by default. This option sets whether to include tablets in the autodetection.

#### plugin.eraseWithDataDefault
false by default. This option sets the default state of the delete with data checkbox in the confirmation page when deleting a torrent.  
If in rutorrent you turned off 'Confirm when deleting torrents', this plugin will not display the confirmaion page either. In this case, the decision about deleting data will be determined by the value of this option.

#### plugin.sort
'name' by default. Possible values: 'name', '-name', 'status', '-status', 'size', '-size', 'uploaded', '-uploaded', 'downloaded', '-downloaded', 'done', '-done', 'eta', '-eta', 'ul', '-ul', 'dl', '-dl', 'ratio', '-ratio', and if the seedingtime plugin is loaded 'addtime', '-addtime', 'seedingtime', '-seedingtime'.  
This option sets the default sort value of the torrent list. Without negative it's ascending, with negative it's descending.

#### plugin.accentColor
'primary' by default. Possible values: 'primary' (blue), 'secondary' (gray), 'success' (green), 'danger' (red), 'warning' (yellow), 'info' (cyan), 'dark' (near-black).  
This option sets the Bootstrap theme color used for buttons, progress bars, tab highlights and selections. The color can also be changed temporarily from the settings page; a page reload reverts to this option.

### Utilization
If you set plugin.enableAutodetect to true, the plugin will automaticaly load when detecting a mobile device. To force load the plugin in a desktop browser add '?mobile=1' to the end of the rutorrent url.

### Troubleshooting
If you are experiencing problems with this plugin, for example it's not scrolling or there are overlapping elements, try these solutions.
* Make sure the httprpc plugin is installed. The mobile plugin requires it.
* Make sure the plugin directory is named 'mobile' or else it won't load the plugin specific css file called mobile.css
* If you are still having issues, submit an issue on github https://github.com/xombiemp/rutorrentMobile/issues and be sure to include as much detail as possible including: mobile device and OS and browser, server OS and webserver.
