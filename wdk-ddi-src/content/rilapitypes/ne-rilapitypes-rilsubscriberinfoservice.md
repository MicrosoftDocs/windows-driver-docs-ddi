---
UID: NE:rilapitypes.RILSUBSCRIBERINFOSERVICE
title: RILSUBSCRIBERINFOSERVICE (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubscriberinfoservice_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILSUBSCRIBERINFOSERVICE enumeration"]
ms.keywords: RILSUBSCRIBERINFOSERVICE, RILSUBSCRIBERINFOSERVICE enumeration [Network Drivers Starting with Windows Vista], RIL_SERVICE_FAX, RIL_SERVICE_MAX, RIL_SERVICE_OTHER, RIL_SERVICE_VOICE, netvista.rilsubscriberinfoservice_2, rilapitypes/RILSUBSCRIBERINFOSERVICE, rilapitypes/RIL_SERVICE_FAX, rilapitypes/RIL_SERVICE_MAX, rilapitypes/RIL_SERVICE_OTHER, rilapitypes/RIL_SERVICE_VOICE
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
req.typenames: RILSUBSCRIBERINFOSERVICE
req.product: Windows 10 or later.
f1_keywords:
 - RILSUBSCRIBERINFOSERVICE
 - rilapitypes/RILSUBSCRIBERINFOSERVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILSUBSCRIBERINFOSERVICE
---

# RILSUBSCRIBERINFOSERVICE enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_SERVICE_UNKNOWN

### -field RIL_SERVICE_VOICE

### -field RIL_SERVICE_FAX

### -field RIL_SERVICE_OTHER

### -field RIL_SERVICE_MAX

## -syntax

```cpp
typedef enum _RILSUBSCRIBERINFOSERVICE {
  RIL_SERVICE_VOICE,
  RIL_SERVICE_FAX,
  RIL_SERVICE_OTHER,
  RIL_SERVICE_MAX
} RILSUBSCRIBERINFOSERVICE;
```

