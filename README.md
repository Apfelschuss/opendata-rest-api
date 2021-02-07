# Testing realtime voting data with Postman

On [opendata.swiss](https://opendata.swiss/de/dataset/echtzeitdaten-am-abstimmungstag-zu-eidgenoessischen-abstimmungsvorlagen) realtime voting data can be grabbed via REST API. The database is maintained by the [Federal Statistical Office (FSO)](https://www.bfs.admin.ch/bfs/en/home.html).

This repository provides a Postman collection with some data requests which should help exploring and understanding the API.

## Installing Postman

1. Postman is available for Windows, macOS and Linux. Go to [postman.com/downloads](https://www.postman.com/downloads/) and download and install.

2. Open Postman and click import as shown red in the screenshot below. Import `Opendata_Realtime_Voting_Data_REST_API.postman_collection.json` from [this repository](Opendata_Realtime_Voting_Data_REST_API.postman_collectionjson).

![Import collection](screenshots/postman_import_collection.png)

> There is also a [Postam team project](https://apfelschuss.postman.co/). Drop an email to apfelschuss.io@gmail.com if you want join.

## Working with the API

The entry point for all results (all past and the upcomming vote) can be accessed via following URL:

```
https://opendata.swiss/api/3/action/package_show?id=echtzeitdaten-am-abstimmungstag-zu-eidgenoessischen-abstimmungsvorlagen
```

The URL above refers for every federal voting day to a voting specific url. Note that past (completed) votes data is hosted on bfs.admin.ch wheras upcomming votes are hosted on Amazon Web Services. See following example that represent the state of February 2021.

### Example past voting

**result > resources > display_name > de:** Volksabstimmung vom 29.11.2020– Eidgenössische Vorlagen  
**result > resources > id:** b7ff742d-5a9a-4e79-941e-906a74d59d23  
```
https://www.bfs.admin.ch/bfsstatic/dam/assets/14843937/master
```

### Example upcomming voting

**result > resources > display_name > de:** Volksabstimmung vom 07.03.2021– Eidgenössische Vorlagen  
**result > resources > id:** 1aaf2ca1-5b8c-4194-906a-45c1d2bde04a  
```
https://app-prod-static-voteinfo.s3.eu-central-1.amazonaws.com/v1/ogd/sd-t-17-02-20210307-eidgAbstimmung.json
```