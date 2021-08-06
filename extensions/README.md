# OK JSON Extensions

We provide integrations for common productivity apps. Currently we support [Alfred](https://www.alfredapp.com/), [LaunchBar](https://obdev.at/products/launchbar/index.html) and [Raycast](https://www.raycast.com/) out-of-the-box. But you can easily write your own if you are not using any of these.

## URL Schemes
OK JSON supports two types of URL Schemes. These official integrations are just wrappers around those two URL Schemes.

1. View JSON String in Pasteboard

```sh
okjson://paste
```

Valid JSON string needs to be presented in your Pasteboard.

2. Download URL in Pasteboard

```sh
okjson://download
```

Valid URL needs to be presented in your Pasteboard.

Please also notice that it uses a `GET` method to download content. Make sure the API server **does not require any kind of authorization** and repsonds with valid JSON string.

## Example

1. Shell Script
```sh
#!/bin/bash

open "okjson://paste"
```

2. Apple Script
```applescript
open location "okjson://paste"
```


## More URL Schemes
If you need more URL Schemes, let us know. You can open an issue in this repository and explain your needs. We would consider it and get back to you.
