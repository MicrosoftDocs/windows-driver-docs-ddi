---
UID: NE:ntddrilapitypes.RILDIALPARAMSOPTIONS
title: RILDIALPARAMSOPTIONS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildialparamsoptions.htm
old-project: netvista
ms.assetid: 78fef8f7-e6cd-4da6-9c2a-2eaf1da6339b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILDIALPARAMSOPTIONS, ntddrilapitypes/RIL_DIALOPT_PRESENTID, RILDIALPARAMSOPTIONS, ntddrilapitypes/RIL_DIALOPT_RESTRICTID, RIL_DIALOPT_ANYEXECUTORFOREMERGENCY, RIL_DIALOPT_RTTFULL, ntddrilapitypes/RIL_DIALOPT_RTTFULL, RIL_DIALOPT_PRESENTID, RILDIALPARAMSOPTIONS enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_DIALOPT_ALL, ntddrilapitypes/RIL_DIALOPT_ANYEXECUTORFOREMERGENCY, RIL_DIALOPT_ALL, netvista.rildialparamsoptions, RIL_DIALOPT_RESTRICTID
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
-	RILDIALPARAMSOPTIONS
product: Windows
targetos: Windows
req.typenames: RILDIALPARAMSOPTIONS
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

