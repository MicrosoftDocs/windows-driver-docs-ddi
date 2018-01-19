---
UID: NS:gnssdriver.GNSS_DISTANCETRACKING_PARAM
title: GNSS_DISTANCETRACKING_PARAM
author: windows-driver-content
description: This structure defines the parameters for a distance-based tracking fix session.
old-location: sensors\gnss_distancetracking_param.htm
old-project: sensors
ms.assetid: B37B3C59-225C-40BC-BCA4-9ABF2500AFC0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_DISTANCETRACKING_PARAM, GNSS_DISTANCETRACKING_PARAM, *PGNSS_DISTANCETRACKING_PARAM
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
req.alt-api: GNSS_DISTANCETRACKING_PARAM
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
req.typenames: GNSS_DISTANCETRACKING_PARAM, *PGNSS_DISTANCETRACKING_PARAM
---

# GNSS_DISTANCETRACKING_PARAM structure



## -description
This structure defines the parameters for a distance-based tracking fix session.



## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG MovementThreshold;
} GNSS_DISTANCETRACKING_PARAM, *PGNSS_DISTANCETRACKING_PARAM;
````


## -struct-fields

### -field Size

Structure size.


### -field Version

Version number.


### -field MovementThreshold

If the device moves beyond this threshold, a fix will be generated/recorded. A value of zero indicates that a fix should be reported whenever the device moves. This value is specified in meters.


## -remarks
