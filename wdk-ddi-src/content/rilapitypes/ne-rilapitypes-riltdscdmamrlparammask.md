---
UID: NE:rilapitypes.RILTDSCDMAMRLPARAMMASK
title: RILTDSCDMAMRLPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltdscdmamrlparammask_2.htm
old-project: netvista
ms.assetid: 7e23aa74-e811-4621-bdf7-a2d8b7715f9d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILTDSCDMAMRLPARAMMASK, RILTDSCDMAMRLPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_TDSCDMAMRL_ALL, RIL_PARAM_TDSCDMAMRL_CELLID, RIL_PARAM_TDSCDMAMRL_CELLPARAM, RIL_PARAM_TDSCDMAMRL_LAC, RIL_PARAM_TDSCDMAMRL_MNC, RIL_PARAM_TDSCDMAMRL_PATHLOSS, RIL_PARAM_TDSCDMAMRL_RSCP, RIL_PARAM_TDSCDMAMRL_UARFCN, netvista.riltdscdmamrlparammask_2, rilapitypes/RILTDSCDMAMRLPARAMMASK, rilapitypes/RIL_PARAM_TDSCDMAMRL_ALL, rilapitypes/RIL_PARAM_TDSCDMAMRL_CELLID, rilapitypes/RIL_PARAM_TDSCDMAMRL_CELLPARAM, rilapitypes/RIL_PARAM_TDSCDMAMRL_LAC, rilapitypes/RIL_PARAM_TDSCDMAMRL_MNC, rilapitypes/RIL_PARAM_TDSCDMAMRL_PATHLOSS, rilapitypes/RIL_PARAM_TDSCDMAMRL_RSCP, rilapitypes/RIL_PARAM_TDSCDMAMRL_UARFCN
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
-	RILTDSCDMAMRLPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILTDSCDMAMRLPARAMMASK
req.product: Windows 10 or later.
---

# RILTDSCDMAMRLPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILTDSCDMAMRLPARAMMASK { 
  RIL_PARAM_TDSCDMAMRL_MNC,
  RIL_PARAM_TDSCDMAMRL_LAC,
  RIL_PARAM_TDSCDMAMRL_CELLID,
  RIL_PARAM_TDSCDMAMRL_UARFCN,
  RIL_PARAM_TDSCDMAMRL_CELLPARAM,
  RIL_PARAM_TDSCDMAMRL_RSCP,
  RIL_PARAM_TDSCDMAMRL_PATHLOSS,
  RIL_PARAM_TDSCDMAMRL_ALL
} RILTDSCDMAMRLPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_TDSCDMAMRL_MCC


### -field RIL_PARAM_TDSCDMAMRL_MNC


### -field RIL_PARAM_TDSCDMAMRL_LAC


### -field RIL_PARAM_TDSCDMAMRL_CELLID


### -field RIL_PARAM_TDSCDMAMRL_UARFCN


### -field RIL_PARAM_TDSCDMAMRL_CELLPARAM


### -field RIL_PARAM_TDSCDMAMRL_RSCP


### -field RIL_PARAM_TDSCDMAMRL_PATHLOSS


### -field RIL_PARAM_TDSCDMAMRL_ALL

