# Get Data from a Specific List
## Description
This API is used to retrieve detailed information for all individuals within a specified list. You can define the type of list to query, and the API will return comprehensive details for every person in that list.

## Request Parameters

| Parameter   | Required   | Description                                 |
|-------------|------------|---------------------------------------------|
| flist       | Yes        |Specifies the type of list to query (e.g., `vip`, `denial`).  |

## Response Parameters

| Parameter          | Type    | Description                           |
|--------------------|---------|---------------------------------------|
| `FACE_COUNT`       | int     | Total number of faces in the list.                                           |
| `INFORMATION`      | array   | An array containing detailed information of individuals in the list.         |
| `INDEX`            | int     | Index number of the individual in the list.                                  |
| `FR_UPDATE_DATE`   | string  | The date and time the individual's data was last updated.                    |
| `FR_LIST_TYPE`     | string  | The type of list the individual belongs to (e.g., `vip`, `denial`, `watch`). |
| `FR_BMP`           | string  | Unique identifier for the individual's image file.                           |
| `FR_SCHEDULE_S`    | string  | Start time of the individual's schedule, if applicable.                      |
| `FR_SCHEDULE_E`    | string  | End time of the individual's schedule, if applicable.                        |
| `FR_OTHER`         | string  | Additional information about the individual, if any.                         |
| `FR_DETECT_ENDTIME`| string  | Time the individual was last detected, if applicable.                        |
| `FR_FACE_NAME`     | string  | Internal face ID or name associated with the individual.                     |
| `FR_LAST_NAME`     | string  | The last name of the individual (if available).                              |
| `FR_FIRST_NAME`    | string  | The first name of the individual (if available).                             |
| `FR_SCORE`         | string  | Face recognition score indicating the match confidence.                      |
| `LIST_TYPE`        | string  | Type of the list from which the data is returned (e.g., `log`).              |

## Syntax

