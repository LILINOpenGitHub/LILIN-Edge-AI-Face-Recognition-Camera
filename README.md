# LILIN-Edge-AI-Facial-Recognition-Camera
LILIN Edge AI Facial Recognition Camera

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


### Get Face Info from Log List

```
http://<serverIP:8592>/face_list?flist=log
```

Return:
```json=
{
    "FACE_COUNT": 3,
    "INFORMATION": [
        {
            "INDEX": 1,
            "FR_UPDATE_DATE": "2024-10-22 16:04:09",
            "FR_LIST_TYPE": "watch",
            "FR_BMP": "2024_10_22_16_4_9_497_00001",
            "FR_SCHEDULE_S": "",
            "FR_SCHEDULE_E": "",
            "FR_OTHER": "",
            "FR_DETECT_ENDTIME": "",
            "FR_FACE_NAME": "00001",
            "FR_LAST_NAME": "",
            "FR_FIRST_NAME": "Visitorf00001",
            "FR_SCORE": "99.6"
        },
        {
            "INDEX": 2,
            "FR_UPDATE_DATE": "2024-10-22 16:04:09",
            "FR_LIST_TYPE": "watch",
            "FR_BMP": "2024_10_22_11_16_9_497_00003",
            "FR_SCHEDULE_S": "",
            "FR_SCHEDULE_E": "",
            "FR_OTHER": "",
            "FR_DETECT_ENDTIME": "",
            "FR_FACE_NAME": "00003",
            "FR_LAST_NAME": "",
            "FR_FIRST_NAME": "Visitorf00003",
            "FR_SCORE": "99.7"
        },
        {
            "INDEX": 3,
            "FR_UPDATE_DATE": "2024-10-22 11:04:09",
            "FR_LIST_TYPE": "watch",
            "FR_BMP": "2024_10_22_11_4_9_497_00002",
            "FR_SCHEDULE_S": "",
            "FR_SCHEDULE_E": "",
            "FR_OTHER": "",
            "FR_DETECT_ENDTIME": "",
            "FR_FACE_NAME": "00002",
            "FR_LAST_NAME": "",
            "FR_FIRST_NAME": "Visitorf00002",
            "FR_SCORE": "99.7"
        }
    ],
    "LIST_TYPE": "log"
}
```

### Get Face List from Watch List
```
Syntax:
http://<serverIP:8592>/face_list?flist=watch
```

Return:
{"FACE_COUNT":2,"INFORMATION":[{"INDEX":1,"TS":"","MOD_TS":"","RTIME":"","ACTION":"","sec_color_id":"","ACT_PARAM":"watch","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","FR_X":"","FR_Y":"","FR_W":"","FR_H":"","FR_BMP":"2024_4_23_14_7_46_378_00001","ROI_BMP":"","COUNTRY":"","FR_USER":"","FR_PHONE":"","FR_ADDRESS":"","FR_PAYSTATUS":"","FR_EXIST":"","FR_SCHEDULE_S":"00:00","FR_SCHEDULE_E":"23:59","FR_OTHER":"","FR_DETECT_ENDTIME":"2200-12-30_23:59","IN_USER":"","face_name":"00001","user_name":"Visitorf00001","last_name":"","face_uuid":"","identification_score":"0.00","face_trackingID":"a626a066-978a-49be"},{"INDEX":2,"TS":"","MOD_TS":"","RTIME":"","ACTION":"","sec_color_id":"","ACT_PARAM":"watch","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","FR_X":"","FR_Y":"","FR_W":"","FR_H":"","FR_BMP":"2024_4_23_14_7_47_103_00002","ROI_BMP":"","COUNTRY":"","FR_USER":"","FR_PHONE":"","FR_ADDRESS":"","FR_PAYSTATUS":"","FR_EXIST":"","FR_SCHEDULE_S":"00:00","FR_SCHEDULE_E":"23:59","FR_OTHER":"","FR_DETECT_ENDTIME":"2200-12-30_23:59","IN_USER":"","face_name":"00002","user_name":"Visitorf00002","last_name":"","face_uuid":"","identification_score":"0.00","face_trackingID":"c0c0ab4f-4f69-478d"}],"LIST_TYPE":"watch"}

### Get Face VIP list
```
Syntax:
[http://<serverIP>/face_list?flist=vip](http://<serverIP:8592>/face_list?flist=vip)
```

