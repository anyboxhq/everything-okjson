# OK JSON Integrations

We provide integrations for common productivity apps. Currently we support [Alfred][alfred], [LaunchBar][launchbar] and [Raycast][raycast] out-of-the-box. But you can easily write your own if you are not using any of these.

## URL Schemes
OK JSON supports four types of URL Schemes. These official integrations are just wrappers around those URL Schemes.

1. View JSON String in Pasteboard

```sh
okjson://paste
```

Valid JSON string needs to be presented in your Pasteboard.

2. Download URL in Pasteboard

```
okjson://download
```

Valid URL needs to be presented in your Pasteboard.

Please also notice that it uses a `GET` method to download content. Make sure the API server **does not require any kind of authorization** and repsonds with valid JSON string.

3. Run cURL command in Pasteboard

```
okjson://curl
```

cURL Command Example:
```sh
curl 'https://okjson.app/api/hello' \
  -H 'cache-control: max-age=0' \
  -H 'dnt: 1' \
  -H 'user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.131 Safari/537.36' \
  -H 'accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9' \
  -H 'sec-fetch-site: none' \
  -H 'sec-fetch-mode: navigate' \
  -H 'sec-fetch-user: ?1' \
  -H 'sec-fetch-dest: document' \
  -H 'accept-language: zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7' \
  --compressed
```

4. Open with Specific JSON Content

```
okjson://new?content={URL Encoded}
```

## Example

1. Popclip
```
# popclip
name: View in OK JSON
icon: symbol:curlybraces.square
url: okjson://new?content=***
```

2. Shell Script
```sh
#!/bin/bash

open "okjson://paste"
```

3. Apple Script
```applescript
open location "okjson://paste"
```

4. Shell Script
```sh
#!/bin/sh
open "okjson://new?content=%7B%22code%22%3A0%2C%22msg%22%3A%22URL%20Scheme%20Usage%22%7D"
```
Result:
```json
{
  "code": 0,
  "msg": "URL Scheme Usage"
}
```

5. Working with jc (JSON CLI output utility)

`jc` is a CLI tool and python library that converts the output of popular command-line tools and file-types to JSON or Dictionaries. You can find it here: [jc][jc].

```sh
# Give OK JSON an alias. You can put it under ~/.bashrc so that it persists through launches.
alias oj="open 'okjson://paste'"

# List current working directory and open it in OK JSON
ls -l ./ | jc --ls | pbcopy | oj

```

Result:
```json
[
  {
    "filename": "LICENSE",
    "flags": "-rw-r--r--",
    "links": 1,
    "owner": "francisfeng",
    "group": "staff",
    "size": 11357,
    "date": "Aug 6 09:46"
  },
  {
    "filename": "README.md",
    "flags": "-rw-r--r--",
    "links": 1,
    "owner": "francisfeng",
    "group": "staff",
    "size": 19,
    "date": "Aug 6 09:46"
  },
  {
    "filename": "extensions",
    "flags": "drwxr-xr-x",
    "links": 7,
    "owner": "francisfeng",
    "group": "staff",
    "size": 224,
    "date": "Aug 6 11:37"
  }
]
```

## More URL Schemes
If you need more URL Schemes, let us know. You can open an issue in this repository and explain your needs. We would consider it and get back to you.

[alfred]: https://www.alfredapp.com/
[launchbar]: https://obdev.at/products/launchbar/index.html
[raycast]:https://www.raycast.com/
[jc]: https://github.com/kellyjonbrazil/jc
