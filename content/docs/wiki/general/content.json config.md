---
title: "content.json config"
description: "Info about the content json file"
---
# content.json
Each folder on the Toniebox contains a JSON-file whose name consists of the Tonies UID like `500304E0.json`. This file sits alongside the actual audio content and contains its configuration.

Usually it looks like the following:

```
{
	"live":	false,
	"nocloud":	false,
	"source":	"",
	"skip_seconds":	0,
	"cache":	false,
	"cloud_ruid":	"",
	"cloud_auth":	"",
	"cloud_override":	false,
	"tonie_model":	"",
	"_version":	5
}
```

## Specification
| Option         | Type   | Default | Description |
|----------------|--------|---------|-------------|
| live           | bool   | `false` |             |
| nocloud        | bool   | `false` | Do not sync the directory with the boxine cloud |
| source         | str    | `""`    |             |
| skip_seconds   | uint32 | `0`     | Skips the audio by given seconds at the beginning |
| cache          | bool   | `false` |             |
| cloud_ruid     | str    | `""`    | Contains the ID of the given Tonie. This is needed to request the content from boxine cloud. You can enable `Dump rUID/auth` in teddycloud to fill in the ruid when placing a Tonie. |
| cloud_auth     | str    | `""`    | Contains the content password of the given Tonie. This is needed to request the content from boxine cloud. You can enable `Dump rUID/auth` in teddycloud to fill in the password when placing a Tonie. |
| cloud_override | bool   | `false` |             |
| tonie_model    | str    | `""`    |             |
| _version       | uint32 | `5`     |             |

## Examples

* Custom audiobooks that you added to Teddycloud (no official Tonies) typically will have `nocloud` enabled
* You can download content right from an URL by setting the `source`. In combination with `nocloud` you can easily set up custom content. The custom content will be downloaded to your Toniebox when triggering a content update (long press one of the volume-ears).