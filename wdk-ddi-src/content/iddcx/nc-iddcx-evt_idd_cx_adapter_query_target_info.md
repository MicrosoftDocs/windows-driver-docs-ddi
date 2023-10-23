---
UID: NC:iddcx.EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO
tech.root: display
title: EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO callback function.
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
 - EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO
f1_keywords:
 - EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO
 - iddcx/EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO
---

## -description

The OS calls an indirect display driver's **EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO** callback function to retrieve information about target capabilities.

## -parameters

### -param AdapterObject

[in] The adapter object of the adapter being queried. This adapter object was returned in a call to [**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md).

### -param pInArgs

[in] A pointer to an [**IDARG_IN_QUERYTARGET_INFO**](ns-iddcx-idarg_in_querytarget_info.md) structure containing input arguments for this function.

### -param pOutArgs

[out] A pointer to an [**IDARG_OUT_QUERYTARGET_INFO**](ns-iddcx-idarg_out_querytarget_info.md) structure containing output arguments for this function.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, the callback should return an appropriate NTSTATUS error code.

## -remarks

The OS calls **EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO** after a driver calls [**IddCxMonitorArrival**](nf-iddcx-iddcxmonitorarrival.md). The OS uses the connector index provided by the driver in the [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md) call for this monitor.

Specifying [**IDDCX_BITS_PER_COMPONENT_NONE**](ne-iddcx-iddcx_bits_per_component.md) is valid; however, to enable HDR, current Windows policies require either the ability to send 10 or more bits per component to a monitor or alternatively for the driver to support dithering of more than 8 bits per component down to 8 bits per component. The ability to dither allows HDR to be supported at 4K resolutions over HDMI 2.0.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_QUERYTARGET_INFO**](ns-iddcx-idarg_in_querytarget_info.md)

[**IDARG_OUT_QUERYTARGET_INFO**](ns-iddcx-idarg_out_querytarget_info.md)

[**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md)

[**IddCxMonitorArrival**](nf-iddcx-iddcxmonitorarrival.md)

[**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md)
