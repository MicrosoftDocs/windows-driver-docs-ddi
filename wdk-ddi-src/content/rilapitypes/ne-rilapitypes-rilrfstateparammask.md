---
UID: NE:rilapitypes.RILRFSTATEPARAMMASK
title: RILRFSTATEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrfstateparammask_2.htm
old-project: netvista
ms.assetid: 075c61aa-b091-4616-810b-f39ad40d2777
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_RFSTATE_ALL, RIL_PARAM_RFSTATE_RFDATA, rilapitypes/RILRFSTATEPARAMMASK, RIL_PARAM_RFSTATE_RFSTATE, RIL_PARAM_RFSTATE_RFDATASIZE, rilapitypes/RIL_PARAM_RFSTATE_RFDATASIZE, RILRFSTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILRFSTATEPARAMMASK, rilapitypes/RIL_PARAM_RFSTATE_ALL, rilapitypes/RIL_PARAM_RFSTATE_RFSTATE, rilapitypes/RIL_PARAM_RFSTATE_RFDATA, netvista.rilrfstateparammask_2
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
-	RILRFSTATEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILRFSTATEPARAMMASK
req.product: Windows 10 or later.
---

# RILRFSTATEPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILRFSTATEPARAMMASK { 
  RIL_PARAM_RFSTATE_RFSTATE,
  RIL_PARAM_RFSTATE_RFDATASIZE,
  RIL_PARAM_RFSTATE_RFDATA,
  RIL_PARAM_RFSTATE_ALL
} RILRFSTATEPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_RFSTATE_NONE



### -field RIL_PARAM_RFSTATE_RFSTATE



### -field RIL_PARAM_RFSTATE_RFDATASIZE



### -field RIL_PARAM_RFSTATE_RFDATA



### -field RIL_PARAM_RFSTATE_ALL


