---
UID: NF:a2dpsidebandaudio.GET_VENDOR_ID_FROM_PARAMSET
tech.root: 
title: GET_VENDOR_ID_FROM_PARAMSET
ms.date: 05/14/2021
targetos: Windows
description: 
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
 - GET_VENDOR_ID_FROM_PARAMSET
f1_keywords:
 - GET_VENDOR_ID_FROM_PARAMSET
 - a2dpsidebandaudio/GET_VENDOR_ID_FROM_PARAMSET
dev_langs:
 - c++
---

## -description

This macro to get the Vendor ID from the VENDOR PARAMS SET derived from SIDEBAND_PARAMS_SET_A2DP_VENDOR_BASE is defined as follows.

```cpp
#define VENDOR_ID_MASK 0x0000FFFF

#define GET_VENDOR_ID_FROM_PARAMSET(paramSet) ((paramSet).Data1 & VENDOR_ID_MASK)
```

**SIDEBAND_PARAMS_SET_A2DP_VENDOR_BASE**

Base GUID for Vendor-defined A2DP Sideband Set of Parameters

The audio driver sets the 32 bit Data1 element to a Vendor ID. The upper 16
bits shall be set to 0. The lower 16 bit shall be set to a valid Company ID
as defined in Bluetooth Assigned Numbers.

For additional information, see https://www.bluetooth.com/specifications/assigned-numbers/company-identifiers

{xxxxxxxx-FE37-468B-AF72-411C0E5A3FFC}
DEFINE_GUID(SIDEBAND_PARAMS_SET_A2DP_VENDOR_BASE,
    0x00000000, 0xfe37, 0x468b, 0xaf, 0x72, 0x41, 0x1c, 0xe, 0x5a, 0x3f, 0xfc);


## -parameters

### -param paramSet

A parameter set. (Additional Information Pending)


## -remarks



## -see-also

[A2DPSidebandAudio](/windows-hardware/drivers/ddi/a2dpsidebandaudio/)

[SET_VENDOR_ID_FROM_PARAMSET](/windows-hardware/drivers/ddi/set_vendor_id_from_paramset)