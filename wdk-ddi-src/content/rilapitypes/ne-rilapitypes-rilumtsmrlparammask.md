---
UID: NE:rilapitypes.RILUMTSMRLPARAMMASK
title: RILUMTSMRLPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilumtsmrlparammask_2.htm
old-project: netvista
ms.assetid: d0450aeb-8b6e-4ab2-94b7-563503a83e76
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILUMTSMRLPARAMMASK, RILUMTSMRLPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_UMTSMRL_ALL, RIL_PARAM_UMTSMRL_CELLID, RIL_PARAM_UMTSMRL_ECNO, RIL_PARAM_UMTSMRL_LAC, RIL_PARAM_UMTSMRL_MNC, RIL_PARAM_UMTSMRL_PATHLOSS, RIL_PARAM_UMTSMRL_PRIMARY_SC, RIL_PARAM_UMTSMRL_RSCP, RIL_PARAM_UMTSMRL_UARFCN, netvista.rilumtsmrlparammask_2, rilapitypes/RILUMTSMRLPARAMMASK, rilapitypes/RIL_PARAM_UMTSMRL_ALL, rilapitypes/RIL_PARAM_UMTSMRL_CELLID, rilapitypes/RIL_PARAM_UMTSMRL_ECNO, rilapitypes/RIL_PARAM_UMTSMRL_LAC, rilapitypes/RIL_PARAM_UMTSMRL_MNC, rilapitypes/RIL_PARAM_UMTSMRL_PATHLOSS, rilapitypes/RIL_PARAM_UMTSMRL_PRIMARY_SC, rilapitypes/RIL_PARAM_UMTSMRL_RSCP, rilapitypes/RIL_PARAM_UMTSMRL_UARFCN
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
-	RILUMTSMRLPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILUMTSMRLPARAMMASK
req.product: Windows 10 or later.
---

# RILUMTSMRLPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILUMTSMRLPARAMMASK { 
  RIL_PARAM_UMTSMRL_MNC,
  RIL_PARAM_UMTSMRL_LAC,
  RIL_PARAM_UMTSMRL_CELLID,
  RIL_PARAM_UMTSMRL_UARFCN,
  RIL_PARAM_UMTSMRL_PRIMARY_SC,
  RIL_PARAM_UMTSMRL_RSCP,
  RIL_PARAM_UMTSMRL_ECNO,
  RIL_PARAM_UMTSMRL_PATHLOSS,
  RIL_PARAM_UMTSMRL_ALL
} RILUMTSMRLPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_UMTSMRL_MCC


### -field RIL_PARAM_UMTSMRL_MNC


### -field RIL_PARAM_UMTSMRL_LAC


### -field RIL_PARAM_UMTSMRL_CELLID


### -field RIL_PARAM_UMTSMRL_UARFCN


### -field RIL_PARAM_UMTSMRL_PRIMARY_SC


### -field RIL_PARAM_UMTSMRL_RSCP


### -field RIL_PARAM_UMTSMRL_ECNO


### -field RIL_PARAM_UMTSMRL_PATHLOSS


### -field RIL_PARAM_UMTSMRL_ALL

