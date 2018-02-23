---
UID: NS:gnssdriver.GNSS_SINGLESHOT_PARAM
title: GNSS_SINGLESHOT_PARAM
author: windows-driver-content
description: This structure defines the parameters for a single-shot fix session.
old-location: sensors\gnss_singleshot_param.htm
old-project: sensors
ms.assetid: BD1CB6CE-4196-4B85-AED0-A7B8ED957ADF
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: GNSS_SINGLESHOT_PARAM, gnssdriver/PGNSS_SINGLESHOT_PARAM, sensors.gnss_singleshot_param, gnssdriver/GNSS_SINGLESHOT_PARAM, PGNSS_SINGLESHOT_PARAM structure pointer [Sensor Devices], GNSS_SINGLESHOT_PARAM structure [Sensor Devices], PGNSS_SINGLESHOT_PARAM, *PGNSS_SINGLESHOT_PARAM
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
-	GNSS_SINGLESHOT_PARAM
product: Windows
targetos: Windows
req.typenames: GNSS_SINGLESHOT_PARAM, *PGNSS_SINGLESHOT_PARAM
---

# GNSS_SINGLESHOT_PARAM structure


## -description


This structure defines the parameters for a single-shot fix session.


## -syntax


````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG ResponseTime;
} GNSS_SINGLESHOT_PARAM, *PGNSS_SINGLESHOT_PARAM;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field ResponseTime

Response time is maximum remaining time that an application can wait for a fix or an error. 

Since the driver is expected to return intermediate fixes the ResponseTime is only an advisory information for the driver that can be used in an implementation-specific manner for making appropriate tradeoffs internally to satisfy the request. A value of 0 indicate that no specific response time is mandated by the GNSS adapter for the fix session.

