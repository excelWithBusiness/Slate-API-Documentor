# Playlist

## FetchAllPlaylists

```shell
curl --data-binary '{"id":"5", "method":"playlist.FetchAllPlaylists", "jsonrpc":"2.0"}'
  -H 'Authorization: Bearer jwt_access_token'
  -H 'content-type:application/json;'
```

> The above command returns JSON structured like this:

```json
{
	"jsonrpc": "2.0",
	"result": [{
		"id": "19",
		"name": "Using Financials",
		"type": "competency",
		"typeExtra": [{
			"id": 19,
			"name": "Using Financials"
		}],
		"laList": {
			"0": {
				"id": 958
				"hashID": "2096012a912d5d8d7a9501dbf706c8df6df03803",
				"title": "A rare interview with the mathematician who cracked Wall Street",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "82800",
				"lengthLabel": "23 hours ",
				"summaryUrl": "18-a-rare-interview-with-the-mathematician-who-cracked-wall-street",
				"directUrl": "https://www.ted.com/talks/jim_simons_a_rare_interview_with_the_mathematician_who_cracked_wall_street",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 19,
					"name": "Using Financials"
				}]
			},
			"1": {
				"id": 419,
				"hashID": "9173522e110a0345256a504274efe7ec43ca7e40",
				"title": "The surprisingly logical minds of babies",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "72000",
				"lengthLabel": "20 hours ",
				"summaryUrl": "187-the-surprisingly-logical-minds-of-babies",
				"directUrl": "https://www.ted.com/talks/laura_schulz_the_surprisingly_logical_minds_of_babies",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 12,
					"name": "Problem Solving \u0026 Decision Making"
				}]
			}
		}
	}, {
		"id": "12",
		"name": "Personal Development",
		"type": "group",
		"typeExtra": [{
			"id": 11,
			"name": "Personal Development"
		}],
		"laList": {
			"0": {
				"id": 8995,
				"hashID": "c872a5d2f4cabfa88149b03137896bb53279712e",
				"title": "How to Run a Brainstorming Session",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Article",
				"lengthSeconds": "21600",
				"lengthLabel": "6 hours ",
				"summaryUrl": "107-how-to-run-a-brainstorming-session",
				"directUrl": "http://www.inc.com/guides/2010/11/how-to-run-a-brainstorming-session.html",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 32,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 1,
					"name": "Planning \u0026 Organizing"
				}]
			}
		}

	}],
	"id": "5"
}
```

Returns a user’s playlists (competency, group, favourite, bifrost) in order.

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
limit (optional) | integer | number of playlists (default limit is 20| maximum limit is 50)
offset (optional) | integer | starting from

<aside class="success">
Returns — Matrix of Playlist Models - all playlists belonging to a user grouped by types
</aside>

### Errors

Error Code | Meaning
---------- | -------
-32603 | Internal Server Error
-32003 | Mandatory JWT Claim missing
-32600 | The JSON sent is not a valid Request object
-32605 | No playlists found

## FetchFavouritePlaylist

```shell
curl --data-binary '{"id":"5","method":"playlist.FetchFavouritePlaylist","jsonrpc": "2.0"}'
  -H 'Authorization: Bearer jwt_access_token'
  -H 'content-type:application/json;'
```

> The above command returns JSON structured like this:

```json
{
	"jsonrpc": "2.0",
	"result": {
		"id": "",
		"name": "Favourites",
		"type": "favourite",
		"typeExtra": [{
			"id": 1,
			"name": "Planning \u0026 Organizing"
		}, {
			"id": 4,
			"name": "Productivity"
		}],
		"laList": {
			"0": {
				"id": 319,
				"hashID": "48abb63828ef165a3c95913c3e106e78a1aa6b97",
				"title": "To-Do Lists Don't Work",
				"description": "\u003cp\u003eMarkovitz uses research to explain why to-do lists don’t work and presents a case for using our calendars - the best measure of our capacity - as a means for project management and becoming more productive. He proposes “living in your calendar” as a solution.\u003c/p\u003e\n",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Article",
				"lengthSeconds": "18000",
				"lengthLabel": "5 hours ",
				"summaryUrl": "10-to-do-lists-dont-work",
				"directUrl": "https://hbr.org/2012/01/to-do-lists-dont-work",
				"isFavourite": true,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": {
					"String": "",
					"Valid": false
				},
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 31,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 1,
					"name": "Planning \u0026 Organizing"
				}, {
					"id": 4,
					"name": "Productivity"
				}]
			}
		}
	},
	"id": "5"
}
```