### Get Face Info from Log List
```bash
http://<serverIP:8592>/face_list?flist=log
```
### Get Face Info from Watch List
```bash
http://<serverIP:8592>/face_list?flist=watch
```
### Get Face Info from VIP List
```bash
http://<serverIP:8592>/face_list?flist=vip
```
### Get Face Info from Denial List
```bash
http://<serverIP:8592>/face_list?flist=denial
```
## Response Example
### Response Example for Log List
```json=
{
    "FACE_COUNT": 3,
    "INFORMATION": [
        {
            "INDEX": 1,
            "FR_UPDATE_DATE": "2024-10-23 11:39:38",
            "FR_LIST_TYPE": "vip",
            "FR_BMP": "2024_10_23_11_39_38_849_00119",
            "FR_SCHEDULE_S": "",
            "FR_SCHEDULE_E": "",
            "FR_OTHER": "臺中市豐原區和平街75號3樓之3",
            "FR_DETECT_ENDTIME": "",
            "FR_FACE_NAME": "00119",
            "FR_LAST_NAME": "湯",
            "FR_FIRST_NAME": "堇暉",
            "FR_SCORE": "98.8"
        },
        {
            "INDEX": 2,
            "FR_UPDATE_DATE": "2024-10-23 11:39:38",
            "FR_LIST_TYPE": "watch",
            "FR_BMP": "2024_10_23_11_39_38_849_00118",
            "FR_SCHEDULE_S": "",
            "FR_SCHEDULE_E": "",
            "FR_OTHER": "新竹市北區南大路74號6樓之6",
            "FR_DETECT_ENDTIME": "",
            "FR_FACE_NAME": "00118",
            "FR_LAST_NAME": "顏",
            "FR_FIRST_NAME": "鷺黛",
            "FR_SCORE": "99.0"
        },
        {
            "INDEX": 3,
            "FR_UPDATE_DATE": "2024-10-23 11:39:38",
            "FR_LIST_TYPE": "watch",
            "FR_BMP": "2024_10_23_11_39_38_849_00117",
            "FR_SCHEDULE_S": "",
            "FR_SCHEDULE_E": "",
            "FR_OTHER": "彰化縣鹿港鎮南橋巷6號6樓之15",
            "FR_DETECT_ENDTIME": "",
            "FR_FACE_NAME": "00117",
            "FR_LAST_NAME": "姚",
            "FR_FIRST_NAME": "彤若",
            "FR_SCORE": "99.4"
            }
    ],
    "LIST_TYPE": "log"
}
```
### Response Example for Watch List
```json=
{
    "FACE_COUNT": 2,
    "INFORMATION": [
        {
            "INDEX": 1,
            "FR_UPDATE_DATE": "2024-10-23 10:20:32",
            "FR_LIST_TYPE": "watch",
            "FR_BMP": "2024_10_23_10_20_32_544_00107",
            "FR_SCHEDULE_S": "00:00",
            "FR_SCHEDULE_E": "23:59",
            "FR_OTHER": "新竹市東區東進路100號",
            "FR_DETECT_ENDTIME": "2044-12-01_23:59",
            "FR_FACE_NAME": "00107",
            "FR_LAST_NAME": "陳",
            "FR_FIRST_NAME": "冠禎",
            "FR_SCORE": "0.00"
        },
        {
            "INDEX": 2,
            "FR_UPDATE_DATE": "2024-10-23 10:20:32",
            "FR_LIST_TYPE": "watch",
            "FR_BMP": "2024_10_23_10_20_32_544_00108",
            "FR_SCHEDULE_S": "00:00",
            "FR_SCHEDULE_E": "23:59",
            "FR_OTHER": "屏東縣屏東市中山路23號11樓",
            "FR_DETECT_ENDTIME": "2044-12-01_23:59",
            "FR_FACE_NAME": "00108",
            "FR_LAST_NAME": "孫",
            "FR_FIRST_NAME": "依妍",
            "FR_SCORE": "0.00"
        }
    ],
    "LIST_TYPE": "watch"
}
```
### Response Example for VIP List
```json=
{
    "FACE_COUNT": 1,
    "INFORMATION": [
        {
            "INDEX": 1,
            "FR_UPDATE_DATE": "2024-10-23 10:48:29",
            "FR_LIST_TYPE": "vip",
            "FR_BMP": "2024_10_23_10_20_32_544_00113",
            "FR_SCHEDULE_S": "00:00",
            "FR_SCHEDULE_E": "23:59",
            "FR_OTHER": "苗栗縣頭屋鄉中山街91號之10",
            "FR_DETECT_ENDTIME": "2044-12-01_23:59",
            "FR_FACE_NAME": "00113",
            "FR_LAST_NAME": "溫",
            "FR_FIRST_NAME": "寧歆",
            "FR_SCORE": "0.00"
        }
    ],
    "LIST_TYPE": "vip"
}
```
### Response Example for Denial List
```json=
{
    "FACE_COUNT": 2,
    "INFORMATION": [
        {
            "INDEX": 1,
            "FR_UPDATE_DATE": "2024-10-23 10:52:22",
            "FR_LIST_TYPE": "denial",
            "FR_BMP": "2024_10_23_10_20_31_544_00105",
            "FR_SCHEDULE_S": "00:00",
            "FR_SCHEDULE_E": "23:59",
            "FR_OTHER": "澎湖縣馬公市宅腳嶼96號6樓之1",
            "FR_DETECT_ENDTIME": "2044-12-01_23:59",
            "FR_FACE_NAME": "00105",
            "FR_LAST_NAME": "胡",
            "FR_FIRST_NAME": "謹霜",
            "FR_SCORE": "0.00"
        },
        {
            "INDEX": 2,
            "FR_UPDATE_DATE": "2024-10-23 10:52:31",
            "FR_LIST_TYPE": "denial",
            "FR_BMP": "2024_10_23_10_20_32_544_00112",
            "FR_SCHEDULE_S": "00:00",
            "FR_SCHEDULE_E": "23:59",
            "FR_OTHER": "彰化縣北斗鎮裕後路34號",
            "FR_DETECT_ENDTIME": "2044-12-01_23:59",
            "FR_FACE_NAME": "00112",
            "FR_LAST_NAME": "陳",
            "FR_FIRST_NAME": "蕊黛",
            "FR_SCORE": "0.00"
        }
    ],
    "LIST_TYPE": "denial"
}

```
# Get Name List from a Specific List
## Description
This API is used to retrieve all names from a specified list type. By specifying the list type, the API will return only the names within that list.

## Request Parameters

| Parameter   | Required   | Description                       |
|-------------|------------|-----------------------------------|
| `flist`     | Yes        | Specifies the list type to query. |
| `namelist`  | Yes        | Indicates that only the name list will be returned. |

