# Content/Inhalt

* [Content/Inhalt](#contentinhalt)
   * [Custom css file for the Seafile server](#custom-css-file-for-the-seafile-server)
      * [Intro](#intro)
      * [Installation](#installation)
      * [Notes](#notes)
   * [Screenshots](#screenshots)
      * [Light](#light)
      * [Semi dark](#semi-dark)

# Custom css file for the Seafile server

## Intro

The Seafile server comes with a standard template that does not look bad, but does not like everyone. This can be changed by overwriting desired parts of the template with own values.

There are two versions of the theme:

1. light and
2. semi dark

With the ***custom.css*** from this repository (folder ***light*** or ***semidark***), the default color **orange** of the elements is changed to **green**.  In the semi dark version some elements are colored in dark grey, for example the left navigation bar.

## Installation

Copy the file ***custom.css*** from the ***light*** or ***semidark*** folder  to ***seahub-data/custom*** and add the following line to ***conf/seahub-settings.py***:

    BRANDING_CSS = 'custom/custom.css'

To change the icon color for folder icons you have to copy the file folder-192.png from the img folder of this repo into the seahub folder (***seafile-server-latest/seahub/media/img***) on your server and rename it to folder-24.png. But before please create a backup of your original file. After an update of the Seafile server this change will be reverted and you have to copy it again.

If you want to use the green Favicon copy the ***favicon.png*** to ***seahub-data/custom*** and add the following line to your ***conf/seahub-settings.py***:
    
    FAVICON_PATH = 'custom/favicon.png'

Finally, the Seafile server (and Seahub) must be restarted. For example in Debian Jessie this can be done with:

```bash
sudo systemctl stop seahub.service
sudo systemctl stop seafile.service
sudo systemctl start seafile.service
sudo systemctl start seahub.service
```

## Notes

- the icons for folders are not changed and still have the color orange. I'm currently looking for a way to change the folder icon color so that the changes will be kept within a server update.
- ***custom.css*** tested with Seafile Server 6.3.2
- for Seafile Server 6.2.5 use the ***custom.css*** from the branch v6_2_5 (**only light version**)
- At the top of the custom.css you will find two variables which define the main colors (dark and light). Here you can change the color to the color you want to use:

```css
:root {
    --darkMain: #3CB371;    /* #008a3b - Main color for elements */
    --lightMain: #C1FFC1;   /* #90a396 - Second color, e. g. for some selected items */
    --textLM: #000000;      /* Text color for elements with lightMain */
    --leftSide: #474747;    /* dark grey - Background color of the left side bar (use #FFFFFF for originasl white) */
    --lefSideText: #D1D1D1; /* light grey - Text and icon color of the left side bar (original #333) */ 
}
```

# Screenshots

## Light

<img src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot1.png" alt="Login" width="300"> <img src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot2.png" alt="Navbar" width="300">
<img src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot3.png" alt="Main" width="600">
<img src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot4.png" alt="Folder" width="600">

---

## Semi dark

<img src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot5.png" alt="Main semi dark" width="600">
<img src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot6.png" alt="Login" width="300">
