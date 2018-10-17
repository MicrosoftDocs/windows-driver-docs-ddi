---
UID: NE:rilapitypes.RILPOSITIONINFOUMTSPARAMMASK
title: RILPOSITIONINFOUMTSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfoumtsparammask_2.htm
tech.root: netvista
ms.assetid: c2e1bf17-130a-4e09-81e3-30100217e1b9
ms.date: 2/26/2018
ms.keywords: RILPOSITIONINFOUMTSPARAMMASK, RILPOSITIONINFOUMTSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_POSITION_UMTS_ALL, RIL_PARAM_POSITION_UMTS_CELLID, RIL_PARAM_POSITION_UMTS_ECNO, RIL_PARAM_POSITION_UMTS_FREQINFO_DL, RIL_PARAM_POSITION_UMTS_FREQINFO_NT, RIL_PARAM_POSITION_UMTS_FREQINFO_UL, RIL_PARAM_POSITION_UMTS_LAC, RIL_PARAM_POSITION_UMTS_MNC, RIL_PARAM_POSITION_UMTS_PATHLOSS, RIL_PARAM_POSITION_UMTS_PRIMARY_SC, RIL_PARAM_POSITION_UMTS_RSCP, RIL_PARAM_POSITION_UMTS_UARFCN, netvista.rilpositioninfoumtsparammask_2, rilapitypes/RILPOSITIONINFOUMTSPARAMMASK, rilapitypes/RIL_PARAM_POSITION_UMTS_ALL, rilapitypes/RIL_PARAM_POSITION_UMTS_CELLID, rilapitypes/RIL_PARAM_POSITION_UMTS_ECNO, rilapitypes/RIL_PARAM_POSITION_UMTS_FREQINFO_DL, rilapitypes/RIL_PARAM_POSITION_UMTS_FREQINFO_NT, rilapitypes/RIL_PARAM_POSITION_UMTS_FREQINFO_UL, rilapitypes/RIL_PARAM_POSITION_UMTS_LAC, rilapitypes/RIL_PARAM_POSITION_UMTS_MNC, rilapitypes/RIL_PARAM_POSITION_UMTS_PATHLOSS, rilapitypes/RIL_PARAM_POSITION_UMTS_PRIMARY_SC, rilapitypes/RIL_PARAM_POSITION_UMTS_RSCP, rilapitypes/RIL_PARAM_POSITION_UMTS_UARFCN
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
-	RILPOSITIONINFOUMTSPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILPOSITIONINFOUMTSPARAMMASK
req.product: Windows 10 or later.
---

# RILPOSITIONINFOUMTSPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```
typedef enum _RILPOSITIONINFOUMTSPARAMMASK {
  RIL_PARAM_POSITION_UMTS_MNC,
  RIL_PARAM_POSITION_UMTS_LAC,
  RIL_PARAM_POSITION_UMTS_CELLID,
  RIL_PARAM_POSITION_UMTS_FREQINFO_UL,
  RIL_PARAM_POSITION_UMTS_FREQINFO_DL,
  RIL_PARAM_POSITION_UMTS_FREQINFO_NT,
  RIL_PARAM_POSITION_UMTS_UARFCN,
  RIL_PARAM_POSITION_UMTS_PRIMARY_SC,
  RIL_PARAM_POSITION_UMTS_RSCP,
  RIL_PARAM_POSITION_UMTS_ECNO,
  RIL_PARAM_POSITION_UMTS_PATHLOSS,
  RIL_PARAM_POSITION_UMTS_ALL
} RILPOSITIONINFOUMTSPARAMMASK;
```


## -enum-fields




### -field RIL_PARAM_POSITION_UMTS_MCC


### -field RIL_PARAM_POSITION_UMTS_MNC


### -field RIL_PARAM_POSITION_UMTS_LAC


### -field RIL_PARAM_POSITION_UMTS_CELLID


### -field RIL_PARAM_POSITION_UMTS_FREQINFO_UL


### -field RIL_PARAM_POSITION_UMTS_FREQINFO_DL


### -field RIL_PARAM_POSITION_UMTS_FREQINFO_NT


### -field RIL_PARAM_POSITION_UMTS_UARFCN


### -field RIL_PARAM_POSITION_UMTS_PRIMARY_SC


### -field RIL_PARAM_POSITION_UMTS_RSCP


### -field RIL_PARAM_POSITION_UMTS_ECNO


### -field RIL_PARAM_POSITION_UMTS_PATHLOSS


### -field RIL_PARAM_POSITION_UMTS_ALL

