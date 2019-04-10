# portable-workstation

## Current Todo

- Make sure all objects of aliases array has "use" property
- Add variable to config conditionally, based on "use" array

## Roadmap

- Automatically create shortcuts
- Download binaries and unpackage them automatically
- Automatically look for applications and stuff under path - add them automatically
- create cli to launch apps from and do more stuff
- make properties of var better named
- create function that autofills optional and required parameters w/ default value
- meta bootstrap exec w/ cmd
- make piping actually work with print statements
- modify scheme such that the following can be used

```json
"binary": {
  "path": "../_bin",
  "exclude": "glob",
  "include": ["glob1", "glob2"]
}
```

## Schema for portable.config.json

will have actual good documentation later

```json
{
  "config": {
    "name": "Edwin Kofler", // doesn't do anything yet
    "relativePathToBinary": "../_binary",
    "relativePathToCmderConfig": "../cmder/config",
    "relativePathToApplications": "../",
  },
  "applications": [
    {
      "name": "Cmder",
      "path": "cmder/Cmder"
    },
    {
      "name": "QuickLook",
      "path": "quicklook/QuickLook",
      "launch": "auto" // optional. Launch keywords include auto, prompt, and autoForce. "prompt" is default. autoForce launches the app even if it already exists
    }
  ],
    "paths": [
    {
      "name": "cmake", // optional. Just for better logging in output
      "path": "cmake/bin"
    }
  ],
  "variables": [
    {
      "name": "six",
      "value": "6"
    },
    {
      "name": "seven",
      "value": "7"
    }
  ],
  "aliases": [
    {
      "name": "gs",
      "value": "git status"
    }
  ]
}
```
