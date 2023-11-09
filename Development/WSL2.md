# WSL2 Windows
If you're running Debian on WSL2, you must add following files, that starts all necessary services at startup:

**/etc/wsl.conf**
```
[boot]
systemd = true
command="/etc/rc"
```

**/etc/rc**
```
#!/bin/sh

# Start system services
for i in /etc/rc3.d/S*; do
  if [ -x $i ]; then
    $i start
  fi
done

# Run /etc/rc.local if it exists
if [ -x /etc/rc.local ] ; then
  /etc/rc.local
fi
```
