---
UID: NE:ntddrilapitypes.RILCALLINFODIRECTION
title: RILCALLINFODIRECTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfodirection.htm
old-project: netvista
ms.assetid: 2243fb04-81a9-49d6-9ce2-d06d4a590fb1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILCALLINFODIRECTION, RILCALLINFODIRECTION enumeration [Network Drivers Starting with Windows Vista], RIL_CALLDIR_MAX, RIL_CALLDIR_OUTGOING, netvista.rilcallinfodirection, ntddrilapitypes/RILCALLINFODIRECTION, ntddrilapitypes/RIL_CALLDIR_MAX, ntddrilapitypes/RIL_CALLDIR_OUTGOING
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILCALLINFODIRECTION
product: Windows
targetos: Windows
req.typenames: RILCALLINFODIRECTION
---

# RILCALLINFODIRECTION enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILCALLINFODIRECTION { 
  RIL_CALLDIR_OUTGOING,
  RIL_CALLDIR_MAX
} RILCALLINFODIRECTION;
````


## -enum-fields




### -field RIL_CALLDIR_INCOMING


### -field RIL_CALLDIR_OUTGOING


### -field RIL_CALLDIR_MAX

