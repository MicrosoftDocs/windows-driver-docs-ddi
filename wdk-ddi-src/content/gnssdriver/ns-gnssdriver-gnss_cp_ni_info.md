---
UID: NS:gnssdriver.__unnamed_struct_30
title: GNSS_CP_NI_INFO (gnssdriver.h)
description: This structure contains CP NI information.
old-location: gnss\gnss_cp_ni_info.htm
tech.root: gnss
ms.assetid: FC05C59C-F8B5-4573-A1F0-722A25BDA151
ms.date: 02/15/2018
ms.keywords: "*PGNSS_CP_NI_INFO, GNSS_CP_NI_INFO, GNSS_CP_NI_INFO structure [Sensor Devices], PGNSS_CP_NI_INFO, PGNSS_CP_NI_INFO structure pointer [Sensor Devices], gnss.gnss_cp_ni_info, gnssdriver/GNSS_CP_NI_INFO, gnssdriver/PGNSS_CP_NI_INFO"
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- gnssdriver.h
api_name:
- GNSS_CP_NI_INFO
product:
- Windows
targetos: Windows
req.typenames: GNSS_CP_NI_INFO, *PGNSS_CP_NI_INFO
---

# GNSS_CP_NI_INFO structure


## -description


This structure contains CP NI information.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field RequestorId

 


### -field NotificationText

 




#### - NotificationText[MAX_PATH]

Name of the client that requests the location of the device.

This will be displayed on the notification dialog to the user. The GNSS Driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.


#### - RequestorId[MAX_PATH]

Requestor ID.

This will be displayed on the notification dialog to the user. The GNSS driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.

