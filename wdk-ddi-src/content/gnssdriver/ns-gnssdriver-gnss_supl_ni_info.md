---
UID: NS:gnssdriver.GNSS_SUPL_NI_INFO
title: GNSS_SUPL_NI_INFO
author: windows-driver-content
description: This structure contains the requested SUPL NI information.
old-location: gnss\gnss_supl_ni_info.htm
tech.root: gnss
ms.assetid: 78D19A0C-E247-4DDA-A689-494B5A61A673
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGNSS_SUPL_NI_INFO, GNSS_SUPL_NI_INFO, GNSS_SUPL_NI_INFO structure [Sensor Devices], PGNSS_SUPL_NI_INFO, PGNSS_SUPL_NI_INFO structure pointer [Sensor Devices], gnss.gnss_supl_ni_info, gnssdriver/GNSS_SUPL_NI_INFO, gnssdriver/PGNSS_SUPL_NI_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_SUPL_NI_INFO
product:
- Windows
targetos: Windows
req.typenames: GNSS_SUPL_NI_INFO, *PGNSS_SUPL_NI_INFO
---

# GNSS_SUPL_NI_INFO structure


## -description


This structure contains the requested SUPL NI information.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field RequestorId

 


### -field ClientName

 


### -field SuplNiUrl

 




#### - ClientName[MAX_PATH]

Name of the client that requests the location of the device.

This will be displayed on the notification dialog to the user. The GNSS driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.


#### - RequestorId[MAX_PATH]

Requestor ID.

This will be displayed on the notification dialog to the user. The GNSS driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.


#### - SuplNiUrl[MAX_SERVER_URL_NAME]

NI URL information.

