# swgoh-gamedata
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
https://raw.githubusercontent.com/scuba75/swgoh-gamedata/main/versions.json
```
Performing a GET request to `https://api.github.com/repos/scuba75/swgoh-gamedata/contents` will give a list of all the files
below is an example:
```
{
    "name": "Loc_ENG_US.txt.json",
    "path": "Loc_ENG_US.txt.json",
    "sha": "2540cba2b4cec3c862a4f5af40e68327911cc99f",
    "size": 9224104,
    "url": "https://api.github.com/repos/scuba75/swgoh-gamedata/contents/Loc_ENG_US.txt.json?ref=main",
    "html_url": "https://github.com/scuba75/swgoh-gamedata/blob/main/Loc_ENG_US.txt.json",
    "git_url": "https://api.github.com/repos/scuba75/swgoh-gamedata/git/blobs/2540cba2b4cec3c862a4f5af40e68327911cc99f",
    "download_url": "https://raw.githubusercontent.com/scuba75/swgoh-gamedata/main/Loc_ENG_US.txt.json",
    "type": "file",
    "_links": {
        "self": "https://api.github.com/repos/scuba75/swgoh-gamedata/contents/Loc_ENG_US.txt.json?ref=main",
        "git": "https://api.github.com/repos/scuba75/swgoh-gamedata/git/blobs/2540cba2b4cec3c862a4f5af40e68327911cc99f",
        "html": "https://github.com/scuba75/swgoh-gamedata/blob/main/Loc_ENG_US.txt.json"
    }
}
```
the download_url can be used with an api call to get the file contents

Please read about the rate limits here:
https://docs.github.com/en/rest/overview/resources-in-the-rest-api?apiVersion=2022-11-28#rate-limiting

The data updates are made via this https://github.com/scuba75/gamedatasync