## Response Parameters

| Parameter       | Type   | Description                               |
|-----------------|--------|-------------------------------------------|
| `NAME_COUNT`    | int    | The total number of names in the list.    |
| `INFORMATION`   | array  | An array containing the name information. |
| `FR_LAST_NAME`  | string | The last name of the individual.          |
| `FR_FIRST_NAME` | string | The first name of the individual.         |
| `LIST_TYPE`     | string | The type of the list that is returned.    |

## Syntax
### Get All Names from Log List
```bash
http://<serverIP:8592>/face_list?flist=log&namelist
```
### Get All Names from Watch List
```bash
http://<serverIP:8592>/face_list?flist=watch&namelist
```
### Get All Names from VIP List
```bash
http://<serverIP:8592>/face_list?flist=vip&namelist
```
### Get All Names from Denial List
```bash
http://<serverIP:8592>/face_list?flist=denial&namelist
```
## Response Example
### Response Example for Log List
```json=
{
  "NAME_COUNT": 3,
  "INFORMATION": [
    { "FR_LAST_NAME": "姚", "FR_FIRST_NAME": "彤若" },
    { "FR_LAST_NAME": "湯", "FR_FIRST_NAME": "堇暉" },
    { "FR_LAST_NAME": "顏", "FR_FIRST_NAME": "鷺黛" }
  ],
  "LIST_TYPE": "log"
}

```
### Response Example for Watch List
```json=
{
  "NAME_COUNT": 2,
  "INFORMATION": [
    {
      "FR_LAST_NAME": "孫",
      "FR_FIRST_NAME": "依妍"
    },
    {
      "FR_LAST_NAME": "陳",
      "FR_FIRST_NAME": "冠禎"
    }
  ],
  "LIST_TYPE": "watch"
}

```
### Response Example for VIP List
```json=
{
  "NAME_COUNT": 1,
  "INFORMATION": [
    {
      "FR_LAST_NAME": "溫",
      "FR_FIRST_NAME": "寧歆"
    }
  ],
  "LIST_TYPE": "vip"
}

```
### Response Example for Denial List
```json=
{
  "NAME_COUNT": 2,
  "INFORMATION": [
    {
      "FR_LAST_NAME": "陳",
      "FR_FIRST_NAME": "蕊黛"
    },
    {
      "FR_LAST_NAME": "胡",
      "FR_FIRST_NAME": "謹霜"
    }
  ],
  "LIST_TYPE": "denial"
}

```
# Get a Specific Person's Information from a List by UUID
## Description
This API is used to retrieve specific information of a person from a designated list using a unique identifier (UUID). The list type and the person's UUID must be provided. Upon successful query, detailed information of the person will be returned.

## Request Parameters

| Parameter   | Required   | Description                               |
|-------------|------------|-------------------------------------------|
| select      | Yes        | Specifies the list type to query (e.g., `vip`). |
| face_name   | Yes        | Specifies the UUID of the person to query.      |

## Response Parameters

| Parameter           | Type   | Description                                           |
|---------------------|--------|-------------------------------------------------------|
| `FACE_COUNT`        | int    | The number of people in the list. (Always 1 for this query) |
| `INFORMATION`       | array  | An array containing the detailed information of the person. |
| `INDEX`             | int    | Index number.                                               |
| `FR_UPDATE_DATE`    | string | The date when the information was last updated.             |
| `FR_LIST_TYPE`      | string | The list type (e.g., `log`, `vip`, `watch`, `denial`).      |
| `FR_BMP`            | string | The file name of the person's face image.                   |
| `FR_SCHEDULE_S`     | string | Scheduled start time.                                       |
| `FR_SCHEDULE_E`     | string | Scheduled end time.                                         |
| `FR_OTHER`          | string | Other related information (e.g., address).                  |
| `FR_DETECT_ENDTIME` | string | Detection end time.                                         |
| `FR_FACE_NAME`      | string | The UUID of the person.                                     |
| `FR_LAST_NAME`      | string | The last name of the person.                                |
| `FR_FIRST_NAME`     | string | The first name of the person.                               |
| `FR_SCORE`          | float  | The face recognition score.                                 |
| `LIST_TYPE`         | string | The list type returned in the response.                     |

## Syntax

