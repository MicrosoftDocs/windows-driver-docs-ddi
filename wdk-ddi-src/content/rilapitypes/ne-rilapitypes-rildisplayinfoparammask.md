---
UID: NE:rilapitypes.RILDISPLAYINFOPARAMMASK
title: RILDISPLAYINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildisplayinfoparammask_2.htm
old-project: netvista
ms.assetid: d8bd093d-ad95-488e-a057-b96fecf58bbb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_PARAM_DISPLAY_MESSAGE, rilapitypes/RIL_PARAM_DISPLAY_TYPE, rilapitypes/RILDISPLAYINFOPARAMMASK, netvista.rildisplayinfoparammask_2, RILDISPLAYINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_DISPLAY_MESSAGESIZE, RIL_PARAM_DISPLAY_ALL, rilapitypes/RIL_PARAM_DISPLAY_MESSAGE, RIL_PARAM_DISPLAY_TAG, rilapitypes/RIL_PARAM_DISPLAY_TAG, rilapitypes/RIL_PARAM_DISPLAY_ALL, rilapitypes/RIL_PARAM_DISPLAY_MESSAGESIZE, RIL_PARAM_DISPLAY_TYPE, RILDISPLAYINFOPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
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
-	RILDISPLAYINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILDISPLAYINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILDISPLAYINFOPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILDISPLAYINFOPARAMMASK { 
  RIL_PARAM_DISPLAY_TYPE,
  RIL_PARAM_DISPLAY_TAG,
  RIL_PARAM_DISPLAY_MESSAGESIZE,
  RIL_PARAM_DISPLAY_MESSAGE,
  RIL_PARAM_DISPLAY_ALL
} RILDISPLAYINFOPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_DISPLAY_EXECUTOR


### -field RIL_PARAM_DISPLAY_TYPE


### -field RIL_PARAM_DISPLAY_TAG


### -field RIL_PARAM_DISPLAY_MESSAGESIZE


### -field RIL_PARAM_DISPLAY_MESSAGE


### -field RIL_PARAM_DISPLAY_ALL

