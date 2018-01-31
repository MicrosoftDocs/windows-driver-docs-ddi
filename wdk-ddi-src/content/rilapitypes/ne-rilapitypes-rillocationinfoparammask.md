---
UID: NE:rilapitypes.RILLOCATIONINFOPARAMMASK
title: RILLOCATIONINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rillocationinfoparammask_2.htm
old-project: netvista
ms.assetid: a7ce7aaf-fd98-4ba6-8c9e-d15419c658f1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_PARAM_LU_HUICCAPP, RIL_PARAM_LU_TAC, RIL_PARAM_LU_HUICCAPP, RILLOCATIONINFOPARAMMASK, RIL_PARAM_LU_ALL, RIL_PARAM_LU_CELLID, rilapitypes/RIL_PARAM_LU_CELLID, RIL_PARAM_LU_LAC, RILLOCATIONINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILLOCATIONINFOPARAMMASK, rilapitypes/RIL_PARAM_LU_ALL, rilapitypes/RIL_PARAM_LU_TAC, rilapitypes/RIL_PARAM_LU_LAC, netvista.rillocationinfoparammask_2
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
-	RILLOCATIONINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILLOCATIONINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILLOCATIONINFOPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILLOCATIONINFOPARAMMASK { 
  RIL_PARAM_LU_HUICCAPP,
  RIL_PARAM_LU_LAC,
  RIL_PARAM_LU_TAC,
  RIL_PARAM_LU_CELLID,
  RIL_PARAM_LU_ALL
} RILLOCATIONINFOPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_LU_EXECUTOR



#### - RIL_PARAM_LU_HUICCAPP



#### - RIL_PARAM_LU_LAC



#### - RIL_PARAM_LU_TAC



#### - RIL_PARAM_LU_CELLID



#### - RIL_PARAM_LU_ALL


