---
UID: NE:rilapitypes.RILADDRESSTYPE
title: RILADDRESSTYPE (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladdresstype_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILADDRESSTYPE enumeration"]
ms.keywords: RILADDRESSTYPE, RILADDRESSTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_ADDRTYPE_ABBREV, RIL_ADDRTYPE_ALPHANUM, RIL_ADDRTYPE_EMAIL, RIL_ADDRTYPE_INTERNATIONAL, RIL_ADDRTYPE_IP, RIL_ADDRTYPE_MAX, RIL_ADDRTYPE_NATIONAL, RIL_ADDRTYPE_NETWKSPECIFIC, RIL_ADDRTYPE_SUBSCRIBER, RIL_ADDRTYPE_URI, netvista.riladdresstype_2, rilapitypes/RILADDRESSTYPE, rilapitypes/RIL_ADDRTYPE_ABBREV, rilapitypes/RIL_ADDRTYPE_ALPHANUM, rilapitypes/RIL_ADDRTYPE_EMAIL, rilapitypes/RIL_ADDRTYPE_INTERNATIONAL, rilapitypes/RIL_ADDRTYPE_IP, rilapitypes/RIL_ADDRTYPE_MAX, rilapitypes/RIL_ADDRTYPE_NATIONAL, rilapitypes/RIL_ADDRTYPE_NETWKSPECIFIC, rilapitypes/RIL_ADDRTYPE_SUBSCRIBER, rilapitypes/RIL_ADDRTYPE_URI
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
targetos: Windows
req.typenames: RILADDRESSTYPE
req.product: Windows 10 or later.
f1_keywords:
 - RILADDRESSTYPE
 - rilapitypes/RILADDRESSTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILADDRESSTYPE
---

# RILADDRESSTYPE enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_ADDRTYPE_UNKNOWN

### -field RIL_ADDRTYPE_INTERNATIONAL

### -field RIL_ADDRTYPE_NATIONAL

### -field RIL_ADDRTYPE_NETWKSPECIFIC

### -field RIL_ADDRTYPE_SUBSCRIBER

### -field RIL_ADDRTYPE_ALPHANUM

### -field RIL_ADDRTYPE_ABBREV

### -field RIL_ADDRTYPE_IP

### -field RIL_ADDRTYPE_EMAIL

### -field RIL_ADDRTYPE_URI

### -field RIL_ADDRTYPE_MAX

## -syntax

```cpp
typedef enum _RILADDRESSTYPE {
  RIL_ADDRTYPE_INTERNATIONAL,
  RIL_ADDRTYPE_NATIONAL,
  RIL_ADDRTYPE_NETWKSPECIFIC,
  RIL_ADDRTYPE_SUBSCRIBER,
  RIL_ADDRTYPE_ALPHANUM,
  RIL_ADDRTYPE_ABBREV,
  RIL_ADDRTYPE_IP,
  RIL_ADDRTYPE_EMAIL,
  RIL_ADDRTYPE_URI,
  RIL_ADDRTYPE_MAX
} RILADDRESSTYPE;
```