Retrieve the user’s favourite assets playlist.

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

<aside class="notice"><code>No parameters</code></aside>

<aside class="success">
Returns — Playlist Model - a user’s playlist of  assets marked as favourite
</aside>

### Errors

Error Code | Meaning
---------- | -------
-32603 | Internal Server Error
-32003 | Mandatory JWT Claim missing
-32600 | The JSON sent is not a valid Request object
-32605 | Playlists not found

## FetchCompetencyPlaylists

```shell
curl --data-binary '{"id":"5", "method":"playlist.FetchCompetencyPlaylists", "jsonrpc":"2.0"}'
  -H 'Authorization: Bearer jwt_access_token'
  -H 'content-type:application/json;'
```

> The above command returns JSON structured like this:

```json
{
	"jsonrpc": "2.0",
	"result": [{
		"id": "19",
		"name": "Using Financials",
		"type": "competency",
		"typeExtra": [{
			"id": 19,
			"name": "Using Financials"
		}],
		"laList": {
			"0": {
				"id": 675,
				"hashID": "14b5221d04bb0041bcc8b11f8d668bb323bb6c6c",
				"title": "A rare interview with the mathematician who cracked Wall Street",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "82800",
				"lengthLabel": "23 hours ",
				"summaryUrl": "18-a-rare-interview-with-the-mathematician-who-cracked-wall-street",
				"directUrl": "https://www.ted.com/talks/jim_simons_a_rare_interview_with_the_mathematician_who_cracked_wall_street",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 19,
					"name": "Using Financials"
				}]
			},
			"1": {
				"id": 1809,
				"hashID": "9bd340ccc5a43eb9d583efe4e094d2851c402c3e",
				"title": "The surprisingly logical minds of babies",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "72000",
				"lengthLabel": "20 hours ",
				"summaryUrl": "187-the-surprisingly-logical-minds-of-babies",
				"directUrl": "https://www.ted.com/talks/laura_schulz_the_surprisingly_logical_minds_of_babies",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 12,
					"name": "Problem Solving \u0026 Decision Making"
				}]
			}
		}
	}, {
		"id": "12",
		"name": "Personal Development",
		"type": "competency",
		"typeExtra": [{
			"id": 11,
			"name": "Personal Development"
		}],
		"laList": {
			"0": {
				"id": 1907,
				"hashID": "0134e6775690dd572da42e0981874a8f24a6d292",
				"title": "How to Run a Brainstorming Session",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Article",
				"lengthSeconds": "21600",
				"lengthLabel": "6 hours ",
				"summaryUrl": "107-how-to-run-a-brainstorming-session",
				"directUrl": "http://www.inc.com/guides/2010/11/how-to-run-a-brainstorming-session.html",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 32,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 1,
					"name": "Planning \u0026 Organizing"
				}]
			}
		}

	}],
	"id": "5"
}
```

Retrieve a user’s list of competency playlists.

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
limit (optional) | integer | number of playlists (default limit is 20| maximum limit is 50)
offset (optional) | integer | starting from

<aside class="success">
Returns - List of Playlist Models - a user’s playlists generated for the organisation’s competencies
</aside>

### Errors

Error Code | Meaning
---------- | -------
-32603 | Internal Server Error
-32003 | Mandatory JWT Claim missing
-32600 | The JSON sent is not a valid Request object
-32605 | No playlists found

## FetchCompetencyPlaylist

```shell
curl --data-binary '{"id":"5", "method":"playlist.FetchCompetencyPlaylist", "params":{"id":"1"}, "jsonrpc":"2.0"}'
  -H 'Authorization: Bearer jwt_access_token'
  -H 'content-type:application/json;'
```

> The above command returns JSON structured like this:

```json
{
	"jsonrpc": "2.0",
	"result": {
		"id": "1",
		"name": "Planning \u0026 Organizing",
		"type": "competency",
		"typeExtra": [{
			"id": 1,
			"name": "Planning \u0026 Organizing"
		}],
		"laList": {
			"0": {
				"id": 649,
				"hashID": "5d1bf4482e667ffd8fc1fb60287b75f4a06655e6",
				"title": "Multi-tasking: you're making yourself slower and dumber",
				"description": "\u003cp\u003eDoing two things at once is actually a very bad idea. Your productivity drops by 40%. By focussing on a single task and clustering various smaller ones you become less distracted, less stressed and more productive.\u003c/p\u003e\n",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Podcast",
				"lengthSeconds": "14400",
				"lengthLabel": "4 hours ",
				"summaryUrl": "1-multi-tasking-youre-making-yourself-slower-and-dumber",
				"directUrl": "https://www.bbc.co.uk/programmes/p047v0xc",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 4,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 1,
					"name": "Planning \u0026 Organizing"
				}, {
					"id": 4,
					"name": "Productivity"
				}]
			},
			"1": {
				"id": 1140,
				"hashID": "65e6cfe5ae4c21a885e033ae4c9484945aec72cf",
				"title": "To-Do Lists Don't Work",
				"description": "\u003cp\u003eMarkovitz uses research to explain why to-do lists don’t work and presents a case for using our calendars - the best measure of our capacity - as a means for project management and becoming more productive. He proposes “living in your calendar” as a solution.\u003c/p\u003e\n",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Article",
				"lengthSeconds": "18000",
				"lengthLabel": "5 hours ",
				"summaryUrl": "10-to-do-lists-dont-work",
				"directUrl": "https://hbr.org/2012/01/to-do-lists-dont-work",
				"isFavourite": true,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 31,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 1,
					"name": "Planning \u0026 Organizing"
				}, {
					"id": 4,
					"name": "Productivity"
				}]
			}
		}
	},
	"id": "5"
}
```

Returns a specific competency playlist for a user.

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
id | string | the playlist's identifier

<aside class="success">
Returns - Playlist Model - specific competency playlist
</aside>

### Errors

Error Code | Meaning
---------- | -------
-32603 | Internal Server Error
-32003 | Mandatory JWT Claim missing
-32600 | The JSON sent is not a valid Request object
-32605 | No playlists found
-32013 | Unsupported competency

## FetchGroupPlaylists

```shell
curl --data-binary '{"id":"5", "method":"playlist.FetchGroupPlaylists", "jsonrpc":"2.0"}'
  -H 'Authorization: Bearer jwt_access_token'
  -H 'content-type:application/json;'
```

> The above command returns JSON structured like this:

```json
{
	"jsonrpc": "2.0",
	"result": [{
		"id": "19",
		"name": "Using Financials",
		"type": "group",
		"typeExtra": [{
			"id": 19,
			"name": "Using Financials"
		}],
		"laList": {
			"0": {
				"id": 650,
				"hashID": "625d63c4b26f65be6d78fe6f7d0301758d916fa5",
				"title": "A rare interview with the mathematician who cracked Wall Street",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "82800",
				"lengthLabel": "23 hours ",
				"summaryUrl": "18-a-rare-interview-with-the-mathematician-who-cracked-wall-street",
				"directUrl": "https://www.ted.com/talks/jim_simons_a_rare_interview_with_the_mathematician_who_cracked_wall_street",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 19,
					"name": "Using Financials"
				}]
			},
			"1": {
				"id": 1146,
				"hashID": "a0a7376fe143806ec851c9221e5b7da5cec0f5b7",
				"title": "The surprisingly logical minds of babies",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "72000",
				"lengthLabel": "20 hours ",
				"summaryUrl": "187-the-surprisingly-logical-minds-of-babies",
				"directUrl": "https://www.ted.com/talks/laura_schulz_the_surprisingly_logical_minds_of_babies",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 12,
					"name": "Problem Solving \u0026 Decision Making"
				}]
			}
		}
	}, {
		"id": "12",
		"name": "Personal Development",
		"type": "group",
		"typeExtra": [{
			"id": 11,
			"name": "Personal Development"
		}],
		"laList": {
			"0": {
				"id": 626,
				"hashID": "b7b94f753b3dc905ae0d57acc24624d06b1be883",
				"title": "How to Run a Brainstorming Session",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Article",
				"lengthSeconds": "21600",
				"lengthLabel": "6 hours ",
				"summaryUrl": "107-how-to-run-a-brainstorming-session",
				"directUrl": "http://www.inc.com/guides/2010/11/how-to-run-a-brainstorming-session.html",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 32,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 1,
					"name": "Planning \u0026 Organizing"
				}]
			}
		}

	}],
	"id": "5"
}
```