```bash
http://<serverIP:8592>/face_list?select=vip&face_name=00113
```

## Response Example

```json=
{
  "FACE_COUNT": 1,
  "INFORMATION": [
    {
      "INDEX": 1,
      "FR_UPDATE_DATE": "2024-10-17 10:48:29",
      "FR_LIST_TYPE": "vip",
      "FR_BMP": "2024_10_17_10_20_32_544_00113",
      "FR_SCHEDULE_S": "00:00",
      "FR_SCHEDULE_E": "23:59",
      "FR_OTHER": "苗栗縣頭屋鄉中山街91號之10",
      "FR_DETECT_ENDTIME": "2044-12-01_23:59",
      "FR_FACE_NAME": "00113",
      "FR_LAST_NAME": "溫",
      "FR_FIRST_NAME": "寧歆",
      "FR_SCORE": "0.00"
    }
  ],
  "LIST_TYPE": "vip"
}
```



# Get Specific Person(s)' Information from a List by Name
## Description
This API allows you to query the information of specific persons from a designated list by their names. Multiple records may be returned if more than one person matches the search criteria. You must specify the list type and provide the names of the persons to be queried. If the query is successful, the relevant information for the specified persons will be returned.

## Request Parameters

| Parameter  | Required   | Description                                     |
|------------|------------|-------------------------------------------------|
| list_type  | Yes        | Specifies the list type to query (e.g., `vip`). |
| names      | Yes        | Contains the first and last names of the persons for the query. |

## Response Parameters
| Parameter            | Type   | Description                            |
|----------------------|--------|----------------------------------------|
| `TOTAL_COUNT`        | int    | The total number of people matching the query in the list. |
| `PAGE_COUNT`         | int    | The number of people shown on the current page.            |
| `INFORMATION`        | array  | An array containing detailed information about the persons.|
| `INDEX`              | int    | Index number.                                              |
| `FR_UPDATE_DATE`     | string | The date when the information was last updated.            |
| `FR_LIST_TYPE`       | string | The list type (e.g., `vip`, `log`).                        |
| `FR_BMP`             | string | The file name of the person's face image.                  |
| `FR_SCHEDULE_S`      | string | Scheduled start time.                                      |
| `FR_SCHEDULE_E`      | string | Scheduled end time.                                        |
| `FR_OTHER`           | string | Other related information (e.g., address).                 |
| `FR_DETECT_ENDTIME`  | string | Detection end time.                                        |
| `FR_FACE_NAM`E       | string | The unique ID of the person.                               |
| `FR_LAST_NAME`       | string | The last name of the person.                               |
| `FR_FIRST_NAME`      | string | The first name of the person.                              |
| `FR_SCORE`           | float  | The face recognition score.                                |
| `LIST_TYPE`          | string | The type of the list returned.                             |

## Syntax

```bash
curl -X POST http://<serverIP:8592>/face_list_batch \
    -u "<username>:<password>" \
    -H "Content-Type: application/json" \
    -H "Cache-Control: no-cache" \
    -H "If-Modified-Since: 0" \
    -H "Expect:" \
    -d '{"list_type": "watch", "names": [{"lastName": "孫", "firstName": "依妍"}, {"lastName": "陳", "firstName": "冠禎"}]}'
```

## Response Example

```json=
{
  "TOTAL_COUNT": 11,
  "PAGE_COUNT": 2,
  "INFORMATION": [
    {
      "INDEX": 1,
      "FR_UPDATE_DATE": "2024-10-23 10:20:32",
      "FR_LIST_TYPE": "watch",
      "FR_BMP": "2024_10_23_10_20_32_544_00108",
      "FR_SCHEDULE_S": "00:00",
      "FR_SCHEDULE_E": "23:59",
      "FR_OTHER": "屏東縣屏東市中山路23號11樓",
      "FR_DETECT_ENDTIME": "2044-12-01_23:59",
      "FR_FACE_NAME": "00108",
      "FR_LAST_NAME": "孫",
      "FR_FIRST_NAME": "依妍",
      "FR_SCORE": "0.00"
    },
    {
      "INDEX": 2,
      "FR_UPDATE_DATE": "2024-10-23 10:20:32",
      "FR_LIST_TYPE": "watch",
      "FR_BMP": "2024_10_23_10_20_32_544_00107",
      "FR_SCHEDULE_S": "00:00",
      "FR_SCHEDULE_E": "23:59",
      "FR_OTHER": "新竹市東區東進路100號",
      "FR_DETECT_ENDTIME": "2044-12-01_23:59",
      "FR_FACE_NAME": "00107",
      "FR_LAST_NAME": "陳",
      "FR_FIRST_NAME": "冠禎",
      "FR_SCORE": "0.00"
    }
  ],
  "LIST_TYPE": "watch"
}

```

