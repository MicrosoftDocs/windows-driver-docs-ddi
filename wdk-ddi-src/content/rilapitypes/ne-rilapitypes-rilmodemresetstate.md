---
UID: NE:rilapitypes.RILMODEMRESETSTATE
title: RILMODEMRESETSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmodemresetstate_2.htm
old-project: netvista
ms.assetid: 9cdc6548-393f-4af6-a8ee-bb96deb0f228
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMODEMRESETSTATE, RILMODEMRESETSTATE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_MODEMRESETSTATE_MAX, rilapitypes/RIL_MODEMRESETSTATE_FAILED, RIL_MODEMRESETSTATE_MAX, RIL_MODEMRESETSTATE_FAILED, netvista.rilmodemresetstate_2, rilapitypes/RILMODEMRESETSTATE, RIL_MODEMRESETSTATE_RECOVERED, rilapitypes/RIL_MODEMRESETSTATE_RECOVERED
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
-	RILMODEMRESETSTATE
product: Windows
targetos: Windows
req.typenames: RILMODEMRESETSTATE
req.product: Windows 10 or later.
---

# RILMODEMRESETSTATE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILMODEMRESETSTATE { 
  RIL_MODEMRESETSTATE_RECOVERED,
  RIL_MODEMRESETSTATE_FAILED,
  RIL_MODEMRESETSTATE_MAX
} RILMODEMRESETSTATE;
````


## -enum-fields




### -field RIL_MODEMRESETSTATE_STARTED


### -field RIL_MODEMRESETSTATE_RECOVERED


### -field RIL_MODEMRESETSTATE_FAILED


### -field RIL_MODEMRESETSTATE_MAX

