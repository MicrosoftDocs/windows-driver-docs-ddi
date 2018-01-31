---
UID: NE:rilapitypes.RILREGSTATUSINFOPARAMMASK
title: RILREGSTATUSINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilregstatusinfoparammask_2.htm
old-project: netvista
ms.assetid: 22751b8b-f19c-4480-b8f4-6ee2322419ca
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_REGSI_SYSTEMCAPS, rilapitypes/RIL_PARAM_REGSI_ALL, RIL_PARAM_REGSI_NETWORKCODE, rilapitypes/RIL_PARAM_REGSI_ACCESSTECHNOLOGY, RILREGSTATUSINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_REGSI_VOICEDOMAIN, netvista.rilregstatusinfoparammask_2, rilapitypes/RIL_PARAM_REGSI_REGSTATUS, RIL_PARAM_REGSI_REGSTATUS, rilapitypes/RILREGSTATUSINFOPARAMMASK, RIL_PARAM_REGSI_HUICCAPP, RIL_PARAM_REGSI_ALL, rilapitypes/RIL_PARAM_REGSI_SYSTEMCAPS, RIL_PARAM_REGSI_VOICEDOMAIN, RIL_PARAM_REGSI_CURRENTOPERATOR, RILREGSTATUSINFOPARAMMASK, RIL_PARAM_REGSI_REGREJECTREASON, rilapitypes/RIL_PARAM_REGSI_HUICCAPP, RIL_PARAM_REGSI_ACCESSTECHNOLOGY, rilapitypes/RIL_PARAM_REGSI_REGREJECTREASON, rilapitypes/RIL_PARAM_REGSI_NETWORKCODE, rilapitypes/RIL_PARAM_REGSI_CURRENTOPERATOR
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
-	RILREGSTATUSINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILREGSTATUSINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILREGSTATUSINFOPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILREGSTATUSINFOPARAMMASK { 
  RIL_PARAM_REGSI_HUICCAPP,
  RIL_PARAM_REGSI_REGSTATUS,
  RIL_PARAM_REGSI_ACCESSTECHNOLOGY,
  RIL_PARAM_REGSI_SYSTEMCAPS,
  RIL_PARAM_REGSI_REGREJECTREASON,
  RIL_PARAM_REGSI_CURRENTOPERATOR,
  RIL_PARAM_REGSI_VOICEDOMAIN,
  RIL_PARAM_REGSI_NETWORKCODE,
  RIL_PARAM_REGSI_ALL
} RILREGSTATUSINFOPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_REGSI_EXECUTOR



#### - RIL_PARAM_REGSI_HUICCAPP



#### - RIL_PARAM_REGSI_REGSTATUS



#### - RIL_PARAM_REGSI_ACCESSTECHNOLOGY



#### - RIL_PARAM_REGSI_SYSTEMCAPS



#### - RIL_PARAM_REGSI_REGREJECTREASON



#### - RIL_PARAM_REGSI_CURRENTOPERATOR



#### - RIL_PARAM_REGSI_VOICEDOMAIN



#### - RIL_PARAM_REGSI_NETWORKCODE



#### - RIL_PARAM_REGSI_ALL


