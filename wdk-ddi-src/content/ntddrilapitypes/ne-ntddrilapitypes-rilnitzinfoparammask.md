---
UID: NE:ntddrilapitypes.RILNITZINFOPARAMMASK
title: RILNITZINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnitzinfoparammask.htm
old-project: netvista
ms.assetid: bdf1505f-2a84-48a3-9534-df83237ab7bb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.rilnitzinfoparammask, RIL_PARAM_NITZ_ALL, ntddrilapitypes/RILNITZINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_NITZ_ALL, ntddrilapitypes/RIL_PARAM_NITZ_SYSTEMTYPE, ntddrilapitypes/RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET, RILNITZINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILNITZINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_NITZ_TIMEZONEOFFSET, RIL_PARAM_NITZ_TIMEZONEOFFSET, RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET, RIL_PARAM_NITZ_SYSTEMTYPE, RIL_PARAM_NITZ_SYSTEMTIME, ntddrilapitypes/RIL_PARAM_NITZ_SYSTEMTIME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILNITZINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILNITZINFOPARAMMASK
---

# RILNITZINFOPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILNITZINFOPARAMMASK { 
  RIL_PARAM_NITZ_TIMEZONEOFFSET,
  RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET,
  RIL_PARAM_NITZ_SYSTEMTIME,
  RIL_PARAM_NITZ_SYSTEMTYPE,
  RIL_PARAM_NITZ_ALL
} RILNITZINFOPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_NITZ_EXECUTOR


### -field RIL_PARAM_NITZ_TIMEZONEOFFSET


### -field RIL_PARAM_NITZ_DAYLIGHTSAVINGOFFSET


### -field RIL_PARAM_NITZ_SYSTEMTIME


### -field RIL_PARAM_NITZ_SYSTEMTYPE


### -field RIL_PARAM_NITZ_ALL

