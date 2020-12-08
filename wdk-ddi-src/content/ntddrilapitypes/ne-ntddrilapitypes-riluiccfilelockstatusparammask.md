---
UID: NE:ntddrilapitypes.RILUICCFILELOCKSTATUSPARAMMASK
title: RILUICCFILELOCKSTATUSPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILUICCFILELOCKSTATUSPARAMMASK.
old-location: netvista\riluiccfilelockstatusparammask.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["RILUICCFILELOCKSTATUSPARAMMASK enumeration"]
ms.keywords: RILUICCFILELOCKSTATUSPARAMMASK, RILUICCFILELOCKSTATUSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_UFLS_ACCESSCONDITION, RIL_PARAM_UFLS_ALL, RIL_PARAM_UFLS_PINREFERENCE, netvista.riluiccfilelockstatusparammask, rilapitypes/RILUICCFILELOCKSTATUSPARAMMASK, rilapitypes/RIL_PARAM_UFLS_ACCESSCONDITION, rilapitypes/RIL_PARAM_UFLS_ALL, rilapitypes/RIL_PARAM_UFLS_PINREFERENCE
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
req.typenames: RILUICCFILELOCKSTATUSPARAMMASK
f1_keywords:
 - RILUICCFILELOCKSTATUSPARAMMASK
 - ntddrilapitypes/RILUICCFILELOCKSTATUSPARAMMASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCFILELOCKSTATUSPARAMMASK
---

# RILUICCFILELOCKSTATUSPARAMMASK enumeration (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCFILELOCKSTATUSPARAMMASK.

## -enum-fields

### -field RIL_PARAM_UFLS_ACCESSCONDITION

### -field RIL_PARAM_UFLS_PINREFERENCE

### -field RIL_PARAM_UFLS_ALL

## -syntax

```cpp
enum RILUICCFILELOCKSTATUSPARAMMASK {
  RIL_PARAM_UFLS_ACCESSCONDITION  = 0x00000001,
  RIL_PARAM_UFLS_PINREFERENCE     = 0x00000002,
  RIL_PARAM_UFLS_ALL              = 0x00000003

};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>