Retrieve a user’s list of group playlists.

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
limit (optional) | integer | number of playlists (default limit is 20| maximum limit is 50)
offset (optional) | integer | starting from

<aside class="success">
Returns - List of Playlist Models - a user’s group afferent playlists
</aside>

### Errors

Error Code | Meaning
---------- | -------
-32603 | Internal Server Error
-32003 | Mandatory JWT Claim missing
-32600 | The JSON sent is not a valid Request object
-32605 | No playlists found

## FetchNexRexPlaylists

```shell
curl --data-binary '{"id":"5", "method":"playlist.FetchNexRexPlaylists", "jsonrpc":"2.0"}'
  -H 'Authorization: Bearer jwt_access_token'
  -H 'content-type:application/json;'
```

> The above command returns JSON structured like this:

```json
{
	"jsonrpc": "2.0",
	"result": [{
		"id": "19",
		"name": "Editor's picks",
		"type": "nexRex",
		"typeExtra": [{
			"id": 19,
			"name": "Editor's picks"
		}],
		"laList": {
			"0": {
				"id": 650,
				"hashID": "625d63c4b26f65be6d78fe6f7d0301758d916fa5",
				"title": "A rare interview with the mathematician who cracked Wall Street",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "82800",
				"lengthLabel": "23 hours ",
				"summaryUrl": "18-a-rare-interview-with-the-mathematician-who-cracked-wall-street",
				"directUrl": "https://www.ted.com/talks/jim_simons_a_rare_interview_with_the_mathematician_who_cracked_wall_street",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 19,
					"name": "Using Financials"
				}]
			},
			"1": {
				"id": 1146,
				"hashID": "a0a7376fe143806ec851c9221e5b7da5cec0f5b7",
				"title": "The surprisingly logical minds of babies",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "72000",
				"lengthLabel": "20 hours ",
				"summaryUrl": "187-the-surprisingly-logical-minds-of-babies",
				"directUrl": "https://www.ted.com/talks/laura_schulz_the_surprisingly_logical_minds_of_babies",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 12,
					"name": "Problem Solving \u0026 Decision Making"
				}]
			}
		}
	}, {
		"id": "12",
		"name": "What should I learn next",
		"type": "nexRex",
		"typeExtra": [{
			"id": 11,
			"name": "What should I learn next"
		}],
		"laList": {
			"0": {
				"id": 626,
				"hashID": "b7b94f753b3dc905ae0d57acc24624d06b1be883",
				"title": "How to Run a Brainstorming Session",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Article",
				"lengthSeconds": "21600",
				"lengthLabel": "6 hours ",
				"summaryUrl": "107-how-to-run-a-brainstorming-session",
				"directUrl": "http://www.inc.com/guides/2010/11/how-to-run-a-brainstorming-session.html",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 32,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 1,
					"name": "Planning \u0026 Organizing"
				}]
			}
		}

	}],
	"id": "5"
}
```

Retrieve a user’s list of nexrex playlists.

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
limit (optional) | integer | number of playlists (default limit is 20| maximum limit is 50)
offset (optional) | integer | starting from

<aside class="success">
Returns - List of Playlist Models - a user’s nexrex playlists
</aside>

### Errors

Error Code | Meaning
---------- | -------
-32603 | Internal Server Error
-32003 | Mandatory JWT Claim missing
-32600 | The JSON sent is not a valid Request object
-32605 | No playlists found

## FetchBifrostPlaylists

```shell
curl --data-binary '{"id":"5", "method":"playlist.FetchBifrostPlaylists", "jsonrpc":"2.0"}'
  -H 'Authorization: Bearer jwt_access_token'
  -H 'content-type:application/json;'
```

> The above command returns JSON structured like this:

