---
UID: NE:ntddrilapitypes.RILSUBSCRIBERINFOPARAMMASK
title: RILSUBSCRIBERINFOPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILSUBSCRIBERINFOPARAMMASK.
old-location: netvista\rilsubscriberinfoparammask.htm
tech.root: netvista
ms.assetid: 271492ee-9053-4150-9e31-f121c9a94097
ms.date: 02/16/2018
keywords: ["RILSUBSCRIBERINFOPARAMMASK enumeration"]
ms.keywords: RILSUBSCRIBERINFOPARAMMASK, RILSUBSCRIBERINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SI_ADDRESS, RIL_PARAM_SI_ALL, RIL_PARAM_SI_DESCRIPTION, RIL_PARAM_SI_SERVICE, netvista.rilsubscriberinfoparammask, rilapitypes/RILSUBSCRIBERINFOPARAMMASK, rilapitypes/RIL_PARAM_SI_ADDRESS, rilapitypes/RIL_PARAM_SI_ALL, rilapitypes/RIL_PARAM_SI_DESCRIPTION, rilapitypes/RIL_PARAM_SI_SERVICE
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
req.typenames: RILSUBSCRIBERINFOPARAMMASK
f1_keywords:
 - RILSUBSCRIBERINFOPARAMMASK
 - ntddrilapitypes/RILSUBSCRIBERINFOPARAMMASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILSUBSCRIBERINFOPARAMMASK
---

# RILSUBSCRIBERINFOPARAMMASK enumeration (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILSUBSCRIBERINFOPARAMMASK.

## -enum-fields

### -field RIL_PARAM_SI_ADDRESS

### -field RIL_PARAM_SI_DESCRIPTION

### -field RIL_PARAM_SI_SERVICE

### -field RIL_PARAM_SI_ALL

## -syntax

```cpp
enum RILSUBSCRIBERINFOPARAMMASK {
  RIL_PARAM_SI_ADDRESS      = 0x00000001,
  RIL_PARAM_SI_DESCRIPTION  = 0x00000002,
  RIL_PARAM_SI_SERVICE      = 0x00000004,
  RIL_PARAM_SI_ALL          = 0x00000007

};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>