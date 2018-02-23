---
UID: NS:rilapitypes.RILUICCSLOTINFO
title: RILUICCSLOTINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccslotinfo_2.htm
old-project: netvista
ms.assetid: 5fd25815-40b1-4fba-a7e8-fed24d731ab0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILUICCSLOTINFO, rilapitypes/RILUICCSLOTINFO, RILUICCSLOTINFO structure [Network Drivers Starting with Windows Vista], netvista.riluiccslotinfo_2, RILUICCSLOTINFO"
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
-	RILUICCSLOTINFO
product: Windows
targetos: Windows
req.typenames: RILUICCSLOTINFO, *LPRILUICCSLOTINFO
req.product: Windows 10 or later.
---

# RILUICCSLOTINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILUICCSLOTINFO {
  DWORD                cbSize;
  DWORD                dwParams;
  DWORD                dwNumOfUiccSlots;
  RILUICCSLOTSTATE [1] dwSlotState;
} RILUICCSLOTINFO, RILUICCSLOTINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwNumOfUiccSlots


### -field dwSlotState

