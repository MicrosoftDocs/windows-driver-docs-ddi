---
UID: NE:rilapitypes.RILSYSTEMCAPS
title: RILSYSTEMCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemcaps_2.htm
old-project: netvista
ms.assetid: d8148f94-d3f0-4578-83a3-024e64c9258b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILSYSTEMCAPS, RILSYSTEMCAPS enumeration [Network Drivers Starting with Windows Vista], RIL_SYSTEMCAPS_ALL, RIL_SYSTEMCAPS_VOICEDATA, netvista.rilsystemcaps_2, rilapitypes/RILSYSTEMCAPS, rilapitypes/RIL_SYSTEMCAPS_ALL, rilapitypes/RIL_SYSTEMCAPS_VOICEDATA
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILSYSTEMCAPS
product: Windows
targetos: Windows
req.typenames: RILSYSTEMCAPS
req.product: Windows 10 or later.
---

# RILSYSTEMCAPS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILSYSTEMCAPS { 
  RIL_SYSTEMCAPS_VOICEDATA,
  RIL_SYSTEMCAPS_ALL
} RILSYSTEMCAPS;
````


## -enum-fields




### -field RIL_SYSTEMCAPS_NONE


### -field RIL_SYSTEMCAPS_VOICEDATA


### -field RIL_SYSTEMCAPS_ALL

