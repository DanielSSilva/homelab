# Allowing vscode-server to write to dockge
sudo chown -R 911:911 /mnt/user/appdata/dockge/stacks

# Force all files that are created afterwards to inherit the permissions of the parent directory
sudo chmod g+s /mnt/user/appdata/dockge/stacks