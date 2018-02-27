---
UID: NE:rilapitypes.RILCALLMEDIAOFFERACTION
title: RILCALLMEDIAOFFERACTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferaction_2.htm
old-project: netvista
ms.assetid: 2acfaeab-c196-46a9-87a4-c44306b46ad1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLMEDIAOFFERACTION, RILCALLMEDIAOFFERACTION enumeration [Network Drivers Starting with Windows Vista], RIL_CALLMEDIAOFFERACTION_ACCEPT, RIL_CALLMEDIAOFFERACTION_ASK, RIL_CALLMEDIAOFFERACTION_CANCEL, RIL_CALLMEDIAOFFERACTION_ERROR, RIL_CALLMEDIAOFFERACTION_MAX, RIL_CALLMEDIAOFFERACTION_REJECT, netvista.rilcallmediaofferaction_2, rilapitypes/RILCALLMEDIAOFFERACTION, rilapitypes/RIL_CALLMEDIAOFFERACTION_ACCEPT, rilapitypes/RIL_CALLMEDIAOFFERACTION_ASK, rilapitypes/RIL_CALLMEDIAOFFERACTION_CANCEL, rilapitypes/RIL_CALLMEDIAOFFERACTION_ERROR, rilapitypes/RIL_CALLMEDIAOFFERACTION_MAX, rilapitypes/RIL_CALLMEDIAOFFERACTION_REJECT
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
-	RILCALLMEDIAOFFERACTION
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAOFFERACTION
req.product: Windows 10 or later.
---

# RILCALLMEDIAOFFERACTION enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLMEDIAOFFERACTION { 
  RIL_CALLMEDIAOFFERACTION_ERROR,
  RIL_CALLMEDIAOFFERACTION_REJECT,
  RIL_CALLMEDIAOFFERACTION_ASK,
  RIL_CALLMEDIAOFFERACTION_ACCEPT,
  RIL_CALLMEDIAOFFERACTION_CANCEL,
  RIL_CALLMEDIAOFFERACTION_MAX
} RILCALLMEDIAOFFERACTION;
````


## -enum-fields




### -field RIL_CALLMEDIAOFFERACTION_NONE


### -field RIL_CALLMEDIAOFFERACTION_ERROR


### -field RIL_CALLMEDIAOFFERACTION_REJECT


### -field RIL_CALLMEDIAOFFERACTION_ASK


### -field RIL_CALLMEDIAOFFERACTION_ACCEPT


### -field RIL_CALLMEDIAOFFERACTION_CANCEL


### -field RIL_CALLMEDIAOFFERACTION_MAX