```json
{
	"jsonrpc": "2.0",
	"result": [{
		"id": "19",
		"name": "Using Financials",
		"type": "algorithm",
		"typeExtra": [{
			"id": 19,
			"name": "Using Financials"
		}],
		"laList": {
			"0": {
				"id": 159,
				"hashID": "5651fa735f3a7147b3fa034a5d34d7c4babfc8fe",
				"title": "A rare interview with the mathematician who cracked Wall Street",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "82800",
				"lengthLabel": "23 hours ",
				"summaryUrl": "18-a-rare-interview-with-the-mathematician-who-cracked-wall-street",
				"directUrl": "https://www.ted.com/talks/jim_simons_a_rare_interview_with_the_mathematician_who_cracked_wall_street",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 19,
					"name": "Using Financials"
				}]
			},
			"1": {
				"id": 885,
				"hashID": "fdad1c42f572206d46c3ff3911435834c9a0b848",
				"title": "The surprisingly logical minds of babies",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "72000",
				"lengthLabel": "20 hours ",
				"summaryUrl": "187-the-surprisingly-logical-minds-of-babies",
				"directUrl": "https://www.ted.com/talks/laura_schulz_the_surprisingly_logical_minds_of_babies",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 12,
					"name": "Problem Solving \u0026 Decision Making"
				}]
			}
		}
	}, {
		"id": "12",
		"name": "Personal Development",
		"type": "algorithm",
		"typeExtra": [{
			"id": 11,
			"name": "Personal Development"
		}],
		"laList": {
			"0": {
				"id": 8928,
				"hashID": "6aa268246e373578b578f0e10bd24cdcd9d8c4b5",
				"title": "How to Run a Brainstorming Session",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Article",
				"lengthSeconds": "21600",
				"lengthLabel": "6 hours ",
				"summaryUrl": "107-how-to-run-a-brainstorming-session",
				"directUrl": "http://www.inc.com/guides/2010/11/how-to-run-a-brainstorming-session.html",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 32,
					"name": "",
					"image": "",
				    "favicon": "",
				},
				"competencyList": [{
					"id": 1,
					"name": "Planning \u0026 Organizing"
				}]
			}
		}

	}],
	"id": "5"
}
```

Retrieve a user’s list of bifrost playlists.

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
limit (optional) | integer | number of playlists (default limit is 20| maximum limit is 50)
offset (optional) | integer | starting from

<aside class="success">
Returns - List of Playlist Models - a user’s ML aglorithm generated playlists
</aside>

### Errors

Error Code | Meaning
---------- | -------
-32603 | Internal Server Error
-32003 | Mandatory JWT Claim missing
-32600 | The JSON sent is not a valid Request object
-32605 | No playlists found

## FetchPlaylistsByTypes

```shell
curl --data-binary '{"id":"5", "method":"playlist.FetchPlaylistsByTypes", "params":{"types":["competency", "group"]}, "jsonrpc":"2.0"}'
  -H 'Authorization: Bearer jwt_access_token'
  -H 'content-type:application/json;'
```

> The above command returns JSON structured like this:

```json
{
	"jsonrpc": "2.0",
	"result": [{
		"id": "19",
		"name": "Using Financials",
		"type": "competency",
		"typeExtra": [{
			"id": 19,
			"name": "Using Financials"
		}],
		"laList": {
			"0": {
				"id": 8929,
				"hashID": "094bb658b5dfb922e1d495574652b75a3d7d77e3",
				"title": "A rare interview with the mathematician who cracked Wall Street",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "82800",
				"lengthLabel": "23 hours ",
				"summaryUrl": "18-a-rare-interview-with-the-mathematician-who-cracked-wall-street",
				"directUrl": "https://www.ted.com/talks/jim_simons_a_rare_interview_with_the_mathematician_who_cracked_wall_street",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 19,
					"name": "Using Financials"
				}]
			},
			"1": {
				"id": 8993,
				"hashID": "26c84a23c24d080e091d3057c5cd6055b7547044",
				"title": "The surprisingly logical minds of babies",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Video",
				"lengthSeconds": "72000",
				"lengthLabel": "20 hours ",
				"summaryUrl": "187-the-surprisingly-logical-minds-of-babies",
				"directUrl": "https://www.ted.com/talks/laura_schulz_the_surprisingly_logical_minds_of_babies",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 56,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 12,
					"name": "Problem Solving \u0026 Decision Making"
				}]
			}
		}
	}, {
		"id": "12",
		"name": "Personal Development",
		"type": "group",
		"typeExtra": [{
			"id": 11,
			"name": "Personal Development"
		}],
		"laList": {
			"0": {
				"id": 2782,
				"hashID": "7d2f4b827c1404f2e456e4d3279da66f186bc1df",
				"title": "How to Run a Brainstorming Session",
				"description": "",
				"mainImage": "",
				"screenshotImage": "",
				"screenshotImageMobile": "",
				"typeLabel": "Article",
				"lengthSeconds": "21600",
				"lengthLabel": "6 hours ",
				"summaryUrl": "107-how-to-run-a-brainstorming-session",
				"directUrl": "http://www.inc.com/guides/2010/11/how-to-run-a-brainstorming-session.html",
				"isFavourite": false,
				"launched": false,
				"dismissed": false,
				"completed": false,
				"notes": "",
				"restrictionCode": "free",
				"restrictionLabel": "Free",
				"provider": {
					"id": 32,
					"name": "",
					"image": ""
				},
				"competencyList": [{
					"id": 1,
					"name": "Planning \u0026 Organizing"
				}]
			}
		}

	}],
	"id": "5"
}
```

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
types | array of strings | the types for the desired playlists(competency, group, user, algorithm, nexRex)
limit (optional) | integer | number of playlists (default limit is 20| maximum limit is 50)
offset (optional) | integer | starting from

