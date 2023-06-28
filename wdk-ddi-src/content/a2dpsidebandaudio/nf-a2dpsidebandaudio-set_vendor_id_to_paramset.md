---
UID: NF:a2dpsidebandaudio.SET_VENDOR_ID_TO_PARAMSET
tech.root: audio
title: SET_VENDOR_ID_TO_PARAMSET (a2dpsidebandaudio.h)
description: This topic describes the macro to set the Vendor ID from the VENDOR PARAMS SET derived from SIDEBAND_PARAMS_SET_A2DP_VENDOR_BASE
ms.date: 05/20/2021
targetos: Windows
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: a2dpsidebandaudio.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - a2dpsidebandaudio.h
api_name:
 - SET_VENDOR_ID_TO_PARAMSET
f1_keywords:
 - SET_VENDOR_ID_TO_PARAMSET
 - a2dpsidebandaudio/SET_VENDOR_ID_TO_PARAMSET
dev_langs:
 - c++
---

# SET_VENDOR_ID_TO_PARAMSET 

## -description

This macro to set the Vendor ID from the VENDOR PARAMS SET derived from SIDEBAND_PARAMS_SET_A2DP_VENDOR_BASE is defined as follows.

```cpp
#define VENDOR_ID_MASK 0x0000FFFF

#define SET_VENDOR_ID_TO_PARAMSET(paramSet, vendorId) ((paramSet).Data1 = ((vendorId) & VENDOR_ID_MASK))
```

## -parameters

### -param paramSet

A parameter set. (Additional Information Pending)

### -param vendorId

The Vendor ID (Additional Information Pending)

## -remarks


## -see-also

[A2DPSidebandAudio](./index.md/)

[GET_VENDOR_ID_FROM_PARAMSET](/windows-hardware/drivers/ddi/get_vendor_id_from_paramset)

