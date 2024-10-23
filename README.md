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
### Get Someone in the List
```
Syntax:
http://<serverIP>/face_list?select=watch&face_name=00001
```

Return:
{"FACE_COUNT":1,"INFORMATION":[{"INDEX":1,"TS":"","MOD_TS":"","RTIME":"","ACTION":"","sec_color_id":"","ACT_PARAM":"watch","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","FR_X":"","FR_Y":"","FR_W":"","FR_H":"","FR_BMP":"2024_4_23_14_7_46_378_00001","ROI_BMP":"","COUNTRY":"","FR_USER":"","FR_PHONE":"","FR_ADDRESS":"","FR_PAYSTATUS":"","FR_EXIST":"","FR_SCHEDULE_S":"00:00","FR_SCHEDULE_E":"23:59","FR_OTHER":"","FR_DETECT_ENDTIME":"2200-12-30_23:59","face_name":"00001","user_name":"Visitorf00001","last_name":"","face_uuid":"a626a066-978a-49be","identification_score":"0.00","face_trackingID":"a626a066-978a-49be"}],"LIST_TYPE":"watch"}

### Get Face Engine Detail
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

## Delete Face event lists
### Delete all Face lists
```
Syntax:
http://<serverIP>/clean_face_list
```

Return:
Clean OK
### Delete the Face Log list
```
Syntax:
http://<serverIP>/set_search_info?clean=log
```

Return:
Clean OK
### Delete the Face Watch list

```
Syntax:
http://<serverIP>/set_search_info?clean=watch
```

Return:
Clean OK

### Delete the Face VIP list
```
Syntax:
http://<serverIP>/set_search_info?clean=vip
```

Return:
Clean OK

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

### Add VIP name and image
```
Syntax:
http://<serverIP>/upload_face_img
```

NOTE: This command must be used via POST, appending the image file and first and last name
. Note: The image file must be in base64 format. Note: The Additional format is Json


### Added face recognition iengine.lic
```
Syntax:
http://<serverIP>/upload_face_licensekey
```

NOTE: This command must be used via POST with the iengine.lic file attached. Note: The file name needs to be iengine.lic


## Import & export lists
### Import a CSV file into wach list and vip list.
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

### Export a CSV file from Face log list
```
Syntax:
http://<serverIP>/face_list?download=log
```
