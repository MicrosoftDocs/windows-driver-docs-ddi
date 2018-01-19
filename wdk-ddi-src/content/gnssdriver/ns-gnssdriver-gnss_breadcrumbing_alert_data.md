---
UID: NS:gnssdriver.GNSS_BREADCRUMBING_ALERT_DATA
title: GNSS_BREADCRUMBING_ALERT_DATA
author: windows-driver-content
description: This structure contains alert information for when the breadcrumb buffer has reached a level where OS read operations should be performed.
old-location: sensors\gnss_breadcrumbing_alert_data.htm
old-project: sensors
ms.assetid: 5B8C1264-336C-438F-89AC-82B6FCBAE931
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_BREADCRUMBING_ALERT_DATA, GNSS_BREADCRUMBING_ALERT_DATA, *PGNSS_BREADCRUMBING_ALERT_DATA
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
req.alt-api: GNSS_BREADCRUMBING_ALERT_DATA
req.alt-loc: gnssdriver.h
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


### -field Unused[512]

Padding buffer.


## -remarks
