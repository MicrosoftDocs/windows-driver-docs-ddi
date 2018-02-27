---
UID: NS:ntddrilapitypes.RILNITZINFO_V1
title: RILNITZINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnitzinfo_v1.htm
old-project: netvista
ms.assetid: 88664809-b5ce-466a-894b-529443cb1b0e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILNITZINFO_V1, RILNITZINFO_V1, RILNITZINFO_V1 structure [Network Drivers Starting with Windows Vista], netvista.rilnitzinfo_v1, ntddrilapitypes/RILNITZINFO_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILNITZINFO_V1
product: Windows
targetos: Windows
req.typenames: RILNITZINFO_V1, *LPRILNITZINFO_V1
---

# RILNITZINFO_V1 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILNITZINFO_V1 {
  DWORD          cbSize;
  DWORD          dwParams;
  DWORD          dwExecutor;
  int            TimeZoneOffsetMinutes;
  int            DaylightSavingOffsetMinutes;
  RILSYSTEMTIME  SysTime;
} RILNITZINFO_V1, RILNITZINFO_V1;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field TimeZoneOffsetMinutes


### -field DaylightSavingOffsetMinutes


### -field SysTime

