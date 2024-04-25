# LILIN-Edge-AI-Facial-Recognition-Camera
LILIN Edge AI Facial Recognition Camera

## Get Face event list

### Get Face log list

```
Syntax:
http://<serverIP>/face_list?flist=log
```

Return:
{"FACE_COUNT":2,"INFORMATION":[{"INDEX":1,"TS":"","MOD_TS":"2024-04-23 14:07:48:388","RTIME":"","ACTION":"","sec_color_id":"","ACT_PARAM":"watch","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","FR_X":"","FR_Y":"","FR_W":"","FR_H":"","FR_BMP":"2024_4_23_14_7_47_890_00001","ROI_BMP":"","COUNTRY":"","FR_USER":"","FR_PHONE":"","FR_ADDRESS":"","FR_PAYSTATUS":"","FR_EXIST":"","FR_SCHEDULE_S":"","FR_SCHEDULE_E":"","FR_OTHER":"","FR_DETECT_ENDTIME":"","IN_USER":"","face_name":"00001","user_name":"Visitorf00001","last_name":"","face_uuid":"","identification_score":"98","face_trackingID":"0"},{"INDEX":2,"TS":"","MOD_TS":"2024-04-23 14:07:47:834","RTIME":"","ACTION":"","sec_color_id":"","ACT_PARAM":"watch","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","FR_X":"","FR_Y":"","FR_W":"","FR_H":"","FR_BMP":"2024_4_23_14_7_47_283_00001","ROI_BMP":"","COUNTRY":"","FR_USER":"","FR_PHONE":"","FR_ADDRESS":"","FR_PAYSTATUS":"","FR_EXIST":"","FR_SCHEDULE_S":"","FR_SCHEDULE_E":"","FR_OTHER":"","FR_DETECT_ENDTIME":"","IN_USER":"","face_name":"00001","user_name":"Visitorf00001","last_name":"","face_uuid":"","identification_score":"98","face_trackingID":"0"}],"LIST_TYPE":"log"}

### Get Face Watch list
```
Syntax:
http://<serverIP>/face_list?flist=watch
```

Return:
{"FACE_COUNT":2,"INFORMATION":[{"INDEX":1,"TS":"","MOD_TS":"","RTIME":"","ACTION":"","sec_color_id":"","ACT_PARAM":"watch","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","FR_X":"","FR_Y":"","FR_W":"","FR_H":"","FR_BMP":"2024_4_23_14_7_46_378_00001","ROI_BMP":"","COUNTRY":"","FR_USER":"","FR_PHONE":"","FR_ADDRESS":"","FR_PAYSTATUS":"","FR_EXIST":"","FR_SCHEDULE_S":"00:00","FR_SCHEDULE_E":"23:59","FR_OTHER":"","FR_DETECT_ENDTIME":"2200-12-30_23:59","IN_USER":"","face_name":"00001","user_name":"Visitorf00001","last_name":"","face_uuid":"","identification_score":"0.00","face_trackingID":"a626a066-978a-49be"},{"INDEX":2,"TS":"","MOD_TS":"","RTIME":"","ACTION":"","sec_color_id":"","ACT_PARAM":"watch","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","FR_X":"","FR_Y":"","FR_W":"","FR_H":"","FR_BMP":"2024_4_23_14_7_47_103_00002","ROI_BMP":"","COUNTRY":"","FR_USER":"","FR_PHONE":"","FR_ADDRESS":"","FR_PAYSTATUS":"","FR_EXIST":"","FR_SCHEDULE_S":"00:00","FR_SCHEDULE_E":"23:59","FR_OTHER":"","FR_DETECT_ENDTIME":"2200-12-30_23:59","IN_USER":"","face_name":"00002","user_name":"Visitorf00002","last_name":"","face_uuid":"","identification_score":"0.00","face_trackingID":"c0c0ab4f-4f69-478d"}],"LIST_TYPE":"watch"}

### Get Face VIP list
```
Syntax:
http://<serverIP>/face_list?flist=vip
```

Return:
{"FACE_COUNT":1,"INFORMATION":[{"INDEX":1,"TS":"","MOD_TS":"","RTIME":"","ACTION":"","sec_color_id":"","ACT_PARAM":"vip","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","FR_X":"","FR_Y":"","FR_W":"","FR_H":"","FR_BMP":"2024_4_23_14_10_54_375_00003","ROI_BMP":"","COUNTRY":"","FR_USER":"林","FR_PHONE":"","FR_ADDRESS":"","FR_PAYSTATUS":"","FR_EXIST":"","FR_SCHEDULE_S":"00:00","FR_SCHEDULE_E":"23:59","FR_OTHER":"","FR_DETECT_ENDTIME":"2200-12-30_23:59","IN_USER":"林","face_name":"00003","user_name":"志玲","last_name":"林","face_uuid":"","identification_score":"100.0","face_trackingID":"9964094f-df62-41a0"}],"LIST_TYPE":"vip"}

### Get someone in the list
```
Syntax:
http://<serverIP>/face_list?select=watch&face_name=00001
```

Return:
{"FACE_COUNT":1,"INFORMATION":[{"INDEX":1,"TS":"","MOD_TS":"","RTIME":"","ACTION":"","sec_color_id":"","ACT_PARAM":"watch","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","FR_X":"","FR_Y":"","FR_W":"","FR_H":"","FR_BMP":"2024_4_23_14_7_46_378_00001","ROI_BMP":"","COUNTRY":"","FR_USER":"","FR_PHONE":"","FR_ADDRESS":"","FR_PAYSTATUS":"","FR_EXIST":"","FR_SCHEDULE_S":"00:00","FR_SCHEDULE_E":"23:59","FR_OTHER":"","FR_DETECT_ENDTIME":"2200-12-30_23:59","face_name":"00001","user_name":"Visitorf00001","last_name":"","face_uuid":"a626a066-978a-49be","identification_score":"0.00","face_trackingID":"a626a066-978a-49be"}],"LIST_TYPE":"watch"}

### Get Face engine detail
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
