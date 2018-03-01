---
UID: NE:rilapitypes.RILCALLINFODISCONNECTINITIATOR
title: RILCALLINFODISCONNECTINITIATOR
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfodisconnectinitiator_2.htm
old-project: netvista
ms.assetid: 4ea730ab-0ba0-46cd-b156-0b2f32b2eafe
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILCALLINFODISCONNECTINITIATOR, RILCALLINFODISCONNECTINITIATOR enumeration [Network Drivers Starting with Windows Vista], RIL_DISCINIT_LOCAL, RIL_DISCINIT_MAX, RIL_DISCINIT_REMOTE, netvista.rilcallinfodisconnectinitiator_2, rilapitypes/RILCALLINFODISCONNECTINITIATOR, rilapitypes/RIL_DISCINIT_LOCAL, rilapitypes/RIL_DISCINIT_MAX, rilapitypes/RIL_DISCINIT_REMOTE
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
-	RILCALLINFODISCONNECTINITIATOR
product: Windows
targetos: Windows
req.typenames: RILCALLINFODISCONNECTINITIATOR
req.product: Windows 10 or later.
---

# RILCALLINFODISCONNECTINITIATOR enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLINFODISCONNECTINITIATOR { 
  RIL_DISCINIT_LOCAL,
  RIL_DISCINIT_REMOTE,
  RIL_DISCINIT_MAX
} RILCALLINFODISCONNECTINITIATOR;
````


## -enum-fields




### -field RIL_DISCINIT_UNKNOWN


### -field RIL_DISCINIT_LOCAL


### -field RIL_DISCINIT_REMOTE


### -field RIL_DISCINIT_MAX

