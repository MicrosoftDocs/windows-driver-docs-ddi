---
UID: NS:iddcx.IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER
title: IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER
ms.date: 10/20/2020
tech.root: display
targetos: Windows
description: IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER contains the information resulting from a buffer release and acquire operation.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER
f1_keywords:
 - IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER
 - iddcx/IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER
dev_langs:
 - c++
---

## -description

**IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER** contains the information resulting from a buffer release and acquire operation.

## -struct-fields

### -field pMetaData [out]

Pointer to a [**IDDCX_METADATA**](ns-iddcx-iddcx_metadata.md) structure containing per-frame metadata and frame information.

### -field pBufferInfo [out]

Pointer to a [**IDDCX_SYSTEM_BUFFER_INFO**](ns-iddcx-iddcx_system_buffer_info.md) structure containing a buffer's surface information.

## -remarks

An indirect display driver (IDD) passes a pointer to a **IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER** when it calls [**IddCxSwapChainReleaseAndAcquireSystemBuffer**](ns-iddcx-idarg_out_releaseandacquiresystembuffer.md).

> [!NOTE]
>  The IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER structure contains pointers to two other structures that should be set by the driver as in the following example code:

```
IDDCX_METADATA MetaData = {};
IDDCX_SYSTEM_BUFFER_INFO SystemBufferInfo = {};
IDARG_OUT_RELEASEANDACQUIRESYSTEMBUFFER system_Buffer = { &MetaData, &SystemBufferInfo };
HRESULT hr = IddCxSwapChainReleaseAndAcquireSystemBuffer(m_hSwapChain, &system_Buffer);
```

## -see-also

[**IDDCX_METADATA**](ns-iddcx-iddcx_metadata.md)

[**IDDCX_SYSTEM_BUFFER_INFO**](ns-iddcx-iddcx_system_buffer_info.md)

[**IddCxSwapChainReleaseAndAcquireSystemBuffer**](ns-iddcx-idarg_out_releaseandacquiresystembuffer.md)
