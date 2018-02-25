---
UID: NS:gnssdriver.GNSS_BREADCRUMBING_ALERT_DATA
title: GNSS_BREADCRUMBING_ALERT_DATA
author: windows-driver-content
description: This structure contains alert information for when the breadcrumb buffer has reached a level where OS read operations should be performed.
old-location: sensors\gnss_breadcrumbing_alert_data.htm
old-project: sensors
ms.assetid: 5B8C1264-336C-438F-89AC-82B6FCBAE931
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PGNSS_BREADCRUMBING_ALERT_DATA, ,, A, B, C, D, E, G, GNSS_BREADCRUMBING_ALERT_DATA, GNSS_BREADCRUMBING_ALERT_DATA structure [Sensor Devices], I, L, M, N, P, PGNSS_BREADCRUMBING_ALERT_DATA, PGNSS_BREADCRUMBING_ALERT_DATA structure pointer [Sensor Devices], R, S, T, U, _, gnssdriver/GNSS_BREADCRUMBING_ALERT_DATA, gnssdriver/PGNSS_BREADCRUMBING_ALERT_DATA, sensors.gnss_breadcrumbing_alert_data"
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
-	GNSS_BREADCRUMBING_ALERT_DATA
product: Windows
targetos: Windows
req.typenames: GNSS_BREADCRUMBING_ALERT_DATA, *PGNSS_BREADCRUMBING_ALERT_DATA
---

# GNSS_BREADCRUMBING_ALERT_DATA structure


## -description


This structure contains alert information for when the breadcrumb buffer has reached a level where OS read operations should be performed.


## -syntax


````
typedef struct {
  ULONG Size;
  ULONG Version;
  BYTE  Unused[512];
} GNSS_BREADCRUMBING_ALERT_DATA, *PGNSS_BREADCRUMBING_ALERT_DATA;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field Unused

 




#### - Unused[512]

Padding buffer.

