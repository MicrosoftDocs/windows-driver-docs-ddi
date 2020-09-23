---
UID: NS:ntddrilapitypes.RILSUBSCRIBERINFO
title: RILSUBSCRIBERINFO (ntddrilapitypes.h)
description: This structure represents RILSUBSCRIBERINFO.
old-location: netvista\rilsubscriberinfo.htm
tech.root: netvista
ms.assetid: b05a38c6-afc5-4dc1-8e51-ecf9d47e144e
ms.date: 02/16/2018
keywords: ["RILSUBSCRIBERINFO structure"]
ms.keywords: "*LPRILSUBSCRIBERINFO, RILSUBSCRIBERINFO, RILSUBSCRIBERINFO structure [Network Drivers Starting with Windows Vista], netvista.rilsubscriberinfo, rilapitypes/RILSUBSCRIBERINFO"
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
req.typenames: RILSUBSCRIBERINFO, *LPRILSUBSCRIBERINFO
f1_keywords:
 - RILSUBSCRIBERINFO
 - ntddrilapitypes/RILSUBSCRIBERINFO
 - LPRILSUBSCRIBERINFO
 - ntddrilapitypes/LPRILSUBSCRIBERINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILSUBSCRIBERINFO
---

# RILSUBSCRIBERINFO structure (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILSUBSCRIBERINFO.

## -struct-fields

### -field cbSize

The size of the structure in bytes.

### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilsubscriberinfoparammask.md">RILSUBSCRIBERINFOPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

### -field raAddress

Phone number of the subscriber line, of type <a href="..\rilapitypes\ne-rilapitypes-riladdresstype.md">RILADDRESSTYPE</a>.

### -field wszDescription

Text description of the subscriber line.

### -field dwService

Specifies the service related to the subscriber phone number, of type <a href="..\rilapitypes\ne-rilapitypes-rilsubscriberinfoservice.md">RILSUBSCRIBERINFOSERVICE</a>.

## -syntax

```cpp
struct RILSUBSCRIBERINFO {
  DWORD                    cbSize;
  DWORD                    dwParams;
  RILADDRESS               raAddress;
  WCHAR                    wszDescription[MAXLENGTH_DESCRIPTION];
  RILSUBSCRIBERINFOSERVICE dwService;
};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>