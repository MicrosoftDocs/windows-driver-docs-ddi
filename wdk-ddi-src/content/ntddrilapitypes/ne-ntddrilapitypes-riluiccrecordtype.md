---
UID: NE:ntddrilapitypes.RILUICCRECORDTYPE
title: RILUICCRECORDTYPE (ntddrilapitypes.h)
description: This enumeration describes the RILUICCRECORDTYPE.
old-location: netvista\riluiccrecordtype.htm
tech.root: netvista
ms.assetid: 962970e2-1861-4872-b0f3-db307f36d5d8
ms.date: 02/16/2018
keywords: ["RILUICCRECORDTYPE enumeration"]
ms.keywords: RILUICCRECORDTYPE, RILUICCRECORDTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_UICCRECORDTYPE_BERTLV, RIL_UICCRECORDTYPE_CYCLIC, RIL_UICCRECORDTYPE_LINEAR, RIL_UICCRECORDTYPE_MASTER, RIL_UICCRECORDTYPE_TRANSPARENT, RIL_UICCRECORDTYPE_UNKNOWN, netvista.riluiccrecordtype, rilapitypes/RILUICCRECORDTYPE, rilapitypes/RIL_UICCRECORDTYPE_BERTLV, rilapitypes/RIL_UICCRECORDTYPE_CYCLIC, rilapitypes/RIL_UICCRECORDTYPE_LINEAR, rilapitypes/RIL_UICCRECORDTYPE_MASTER, rilapitypes/RIL_UICCRECORDTYPE_TRANSPARENT, rilapitypes/RIL_UICCRECORDTYPE_UNKNOWN
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
req.typenames: RILUICCRECORDTYPE
f1_keywords:
 - RILUICCRECORDTYPE
 - ntddrilapitypes/RILUICCRECORDTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCRECORDTYPE
---

# RILUICCRECORDTYPE enumeration (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCRECORDTYPE.

## -enum-fields

### -field RIL_UICCRECORDTYPE_UNKNOWN

### -field RIL_UICCRECORDTYPE_TRANSPARENT

### -field RIL_UICCRECORDTYPE_CYCLIC

### -field RIL_UICCRECORDTYPE_LINEAR

### -field RIL_UICCRECORDTYPE_BERTLV

### -field RIL_UICCRECORDTYPE_MASTER

### -field RIL_UICCRECORDTYPE_DEDICATED

### -field RIL_UICCRECORDTYPE_MAX

## -syntax

```cpp
enum RILUICCRECORDTYPE {
  RIL_UICCRECORDTYPE_UNKNOWN      = 0x00000000,
  RIL_UICCRECORDTYPE_TRANSPARENT  = 0x00000001,
  RIL_UICCRECORDTYPE_CYCLIC       = 0x00000002,
  RIL_UICCRECORDTYPE_LINEAR       = 0x00000003,
  RIL_UICCRECORDTYPE_BERTLV       = 0x00000004,
  RIL_UICCRECORDTYPE_MASTER       = 0x00000005

};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>