# Search for Specific Person Information from a List
## Description
This API allows you to search for person information in a designated list (e.g., `vip`) based on a keyword (such as a partial name). It returns detailed information of the persons that match the search criteria.

## Request Parameters

| Parameter  | Required | Description                                |
|------------|----------|--------------------------------------------|
| list_type  | Yes      | Specifies the type of list to search (e.g., `vip`). |
| search     | Yes      | The keyword used for searching names.               |

## Response Parameters

| Parameter           | Type   | Description                                        |
|---------------------|--------|----------------------------------------------------|
| `TOTAL_COUNT`       | int    | The total number of persons matching the search criteria.|
| `PAGE_COUNT`        | int    | The number of persons displayed on the current page.     |
| `INFORMATION`       | array  | An array containing detailed information of the persons. |
| `FR_INDEX`          | int    | Index number.                                            |
| `FR_UPDATE_DATE`    | string | The date when the information was last updated.          |
| `FR_LIST_TYPE`      | string | The list type (e.g., `vip`, `log`).                      |
| `FR_BMP`            | string | The file name of the person's face image.                |
| `FR_SCHEDULE_S`     | string | Scheduled start time.                                    |
| `FR_SCHEDULE_E`     | string | Scheduled end time.                                      |
| `FR_OTHER`          | string | Other related information (e.g., address).               |
| `FR_DETECT_ENDTIME` | string | Detection end time.                                      |
| `FR_FACE_NAME`      | string | The unique ID of the person.                             |
| `FR_LAST_NAME`      | string | The last name of the person.                             |
| `FR_FIRST_NAME`     | string | The first name of the person.                            |
| `FR_SCORE`          | float  | The face recognition score.                              |
| `LIST_TYPE`         | string | The type of list returned.                               |

## Syntax
```bash
curl -X POST http://<serverIP:8592>/face_search \
    -u "<username>:<password>" \
    -H "Content-Type: application/json" \
    -H "Cache-Control: no-cache" \
    -H "If-Modified-Since: 0" \
    -d '{"search":"陳","list_type":"denial"}'
```
## Response Example
```json=
{
  "TOTAL_COUNT": 5,
  "PAGE_COUNT": 1,
  "INFORMATION": [
    {
      "INDEX": 1,
      "FR_UPDATE_DATE": "2024-10-23 10:52:31",
      "FR_LIST_TYPE": "denial",
      "FR_BMP": "2024_10_23_10_20_32_544_00112",
      "FR_SCHEDULE_S": "00:00",
      "FR_SCHEDULE_E": "23:59",
      "FR_OTHER": "彰化縣北斗鎮裕後路34號",
      "FR_DETECT_ENDTIME": "2044-12-01_23:59",
      "FR_FACE_NAME": "00112",
      "FR_LAST_NAME": "陳",
      "FR_FIRST_NAME": "蕊黛",
      "FR_SCORE": "0.00"
    }
  ],
  "LIST_TYPE": "denial"
}

```

# Update Specific List Data
## Description
This API is used to update specific person data in a designated list. You can specify the list type (e.g., `watch` or `vip`) and provide detailed information for the person (such as first name, last name, schedule time, etc.) to update the record.

## Request Parameters

| Parameter             | Required | Description                                                   |
|-----------------------|----------|---------------------------------------------------------------|
| update                | Yes      | Specifies the list type to be updated (e.g., `watch`, `vip`). |
| count                 | Yes      | The number of people to be updated (usually 1).               |
| face_name             | Yes      | The person's identifier (UUID) to be updated.                 |
| face_first_name       | Yes      | The first name of the person to be updated.                   |
| face_last_name        | Yes      | The last name of the person to be updated.                    |
| face_other            | Yes      | Other relevant information to be updated (e.g., address).     |
| face_schedule_s       | Yes      | Start schedule time (Format: `HH:MM`).                        |
| face_schedule_e       | Yes      | End schedule time (Format: `HH:MM`).                          |
| face_detect_endtime   | Yes      | Detection end time (Format: `YYYY-MM-DD_HH:MM`).              |

