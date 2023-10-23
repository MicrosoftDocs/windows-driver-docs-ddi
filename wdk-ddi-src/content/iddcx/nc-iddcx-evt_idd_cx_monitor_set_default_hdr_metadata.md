---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA
tech.root: display
title: EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA callback function.
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
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
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
 - EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA
f1_keywords:
 - EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA
 - iddcx/EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA
dev_langs:
 - c++
helpviewer_keywords:
 - EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA
---

## -description

The OS calls **EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA** to provide the default HDR10 metadata that a console driver should send to the monitor when default metadata is specified in a call to [**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md).

## -parameters

### -param MonitorObject

[in] An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object that is the OS context handle for the monitor. The OS provided this handle in a prior call to [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md).

### -param pInArgs

[in] Pointer to an [**IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA**](ns-iddcx-idarg_in_monitor_set_default_hdr_metadata.md) structure that contains the input arguments for this callback function.

## -returns

**EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA** returns an [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) value. If the operation is successful, it returns STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

The OS only calls this callback function for console drivers. It calls the driver for any monitor that supports HDR to tell the driver what default HDR metadata to use if the driver sets the [**IDDCX_ADAPTER_FLAGS_CAN_PROCESS_FP16**](ne-iddcx-iddcx_adapter_flags.md). flag. This call occurs after [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md) is called and before any calls to [**EVT_IDD_CX_ADAPTER_COMMIT_MODES2**](nc-iddcx-evt_idd_cx_adapter_commit_modes2.md). The driver should use this data whenever **IDDCX_HDRMETADATA_TYPE_DEFAULT** is specified as the metadata type in the [**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md) returned when calling [**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md). The OS can call the driver to update this default at any time.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA**](ns-iddcx-idarg_in_monitor_set_default_hdr_metadata.md)

[**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md)

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
