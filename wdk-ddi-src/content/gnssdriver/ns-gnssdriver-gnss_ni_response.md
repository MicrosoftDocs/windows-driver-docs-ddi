---
UID: NS:gnssdriver.GNSS_NI_RESPONSE
title: GNSS_NI_RESPONSE
author: windows-driver-content
description: This structure contains NI request response information.
old-location: sensors\gnss_ni_response.htm
old-project: sensors
ms.assetid: D2F7C90E-BAF4-419D-94CF-5FC39E7B6A58
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: gnssdriver/PGNSS_NI_RESPONSE, PGNSS_NI_RESPONSE, sensors.gnss_ni_response, gnssdriver/GNSS_NI_RESPONSE, GNSS_NI_RESPONSE, GNSS_NI_RESPONSE structure [Sensor Devices], *PGNSS_NI_RESPONSE, PGNSS_NI_RESPONSE structure pointer [Sensor Devices]
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
-	GNSS_NI_RESPONSE
product: Windows
targetos: Windows
req.typenames: GNSS_NI_RESPONSE, *PGNSS_NI_RESPONSE
---

# GNSS_NI_RESPONSE structure


## -description


This structure contains NI request response information.


## -syntax


````
typedef struct {
  ULONG                 Size;
  ULONG                 Version;
  ULONG                 RequestId;
  GNSS_NI_USER_RESPONSE UserResponse;
} GNSS_NI_RESPONSE, *PGNSS_NI_RESPONSE;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field RequestId

The ID to uniquely identify the NI request.


### -field UserResponse

The user response to the NI request.

