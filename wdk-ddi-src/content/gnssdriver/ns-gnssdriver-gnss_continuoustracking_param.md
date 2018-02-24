---
UID: NS:gnssdriver.GNSS_CONTINUOUSTRACKING_PARAM
title: GNSS_CONTINUOUSTRACKING_PARAM
author: windows-driver-content
description: This structure defines the parameters for a continuous tracking fix session.
old-location: sensors\gnss_continuoustracking_param.htm
old-project: sensors
ms.assetid: D69D317C-5B42-4709-87AF-4323DF2EBE2D
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PGNSS_CONTINUOUSTRACKING_PARAM structure pointer [Sensor Devices], gnssdriver/GNSS_CONTINUOUSTRACKING_PARAM, GNSS_CONTINUOUSTRACKING_PARAM, *PGNSS_CONTINUOUSTRACKING_PARAM, GNSS_CONTINUOUSTRACKING_PARAM structure [Sensor Devices], PGNSS_CONTINUOUSTRACKING_PARAM, sensors.gnss_continuoustracking_param, gnssdriver/PGNSS_CONTINUOUSTRACKING_PARAM
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
-	GNSS_CONTINUOUSTRACKING_PARAM
product: Windows
targetos: Windows
req.typenames: "*PGNSS_CONTINUOUSTRACKING_PARAM, GNSS_CONTINUOUSTRACKING_PARAM"
---

# GNSS_CONTINUOUSTRACKING_PARAM structure


## -description


This structure defines the parameters for a continuous tracking fix session.


## -syntax


````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG PreferredInterval;
} GNSS_CONTINUOUSTRACKING_PARAM, *PGNSS_CONTINUOUSTRACKING_PARAM;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field PreferredInterval

Specifies the preferred interval of receiving fixes for a continuous tracking session. The units for this value is seconds.

