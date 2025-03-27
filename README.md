# swgoh-gamedata.
This should be updated automatically within about 10 mins of a new update pushed for the game
all the collections are structured as 
```
{version: 'CURRENT_VERSION', data: []}
```
the units.json is filtered for obtainable === true and obtainableTime === '0' (this should be player obtainable units)

the units_pve is filtered for obtainable !== true or obtainableTime !== '0' (this should be pve units)

the versions.json has `gameVersion` and `localeVersion` that is only updated with the current game and locale version if all files where uploaded successfully. 
The versions of the files may be update before these are due to upload errors

It is recommended to just pull this file and compare to stored values before pulling all the files.
```
https://raw.githubusercontent.com/swgoh-utils/gamedata/main/allVersions.json
```
Performing a GET request to `https://api.github.com/repos/swgoh-utils/gamedata/contents` will give a list of all the files
below is an example:
```
{
    "name": "Loc_CHS_CN.txt.json",
    "path": "Loc_CHS_CN.txt.json",
    "sha": "e755a1e745f0b77be711a82f24e4a713b4084e34",
    "size": 12698495,
    "url": "https://api.github.com/repos/swgoh-utils/gamedata/contents/Loc_CHS_CN.txt.json?ref=main",
    "html_url": "https://github.com/swgoh-utils/gamedata/blob/main/Loc_CHS_CN.txt.json",
    "git_url": "https://api.github.com/repos/swgoh-utils/gamedata/git/blobs/e755a1e745f0b77be711a82f24e4a713b4084e34",
    "download_url": "https://raw.githubusercontent.com/swgoh-utils/gamedata/main/Loc_CHS_CN.txt.json",
    "type": "file",
    "_links": {
      "self": "https://api.github.com/repos/swgoh-utils/gamedata/contents/Loc_CHS_CN.txt.json?ref=main",
      "git": "https://api.github.com/repos/swgoh-utils/gamedata/git/blobs/e755a1e745f0b77be711a82f24e4a713b4084e34",
      "html": "https://github.com/swgoh-utils/gamedata/blob/main/Loc_CHS_CN.txt.json"
    }
  }
```

the download_url can be used with an api call to get the file contents
you can also just use `https://raw.githubusercontent.com/swgoh-utils/gamedata/main/FILE_NAME.json` as url to download


Please read about the rate limits here:
https://docs.github.com/en/rest/overview/resources-in-the-rest-api?apiVersion=2022-11-28#rate-limiting

The data updates are made via this https://github.com/c3pobot/gamedatasync
