---
UID: NE:rilapitypes.RILRADIOPRESENCE
title: RILRADIOPRESENCE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiopresence.htm
old-project: netvista
ms.assetid: de67cf2e-1dd8-4b01-9a60-b8a2a01d326b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILRADIOPRESENCE, RILRADIOPRESENCE enumeration [Network Drivers Starting with Windows Vista], RIL_RADIOPRESENCE_MAX, RIL_RADIOPRESENCE_PRESENT, netvista.rilradiopresence, ntddrilapitypes/RILRADIOPRESENCE, ntddrilapitypes/RIL_RADIOPRESENCE_MAX, ntddrilapitypes/RIL_RADIOPRESENCE_PRESENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILRADIOPRESENCE
product: Windows
targetos: Windows
req.typenames: RILRADIOPRESENCE
req.product: Windows 10 or later.
---

# RILRADIOPRESENCE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILRADIOPRESENCE { 
  RIL_RADIOPRESENCE_PRESENT,
  RIL_RADIOPRESENCE_MAX
} RILRADIOPRESENCE;
````


## -enum-fields




### -field RIL_RADIOPRESENCE_NOTPRESENT


### -field RIL_RADIOPRESENCE_PRESENT


### -field RIL_RADIOPRESENCE_MAX

