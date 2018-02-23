---
UID: NS:rilapitypes.RILNITZINFO_V2
title: RILNITZINFO_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnitzinfo_v2_2.htm
old-project: netvista
ms.assetid: 508d89d5-1f79-4346-81f5-fabfeb405bd4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILNITZINFO_V2 structure [Network Drivers Starting with Windows Vista], RILNITZINFO_V2, *LPRILNITZINFO_V2, rilapitypes/RILNITZINFO_V2, netvista.rilnitzinfo_v2_2, RILNITZINFO, *LPRILNITZINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
-	rilapitypes.h
apiname:
-	RILNITZINFO_V2
product: Windows
targetos: Windows
req.typenames: RILNITZINFO_V2, RILNITZINFO, *LPRILNITZINFO, *LPRILNITZINFO_V2
req.product: Windows 10 or later.
---

# RILNITZINFO_V2 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILNITZINFO_V2 {
  DWORD          cbSize;
  DWORD          dwParams;
  DWORD          dwExecutor;
  int            TimeZoneOffsetMinutes;
  int            DaylightSavingOffsetMinutes;
  RILSYSTEMTIME  SysTime;
  DWORD          dwSystemTypes;
} RILNITZINFO_V2, RILNITZINFO_V2;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field TimeZoneOffsetMinutes


### -field DaylightSavingOffsetMinutes


### -field SysTime


### -field dwSystemTypes

