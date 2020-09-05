---
UID: NE:rilapitypes.RILIMSSERVICE
title: RILIMSSERVICE (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsservice_2.htm
tech.root: netvista
ms.assetid: 9cac61e7-8260-49ef-881d-6430acb622a8
ms.date: 02/26/2018
keywords: ["RILIMSSERVICE enumeration"]
ms.keywords: RILIMSSERVICE, RILIMSSERVICE enumeration [Network Drivers Starting with Windows Vista], RIL_IMS_SERVICE_ALL, RIL_IMS_SERVICE_CUSTOM, RIL_IMS_SERVICE_E_VOICE, RIL_IMS_SERVICE_RCS, RIL_IMS_SERVICE_SUPSVC, RIL_IMS_SERVICE_USSD, RIL_IMS_SERVICE_VIDEO, RIL_IMS_SERVICE_VOICE, netvista.rilimsservice_2, rilapitypes/RILIMSSERVICE, rilapitypes/RIL_IMS_SERVICE_ALL, rilapitypes/RIL_IMS_SERVICE_CUSTOM, rilapitypes/RIL_IMS_SERVICE_E_VOICE, rilapitypes/RIL_IMS_SERVICE_RCS, rilapitypes/RIL_IMS_SERVICE_SUPSVC, rilapitypes/RIL_IMS_SERVICE_USSD, rilapitypes/RIL_IMS_SERVICE_VIDEO, rilapitypes/RIL_IMS_SERVICE_VOICE
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
req.typenames: RILIMSSERVICE
req.product: Windows 10 or later.
f1_keywords:
 - RILIMSSERVICE
 - rilapitypes/RILIMSSERVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILIMSSERVICE
---

# RILIMSSERVICE enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_IMS_SERVICE_SMS

### -field RIL_IMS_SERVICE_VOICE

### -field RIL_IMS_SERVICE_VIDEO

### -field RIL_IMS_SERVICE_CUSTOM

### -field RIL_IMS_SERVICE_SUPSVC

### -field RIL_IMS_SERVICE_RCS

### -field RIL_IMS_SERVICE_USSD

### -field RIL_IMS_SERVICE_E_VOICE

### -field RIL_IMS_SERVICE_ALL

## -syntax

```cpp
typedef enum _RILIMSSERVICE {
  RIL_IMS_SERVICE_VOICE,
  RIL_IMS_SERVICE_VIDEO,
  RIL_IMS_SERVICE_CUSTOM,
  RIL_IMS_SERVICE_SUPSVC,
  RIL_IMS_SERVICE_RCS,
  RIL_IMS_SERVICE_USSD,
  RIL_IMS_SERVICE_E_VOICE,
  RIL_IMS_SERVICE_ALL
} RILIMSSERVICE;
```

