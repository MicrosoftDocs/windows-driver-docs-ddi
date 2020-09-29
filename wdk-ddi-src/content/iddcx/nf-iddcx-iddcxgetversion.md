---
UID: NF:iddcx.IddCxGetVersion
title: IddCxGetVersion
ms.date: 09/24/2020
ms.topic: language-reference
tech.root: display
ms.assetid: a0101d24-415f-4376-8842-a7012cce2092
targetos: Windows
description: IddCxGetVersion is an OS callback function that an indirect display (ID) driver calls to obtain the IddCx version.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - iddcx.h
api_name:
 - IddCxGetVersion
f1_keywords:
 - IddCxGetVersion
 - iddcx/IddCxGetVersion
dev_langs:
 - c++
---

## -description

**IddCxGetVersion** is an OS callback function that an indirect display (ID) driver calls to obtain the IddCx version (Indirect Display Driver Class eXtension).

## -parameters

### -param pOutArgs

[out] Pointer to an [**IDARG_OUT_GETVERSION**](ns-iddcx-idarg_out_getversion.md) structure in which the current IddCx version is returned. See Remarks.

## -returns

(NTSTATUS) **IddCxGetVersion** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it returns an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

See [**IDARG_OUT_GETVERSION**](ns-iddcx-idarg_out_getversion.md) for a list of possible version values.

## -see-also

[**IDARG_OUT_GETVERSION**](ns-iddcx-idarg_out_getversion.md)
