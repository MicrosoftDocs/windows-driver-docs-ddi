---
UID: NE:rilapitypes.RILCALLMEDIATYPE
title: RILCALLMEDIATYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediatype_2.htm
old-project: netvista
ms.assetid: f4ecaf9a-1d8d-4a56-afa0-b893eb0c4c62
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_CALLMEDIATYPE_CUSTOM, RIL_CALLMEDIATYPE_CUSTOM, RIL_CALLMEDIATYPE_MAX, netvista.rilcallmediatype_2, RIL_CALLMEDIATYPE_VIDEO, rilapitypes/RIL_CALLMEDIATYPE_AUDIO, rilapitypes/RIL_CALLMEDIATYPE_VIDEO, RILCALLMEDIATYPE enumeration [Network Drivers Starting with Windows Vista], RILCALLMEDIATYPE, RIL_CALLMEDIATYPE_AUDIO, rilapitypes/RILCALLMEDIATYPE, rilapitypes/RIL_CALLMEDIATYPE_MAX
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
-	RILCALLMEDIATYPE
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIATYPE
req.product: Windows 10 or later.
---

# RILCALLMEDIATYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLMEDIATYPE { 
  RIL_CALLMEDIATYPE_AUDIO,
  RIL_CALLMEDIATYPE_VIDEO,
  RIL_CALLMEDIATYPE_CUSTOM,
  RIL_CALLMEDIATYPE_MAX
} RILCALLMEDIATYPE;
````


## -enum-fields




### -field RIL_CALLMEDIATYPE_UNKNOWN


### -field RIL_CALLMEDIATYPE_AUDIO


### -field RIL_CALLMEDIATYPE_VIDEO


### -field RIL_CALLMEDIATYPE_CUSTOM


### -field RIL_CALLMEDIATYPE_MAX