## Response Format

- **Success**: If the update is successful, the server will return `OK`.
- **Failure**: If the update fails, the server will return `Fail`.

## Syntax
```
http://<serverIP:8592>/face_list?update=watch&count=1&face_name=00108&face_first_name=依妍&face_last_name=孫&face_other=屏東縣屏東市中山路23號11樓&face_schedule_s=00:00&face_schedule_e=23:59&face_detect_endtime=2044-12-01_23:59
```

# Delete Specific Person
## Description

This API is used to delete a specific person’s data from a designated list. You need to specify the list type (e.g., `vip` or `watch`) and provide the person's first name and last name for the deletion operation. 
**Note: All records with the same name will be removed, not just a single entry.**

## Request Parameters

| Parameter          | Required | Description                                              |
|--------------------|----------|----------------------------------------------------------|
| delete             | Yes      | Specifies the list type for deletion (e.g., `vip`, `watch`, `denial`). |
| face_first_names   | Yes      | The first name of the person to be deleted.              |
| face_last_names    | Yes      | The last name of the person to be deleted.               |

## Response Format

- **Success**: If the deletion is successful, the server will return `OK`.
- **Failure**: If the deletion fails, the server will return `Fail`.

## Syntax
```bash
http://<serverIP:8592>/face_list?delete=denial&face_first_names=蕊黛&face_last_names=陳
```


# Clean Specific List
## Description

This API is used to clear the data of a specified list. You can specify the type of list to be cleared, such as `log`. Upon successful deletion, a confirmation message will be returned.

## Request Parameters

| Parameter | Required  | Description                        |
|-----------|-----------|------------------------------------|
| clean     | Yes       | Specifies the list type to be cleaned (e.g., `log`). |

## Response Format

- **Success**: If the list is successfully cleared, the server will return `Clean OK`.
- **Failure**: If the list clearing fails, the server will return `Clean Fail`.

## Syntax

```bash
http://<serverIP:8592>/face_list?clean=log
```

```bash
http://<serverIP:8592>/face_list?clean=denial
```

# Clean All Lists
## Description

This API is used to clear all list data without specifying a particular type. Upon successful deletion, a confirmation message will be returned.

## Response Format

- **Success**: If all lists are successfully cleared, the server will return `OK`.

## Syntax
```bash
http://<serverIP>/clean_face_list
```

# Upload Face Recognition License File
## Description
This API is used to upload a face recognition license file to the device.

## Request Parameters

| Parameter  | Required | Description                                |
|------------|----------|--------------------------------------------|
| file       | Yes      | The license file in `.lic` format, must be uploaded via a form. |

## Response Format

Upon successful upload of the license, the API does not return any information, but the server will restart.

## Syntax

```bash
curl -X POST http://<serverIP:8592>/upload_face_licensekey \
    -u "<username>:<password>" \
    -H "If-Modified-Since: 0" \
    -H "Cache-Control: no-cache" \
    -F "file=@iengine.lic"
```

### Sample iengine.lic File

```json=
{
    "version": "<version>",
    "contract": {
        "customer": "MERITLILIN_REST integration",
        "expiration": {
            "day": "<expiration_day>",
            "month": "<expiration_month>",
            "year": "<expiration_year>"
        },
        "hwids": [
            "<hwid>"
        ],
        "products": [
            "iface"
        ],
        "idkit": {
            "database_size": 0,
            "max_client_connections": 0
        },
        "smartface_embedded": {
            "enable": true,
            "face_template_count": 10000
        }
    },
    "contract_signature": "<contract_signature>"
}
```

# Upload CSV to Batch Add Personnel
## Description

This API is used to upload a CSV file, which is converted into JSON format to batch add personnel data. The CSV file contains information such as names, schedule times, images, and list categories. Upon successful upload, a success message will be returned.

## File Format Description

**CSV Columns Description**

| Column  | Description                                      |
|---------|--------------------------------------------------|
| A       | First Name                                       |
| B       | Last Name                                        |
| C       | Schedule Start Time                              |
| D       | Schedule End Time                                |
| E       | Other Information                                |
| F       | List Category                                    |
| G       | Image File Name (for the facial recognition data)|