<aside class="success">
Returns - List of Playlist Models - a user’s specific type playlists
</aside>

### Errors

Error Code | Meaning
---------- | -------
-32603 | Internal Server Error
-32003 | Mandatory JWT Claim missing
-32600 | The JSON sent is not a valid Request object
-32605 | No playlists found
-32015 | Non-existing playlist type

## FetchPlaylistByID

```shell
```

> The above command returns JSON structured like this:

```json
{
}
```

<aside class="warning">
Method not yet implemented
</aside>

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
id | string | the playlist's identifier

<aside class="success">
Returns - Playlist Model - specific playlist
</aside>

## ArePlaylistsGenerated

```shell
```

> The above command returns JSON structured like this:

```json
{
}
```

<aside class="warning">
Method not yet implemented
</aside>

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

<aside class="notice"><code>No parameters</code></aside>

<aside class="success">
Returns - Boolean - flag if any playlists of any type have been generated for the user
</aside>

## GetAsset

```shell
curl --data-binary '{"id":"5","method":"playlist.GetAsset","params":{"id":319},"jsonrpc": "2.0"}'
  -H 'Authorization: Bearer jwt_access_token'
  -H 'content-type:application/json;'
```

> The above command returns JSON structured like this:

```json
{
	"jsonrpc": "2.0",
	"result": {
		"id": 319,
		"hashID": "48abb63828ef165a3c95913c3e106e78a1aa6b97",
		"title": "To-Do Lists Don't Work",
		"description": "\u003cp\u003eMarkovitz uses research to explain why to-do lists don’t work and presents a case for using our calendars - the best measure of our capacity - as a means for project management and becoming more productive. He proposes “living in your calendar” as a solution.\u003c/p\u003e\n",
		"mainImage": "",
		"screenshotImage": "",
		"screenshotImageMobile": "",
		"typeLabel": "Article",
		"lengthSeconds": "18000",
		"lengthLabel": "5 hours ",
		"summaryUrl": "10-to-do-lists-dont-work",
		"directUrl": "https://hbr.org/2012/01/to-do-lists-dont-work",
		"isFavourite": true,
		"launched": false,
		"dismissed": false,
		"completed": false,
		"notes": {
			"String": "",
			"Valid": false
		},
		"restrictionCode": "free",
		"restrictionLabel": "Free",
		"provider": {
			"id": 31,
			"name": "",
			"image": ""
		},
		"competencyList": [{
			"id": 1,
			"name": "Planning \u0026 Organizing"
		}, {
			"id": 4,
			"name": "Productivity"
		}]
	},
	"id": "5"
}
```

Retrieve a given asset

### HTTP Request

`POST https://api.sec.filtered.com/v2/jsonrpc/mgp`

### Parameters

Parameter | Type | Description
--------- | ------- | -----------
id | string | the asset's identifier

<aside class="success">
Returns — Learning Asset Model - specific asset
</aside>

### Errors

Error Code | Meaning
---------- | -------
-32603 | Internal Server Error
-32003 | Mandatory JWT Claim missing
-32600 | The JSON sent is not a valid Request object
-32014 | Unsupported asset