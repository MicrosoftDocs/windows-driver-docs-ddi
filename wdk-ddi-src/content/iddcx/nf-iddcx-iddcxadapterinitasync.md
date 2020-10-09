---
UID: NF:iddcx.IddCxAdapterInitAsync
title: IddCxAdapterInitAsync function (iddcx.h)
description: IddCxAdapterInitAsync is an asynchronous initiation function called by the driver to create a WDDM graphics adapter.
old-location: display\iddcxadapterinitasync.htm
tech.root: display
ms.assetid: c23d0d24-b043-4e39-afd3-abab6bb84769
ms.date: 09/24/2020
keywords: ["IddCxAdapterInitAsync function"]
ms.keywords: IddCxAdapterInitAsync, IddCxAdapterInitAsync method [Display Devices], display.iddcxadapterinitasync, iddcx/IddCxAdapterInitAsync
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: IddCxStub.lib
req.dll: IddCx.dll
req.irql: _Must_inspect_result_
targetos: Windows
req.typenames: 
f1_keywords:
 - IddCxAdapterInitAsync
 - iddcx/IddCxAdapterInitAsync
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - IddCx.dll
api_name:
 - IddCxAdapterInitAsync
---

# IddCxAdapterInitAsync function

## -description

**IddCxAdapterInitAsync** is an asynchronous initiation function called by the indirect display driver (IDD) to create a WDDM graphics adapter.

## -parameters

### -param pInArgs

[in] Pointer to an [**IDARG_IN_ADAPTER_INIT**](ns-iddcx-idarg_in_adapter_init.md) structure containing the information needed to initialize an adapter that will be hosted on a WDF device.

### -param pOutArgs

[out] Pointer to an [**IDARG_OUT_ADAPTER_INIT**](ns-iddcx-idarg_out_adapter_init.md) structure in which the IDD returns information about the initialized adapter.

## -returns

(NTSTATUS) The method returns S_OK if the operation succeeds. Otherwise, it returns an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -see-also

[**IDARG_IN_ADAPTER_INIT**](ns-iddcx-idarg_in_adapter_init.md)

[**IDARG_OUT_ADAPTER_INIT**](ns-iddcx-idarg_out_adapter_init.md)