## Request Parameters

| Parameter | Required | Description                                 |
|-----------|----------|---------------------------------------------|
| file      | Yes      | The CSV file in `.csv` format, must be uploaded via form. |

## Response Format

If the data is successfully added, the server will return `Success`.

## Syntax

```bash
curl -X POST http://<serverIP:8592>/import_face_list \
-u "<username>:<password>" \
-H "Content-Type: application/json" \
-H "If-Modified-Since: 0" \
-H "Cache-Control: no-cache" \
-d '[{
    "firstname": "容添",
    "lastName": "黃",
    "scheduleStart": "00:00",
    "scheduleEnd": "23:59",
    "other": "臺南市歸仁區中山路7號10樓",
    "list_type": "vip"
}, {
    "firstname": "千娜",
    "lastName": "馮",
    "scheduleStart": "00:00",
    "scheduleEnd": "23:59",
    "other": "新北市汐止區康寧街70號",
    "list_type": "watch"
}, {
    "firstname": "理福",
    "lastName": "蕭",
    "scheduleStart": "00:00",
    "scheduleEnd": "23:59",
    "other": "桃園市桃園區德壽六街49號6樓之6",
    "list_type": "denial"
}]'
```

# Download Specific List CSV File
## Description
This API allows users to download data from a specified list and export it in CSV format. The data from the list will be displayed in a comma-separated format.

## File Format Description
The API will download the corresponding CSV file based on the specified list type. The response CSV file uses **UTF-8 with BOM** encoding to ensure proper display of multi-byte characters (e.g., Chinese).

**CSV Columns Description**

| Column | Description                               |
|--------|-------------------------------------------|
| A      | First Name                                |
| B      | Last Name                                 |
| C      | Schedule Start Time                       |
| D      | Schedule End Time                         |
| E      | Other Information                         |
| F      | List Category                             |
| G      | Image File Name                           |

## Request Parameters

| Parameter | Required | Description                                 |
|-----------|----------|---------------------------------------------|
| download  | Yes      | The type of list to download (e.g., `vip`, `watch`, `log`, `denial`, or `ALL`) |

## Syntax
### Download Watch and VIP List
```bash
http://<serverIP:8592>/face_list?download=ALL
```

### Download Log List
```bash
http://<serverIP:8592>/face_list?download=log
```

### Download Watch List
```bash
http://<serverIP:8592>/face_list?download=watch
```

### Download VIP List
```bash
http://<serverIP:8592>/face_list?download=vip
```

### Download Denial List
```bash
http://<serverIP:8592>/face_list?download=denial
```

Here’s the SDK documentation in English:

# Get Server Information

## Description
This API retrieves system and license information from the server, such as the device name, version, system ID, and license status.

## Request Syntax
```bash
http://<serverIP:8592>/server
```

## Response Parameters
| Parameter         | Type   | Description                                                      |
|-------------------|--------|------------------------------------------------------------------|
| `DeviceName`      | string | Name of the device (e.g., GYNet)                                 |
| `Version`         | string | Software version (e.g., 2.0.6.5-24)                              |
| `SystemID`        | string | System ID                                                        |
| `LicenseType`     | string | Type of license (e.g., Face Recognition)                         |
| `LicenseStatus`   | string | License status and expiration date (e.g., expiration: 2024-12-9) |
| `UnlockingKey`    | string | Unlocking key for the system                                     |
| `ModeName`        | string | Mode name                                                        |

## Response Example
```json=
{
    "DeviceName": "GYNet",
    "Version": "2.0.6.5-24",
    "SystemID": "00-0F-FC-53-5F-C6",
    "LicenseType": "EDGEFACE (Face Recognition)",
    "LicenseStatus": "expiration:2024-12-9, hwids:IM0000ffc535fc60, customer:MERITLILIN_REST integration",
    "UnlockingKey": "faceDcAoGTXf0jra1yapYLsssF7Hg70sPU5N9KfH341dDIchJlK+79Z81woUcFM2DoUVoldILzE+1vdPmRXW2PPGDetNJqrbLa8fRW5FbjZ5gG5iik6sBu+IMqVFijpBd/f8tXofBeQtM7lG78guYOAVGDUVebQNZNmlo3RRxF0Nqig=",
    "ModeName": "mod001"
}
``` 
