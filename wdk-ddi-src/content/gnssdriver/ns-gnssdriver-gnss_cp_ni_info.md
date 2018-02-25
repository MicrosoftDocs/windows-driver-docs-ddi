---
UID: NS:gnssdriver.GNSS_CP_NI_INFO
title: GNSS_CP_NI_INFO
author: windows-driver-content
description: This structure contains CP NI information.
old-location: sensors\gnss_cp_ni_info.htm
old-project: sensors
ms.assetid: FC05C59C-F8B5-4573-A1F0-722A25BDA151
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PGNSS_CP_NI_INFO, ,, C, F, G, GNSS_CP_NI_INFO, GNSS_CP_NI_INFO structure [Sensor Devices], I, N, O, P, PGNSS_CP_NI_INFO, PGNSS_CP_NI_INFO structure pointer [Sensor Devices], S, _, gnssdriver/GNSS_CP_NI_INFO, gnssdriver/PGNSS_CP_NI_INFO, sensors.gnss_cp_ni_info"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	GNSS_CP_NI_INFO
product: Windows
targetos: Windows
req.typenames: GNSS_CP_NI_INFO, *PGNSS_CP_NI_INFO
---

# GNSS_CP_NI_INFO structure


## -description


This structure contains CP NI information.


## -syntax


````
typedef struct {
  ULONG Size;
  ULONG Version;
  WCHAR RequestorId[MAX_PATH];
  WCHAR NotificationText[MAX_PATH];
} GNSS_CP_NI_INFO, *PGNSS_CP_NI_INFO;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field RequestorId

 


### -field NotificationText

 




#### - RequestorId[MAX_PATH]

Requestor ID.

This will be displayed on the notification dialog to the user. The GNSS driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.


#### - NotificationText[MAX_PATH]

Name of the client that requests the location of the device.

This will be displayed on the notification dialog to the user. The GNSS Driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.

