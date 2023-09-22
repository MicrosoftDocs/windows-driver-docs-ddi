---
UID: NC:iddcx.EVT_IDD_CX_ADAPTER_COMMIT_MODES2
tech.root: display
title: EVT_IDD_CX_ADAPTER_COMMIT_MODES2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the EVT_IDD_CX_ADAPTER_COMMIT_MODES2 callback function.
prerelease: true
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
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx Version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - iddcx.h
api_name:
 - EVT_IDD_CX_ADAPTER_COMMIT_MODES2
f1_keywords:
 - EVT_IDD_CX_ADAPTER_COMMIT_MODES2
 - iddcx/EVT_IDD_CX_ADAPTER_COMMIT_MODES2
dev_langs:
 - c++
helpviewer_keywords:
 - EVT_IDD_CX_ADAPTER_COMMIT_MODES2
---

## -description

The OS calls **EVT_IDD_CX_ADAPTER_COMMIT_MODES2** to inform the driver of a mode change for monitors on the adapter.

## -parameters

### -param AdapterObject

[in] The OS-generated adapter object of the adapter being queried. This [**IDDCX_ADAPTER**](/windows-hardware/drivers/display/iddcx-objects#iddcx_adapter) object handle was returned in a previous call to [**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md).

### -param pInArgs

[in] Pointer to a [**IDARG_IN_COMMITMODES2**](ns-iddcx-idarg_in_commitmodes2.md) structure that contains arguments used by **EVT_IDD_CX_ADAPTER_COMMIT_MODES2**.

## -returns

**EVT_IDD_CX_ADAPTER_COMMIT_MODES2** returns an [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) value. If the operation is successful, it returns STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

When modes are committed for monitors, IddCx version 1.10 drivers that support HDR or WCG are called via this function and told the color space and bits per component to be used on the physical monitor connection. These values are based on the target capabilities and mode parameters previously reported by the driver. Reporting [adapter support for FP16](ns-iddcx-iddcx_adapter_caps.md) but not exposing this function is an error.

The color space specified in a committed mode does not specify the surface format used for every surface in a swapchain. The surface provided in [**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md) must still be queried.

The OS always provides the [**IDDCX_PATH2**](ns-iddcx-iddcx_path2.md) for every connected monitor even if that monitor isn't active, and indicates which paths have changed. If a path is marked inactive, then the whole display pipeline for that path will be powered off and no signal will be sent to the monitor.

When a new path is committed, the driver should program the display pipeline to display a black image until the first frame is ready to be displayed. To achieve this, WDDM visibility should be off until the first frame is ready to be displayed, then the visibility should be turned on.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_COMMITMODES2**](ns-iddcx-idarg_in_commitmodes2.md)

[**IDDCX_PATH2**](ns-iddcx-iddcx_path2.md)

[**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md)
