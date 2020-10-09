---
UID: NS:ntddrilapitypes.RILUICCLOCK
title: RILUICCLOCK (ntddrilapitypes.h)
description: This structure represents a RILUICCLOCK.
old-location: netvista\riluicclock.htm
tech.root: netvista
ms.assetid: 634c2177-8e6f-4967-a555-928eb512fce3
ms.date: 02/16/2018
keywords: ["RILUICCLOCK structure"]
ms.keywords: "*LPRILUICCLOCK, RILUICCLOCK, RILUICCLOCK structure [Network Drivers Starting with Windows Vista], netvista.riluicclock, rilapitypes/RILUICCLOCK"
req.header: ntddrilapitypes.h
req.include-header: Ntddrilapitypes.h
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
req.typenames: RILUICCLOCK, *LPRILUICCLOCK
f1_keywords:
 - RILUICCLOCK
 - ntddrilapitypes/RILUICCLOCK
 - LPRILUICCLOCK
 - ntddrilapitypes/LPRILUICCLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCLOCK
---

# RILUICCLOCK structure (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILUICCLOCK.

## -struct-fields

### -field hUiccApp

Specifies the UICC application context for this lock. In the case of PIN1 or UPIN, more than one application may make reference to the same key.

### -field dwKeyRef

The key for this lock of <a href="..\rilapitypes\ne-rilapitypes-riluicckeyref.md">RILUICCKEYREF</a> type. PIN1 keys are in the range 0x01..0x08 and may be shared by multiple applications. The Universal PIN is designated with key 0x11. PIN2 keys are in the range 0x81..0x88 and are local to each application (not shared). Two additional special values are defined: 0x00 represents a lock that is always verified (the “ALWays” access condition on the UICC) and 0xFF represents a lock that cannot be verified (the “NEVer” access condition).

## -syntax

```cpp
struct RILUICCLOCK {
  HUICCAPP hUiccApp;
  DWORD    dwKeyRef;
};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>