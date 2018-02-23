---
UID: NE:ntddrilapitypes.RILCALLMEDIATYPE
title: RILCALLMEDIATYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediatype.htm
old-project: netvista
ms.assetid: 993013f1-5026-4c30-b4df-958606adc8fa
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RIL_CALLMEDIATYPE_AUDIO, RIL_CALLMEDIATYPE_AUDIO, RIL_CALLMEDIATYPE_VIDEO, RIL_CALLMEDIATYPE_MAX, RILCALLMEDIATYPE, RILCALLMEDIATYPE enumeration [Network Drivers Starting with Windows Vista], netvista.rilcallmediatype, ntddrilapitypes/RILCALLMEDIATYPE, ntddrilapitypes/RIL_CALLMEDIATYPE_CUSTOM, ntddrilapitypes/RIL_CALLMEDIATYPE_VIDEO, ntddrilapitypes/RIL_CALLMEDIATYPE_MAX, RIL_CALLMEDIATYPE_CUSTOM
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
-	RILCALLMEDIATYPE
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIATYPE
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

