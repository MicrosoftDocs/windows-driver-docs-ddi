---
UID: NE:rilapitypes.RILDIALPARAMSOPTIONS
title: RILDIALPARAMSOPTIONS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildialparamsoptions_2.htm
old-project: netvista
ms.assetid: c2635f91-005f-45e7-9d6c-92caca7f4452
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, D, I, L, M, N, O, P, R, RILDIALPARAMSOPTIONS, RILDIALPARAMSOPTIONS enumeration [Network Drivers Starting with Windows Vista], RIL_DIALOPT_ALL, RIL_DIALOPT_ANYEXECUTORFOREMERGENCY, RIL_DIALOPT_PRESENTID, RIL_DIALOPT_RESTRICTID, RIL_DIALOPT_RTTFULL, S, T, netvista.rildialparamsoptions_2, rilapitypes/RILDIALPARAMSOPTIONS, rilapitypes/RIL_DIALOPT_ALL, rilapitypes/RIL_DIALOPT_ANYEXECUTORFOREMERGENCY, rilapitypes/RIL_DIALOPT_PRESENTID, rilapitypes/RIL_DIALOPT_RESTRICTID, rilapitypes/RIL_DIALOPT_RTTFULL"
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
-	RILDIALPARAMSOPTIONS
product: Windows
targetos: Windows
req.typenames: RILDIALPARAMSOPTIONS
req.product: Windows 10 or later.
---

# RILDIALPARAMSOPTIONS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILDIALPARAMSOPTIONS { 
  RIL_DIALOPT_RESTRICTID,
  RIL_DIALOPT_PRESENTID,
  RIL_DIALOPT_ANYEXECUTORFOREMERGENCY,
  RIL_DIALOPT_RTTFULL,
  RIL_DIALOPT_ALL
} RILDIALPARAMSOPTIONS;
````


## -enum-fields




### -field RIL_DIALOPT_NONE


### -field RIL_DIALOPT_RESTRICTID


### -field RIL_DIALOPT_PRESENTID


### -field RIL_DIALOPT_ANYEXECUTORFOREMERGENCY


### -field RIL_DIALOPT_RTTFULL


### -field RIL_DIALOPT_ALL

