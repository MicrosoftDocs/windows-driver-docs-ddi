---
UID: NS:gnssdriver.GNSS_SUPL_VERSION
title: GNSS_SUPL_VERSION
author: windows-driver-content
description: This structure contains SUPL version information.
old-location: sensors\gnss_supl_version.htm
old-project: sensors
ms.assetid: D004DAEF-F25F-442D-9A6D-91FB8A18E0DB
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PGNSS_SUPL_VERSION, GNSS_SUPL_VERSION, gnssdriver/GNSS_SUPL_VERSION, PGNSS_SUPL_VERSION structure pointer [Sensor Devices], sensors.gnss_supl_version, *PGNSS_SUPL_VERSION, gnssdriver/PGNSS_SUPL_VERSION, GNSS_SUPL_VERSION structure [Sensor Devices]
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
-	GNSS_SUPL_VERSION
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_VERSION, *PGNSS_SUPL_VERSION
---

# GNSS_SUPL_VERSION structure


## -description


This structure contains SUPL version information.




## -syntax


````
typedef struct {
  ULONG MajorVersion;
  ULONG MinorVersion;
} GNSS_SUPL_VERSION, *PGNSS_SUPL_VERSION;
````


## -struct-fields




### -field MajorVersion

Major version number.


### -field MinorVersion

Minor version number.

