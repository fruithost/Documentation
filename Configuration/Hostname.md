# Hostname
It may happen that the `hostname` is not set correctly during the installation process.

The following message then appears when you try to call up the fruithost panel:

![IMAGE_HOST_ERROR]

The `hostname` must be entered correctly in the VHost of the panel so that the web panel can be called up. Unfortunately, for inexplicable reasons, it happens again and again that the `hostname` is not correctly transferred to the system despite a query during the installation process.

### `Either:` Correct the Hostname via `FTP`

Open the file `/etc/fruithost/config/apache2/panel.conf` with your **SFTP**- or **FTP**-Client:

![IMAGE_EDIT_PANEL]

and edit the Entry `ServerName` to your correct Panel-Domain.

### `Other:` Correct the Hostname via `Shell`
Open the file `/etc/fruithost/config/apache2/panel.conf` with your Shell-Editor like `nano`:

> nano /etc/fruithost/config/apache2/panel.conf

![IMAGE_NANO_PANEL]

After the host name has been opened and changed with `nano`, the file still needs to be saved:

> 1. Press `CMD` + `O` on your keyboard to save the file.
> 2. Press `Enter` on your keyboard to confirm the save process.
> 3. Press `CMD` + `X` on your keyboard to exit `nano`.


### After Editing
Please note that you must reload or restart the web server after editing the `panel.conf`:

> service apache2 reload

After these two steps, the web panel should be accessible as usual.

[IMAGE_HOST_ERROR]: ../Images/Install/HostnameError.png
[IMAGE_EDIT_PANEL]: ../Images/Install/EditPanelConf.png
[IMAGE_NANO_PANEL]: ../Images/Install/NanoPanelConfig.png
