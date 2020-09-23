---
UID: NE:ntddrilapitypes.RILPOSITIONINFOGSMPARAMMASK
title: RILPOSITIONINFOGSMPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILPOSITIONINFOGSMPARAMMASK.
old-location: netvista\rilpositioninfogsmparammask.htm
tech.root: netvista
ms.assetid: 9785ef86-8a2f-4e08-8caf-aa25f52a76ab
ms.date: 02/16/2018
keywords: ["RILPOSITIONINFOGSMPARAMMASK enumeration"]
ms.keywords: RILPOSITIONINFOGSMPARAMMASK, RILPOSITIONINFOGSMPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_POSITION_GSM_ALL, RIL_PARAM_POSITION_GSM_ARFCN, RIL_PARAM_POSITION_GSM_BSID, RIL_PARAM_POSITION_GSM_CELLID, RIL_PARAM_POSITION_GSM_LAC, RIL_PARAM_POSITION_GSM_MCC, RIL_PARAM_POSITION_GSM_MNC, RIL_PARAM_POSITION_GSM_RXLEVEL, RIL_PARAM_POSITION_GSM_TA, netvista.rilpositioninfogsmparammask, rilapitypes/RILPOSITIONINFOGSMPARAMMASK, rilapitypes/RIL_PARAM_POSITION_GSM_ALL, rilapitypes/RIL_PARAM_POSITION_GSM_ARFCN, rilapitypes/RIL_PARAM_POSITION_GSM_BSID, rilapitypes/RIL_PARAM_POSITION_GSM_CELLID, rilapitypes/RIL_PARAM_POSITION_GSM_LAC, rilapitypes/RIL_PARAM_POSITION_GSM_MCC, rilapitypes/RIL_PARAM_POSITION_GSM_MNC, rilapitypes/RIL_PARAM_POSITION_GSM_RXLEVEL, rilapitypes/RIL_PARAM_POSITION_GSM_TA
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
targetos: Windows
req.typenames: RILPOSITIONINFOGSMPARAMMASK
f1_keywords:
 - RILPOSITIONINFOGSMPARAMMASK
 - ntddrilapitypes/RILPOSITIONINFOGSMPARAMMASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFOGSMPARAMMASK
---

# RILPOSITIONINFOGSMPARAMMASK enumeration (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILPOSITIONINFOGSMPARAMMASK.

## -enum-fields

### -field RIL_PARAM_POSITION_GSM_MCC

### -field RIL_PARAM_POSITION_GSM_MNC

### -field RIL_PARAM_POSITION_GSM_LAC

### -field RIL_PARAM_POSITION_GSM_CELLID

### -field RIL_PARAM_POSITION_GSM_TA

### -field RIL_PARAM_POSITION_GSM_ARFCN

### -field RIL_PARAM_POSITION_GSM_BSID

### -field RIL_PARAM_POSITION_GSM_RXLEVEL

### -field RIL_PARAM_POSITION_GSM_ALL

## -syntax

```cpp
enum RILPOSITIONINFOGSMPARAMMASK {
  RIL_PARAM_POSITION_GSM_MCC      = 0x00000001,
  RIL_PARAM_POSITION_GSM_MNC      = 0x00000002,
  RIL_PARAM_POSITION_GSM_LAC      = 0x00000004,
  RIL_PARAM_POSITION_GSM_CELLID   = 0x00000008,
  RIL_PARAM_POSITION_GSM_TA       = 0x00000010,
  RIL_PARAM_POSITION_GSM_ARFCN    = 0x00000020,
  RIL_PARAM_POSITION_GSM_BSID     = 0x00000040,
  RIL_PARAM_POSITION_GSM_RXLEVEL  = 0x00000080,
  RIL_PARAM_POSITION_GSM_ALL      = 0x000000ff

};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>