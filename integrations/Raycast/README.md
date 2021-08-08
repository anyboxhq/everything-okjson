# Raycast Script Commands

Thare are two Script Commands for Raycast users:

1. `okjson-pasteboard.sh`

This script command lets you open OK JSON and view JSON string in your Pasteboard.

Valid JSON string needs to be presented in your Pasteboard.

2. `okjson-download.sh`

This script command lets you open OK JSON and download URL in your pasteboard.

Valid URL needs to be presented in your Pasteboard. Please also notice that it uses a `GET` method to download content. Make sure the API server does not require any kind of authorization and repsonds with valid JSON string.

## Usuage
1. Open Preferences in Raycast and select "extensions" tab.
2. Select "Script Commands" and Click "Add Directories" if you have not added a directory.
3. Open the directory and copy `okjson-pasteboard.sh` or`okjson-download.sh` to this directory (or both if you want).
4. Add a new folder called `images` and copy `okjson.png` in `images` to this folder.
5. You should see OK JSON in Raycast's search results afterwards.