Return:
```json=
{
    "FACE_COUNT": 2,
    "INFORMATION": [
        {
            "INDEX": 1,
            "FR_UPDATE_DATE": "2024-10-22 15:25:40",
            "FR_LIST_TYPE": "vip",
            "FR_BMP": "2024_10_22_11_2_59_443_00003",
            "FR_SCHEDULE_S": "00:00",
            "FR_SCHEDULE_E": "23:59",
            "FR_OTHER": "台北市松山區民生東路五段27巷10號",
            "FR_DETECT_ENDTIME": "2044-12-01_23:59",
            "FR_FACE_NAME": "00003",
            "FR_LAST_NAME": "Chao",
            "FR_FIRST_NAME": "Alan",
            "FR_SCORE": "0.00"
        },
        {
            "INDEX": 2,
            "FR_UPDATE_DATE": "2024-10-22 15:30:59",
            "FR_LIST_TYPE": "vip",
            "FR_BMP": "2024_10_22_15_30_59_661_00005",
            "FR_SCHEDULE_S": "00:00",
            "FR_SCHEDULE_E": "23:59",
            "FR_OTHER": "金門縣金湖鎮市港路32號",
            "FR_DETECT_ENDTIME": "2044-12-01_23:59",
            "FR_FACE_NAME": "00005",
            "FR_LAST_NAME": "Cheng",
            "FR_FIRST_NAME": "Frank",
            "FR_SCORE": "100.0"
        }
    ],
    "LIST_TYPE": "vip"
}
```
### Get Face Info from Denial List
```
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

```
http://<serverIP:8592>/face_list?select=vip&face_name=00005
```

## Response Example

```json=
{
    "FACE_COUNT": 1,
    "INFORMATION": [
        {
            "INDEX": 1,
            "FR_UPDATE_DATE": "2024-10-22 15:30:59",
            "FR_LIST_TYPE": "vip",
            "FR_BMP": "2024_10_22_15_30_59_661_00005",
            "FR_SCHEDULE_S": "00:00",
            "FR_SCHEDULE_E": "23:59",
            "FR_OTHER": "32 Port Street, Jinhu Township, Kinmen County",
            "FR_DETECT_ENDTIME": "2044-12-01_23:59",
            "FR_FACE_NAME": "00005",
            "FR_LAST_NAME": "Cheng",
            "FR_FIRST_NAME": "Frank",
            "FR_SCORE": "100.0"
        }
    ],
    "LIST_TYPE": "vip"
}
```

### Get Face Recognition Engine Detail
```
Syntax:
http://<serverIP>/server
```

Return:
DeviceName=GYNet
Version=2.0.6.5-8 Language=en_gb
SystemID=00-0F-FC-53-5F-C6
LicenseType= EDGEFACE (Face Recognition),
LicenseStatus=expiration:2024-6-14, hwids:IM0000ffc535fc60, customer:MERITLILIN_REST integration
UnlockingKey=faceXeXbUncgyd9cJKHn+paOOUKlTEXP/4Q2+udnEBAX7RsSXf6uMV3QNLvYngJ4Pm4nI/1rTjwzpdT5B8LZxyTJJZPhdadEsDuCXnAA4AUBU7hEii6ZBv/P4nKw0XtAyaEylPBHFAg8xj18bpMIxmrsAYRbi9v2wapkicFMUNXmODk=
ModeName=mod001

# Delete Specific Person

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

```
http://<serverIP:8592>/face_list?clean=log
```

```
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

```bash
http://<serverIP:8592>/face_list?flist=log&namelist
```

```bash
http://<serverIP:8592>/face_list?flist=watch&namelist
```

## Response Example

```json=
{
    "NAME_COUNT": 3,
    "INFORMATION": [
        {
            "FR_LAST_NAME": "Chao",
            "FR_FIRST_NAME": "Alan"
        },
        {
            "FR_LAST_NAME": "Kao",
            "FR_FIRST_NAME": "Dora"
        },
        {
            "FR_LAST_NAME": "Tsui",
            "FR_FIRST_NAME": "Judy"
        }
    ],
    "LIST_TYPE": "log"
}
```
### Delete items of an Face list
```
Syntax:
http://<serverIP>/face_list?delete=vip&count=1&face_name=00051
```

Return:
OK

## Set Face list

```
Syntax:
http://<serverIP>/face_list?update=watch&count=1&lpr_plate=Eric&lpr_user=Chen&lpr_paystatus=&lpr_schedule_s=01:01&lpr_schedule_e=05:40&lpr_other=No.50,%20Sec.%203,%20Renai%20Rd.,%20D&face_name=00002&user_name=Chen&face_first_name=Eric&face_last_name=Chen&face_address=No.50,%20Sec.%203,%20Renai%20Rd.,%20D&lpr_detect_endtime=2030-12-30_04:53
```

Return:
OK

### Confirm the number of records with the same name in the vip list
```
Syntax:
http://<serverIP>/check_vip
```

NOTE: This command must be used via POST with first and last name appended. Note: Additional format is Json
Return:
0

### Move watch list data to vip list
```
Syntax:
http://<serverIP>/move_watch_or_log_to_vip
```

NOTE: This command must be used via POST with first and last name appended. Note: Additional format is Json

Return:
OK

### Add VIP Name and Image
```
Syntax:
http://<serverIP>/upload_face_img
```

NOTE: This command must be used via POST, appending the image file and first and last name
. Note: The image file must be in base64 format. Note: The Additional format is Json


### Added Face Recognition iengine.lic
```
Syntax:
http://<serverIP>/upload_face_licensekey
```

NOTE: This command must be used via POST with the iengine.lic file attached. Note: The file name needs to be iengine.lic


## Import & Export Lists
### Import a CSV File into Watch List and VIP List.
```
Syntax:
http://<serverIP>/import_face_list
```

Note: This command has to be used by POST, and attach the csv file. Note: The file should be utf8 with Bom format.

### Export a CSV file from Face watch list and vip list.
```
Syntax:
http://<serverIP>/face_list?download=ALL
```

### Export a CSV File from the List of Face Log
```
Syntax:
http://<serverIP>/face_list?download=log
```
