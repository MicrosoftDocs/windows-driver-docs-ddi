---
UID: NC:iddcx.EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2
tech.root: display
title: EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2 callback function.
prerelease: false
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
 - EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2
f1_keywords:
 - EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2
 - iddcx/EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2
dev_langs:
 - c++
helpviewer_keywords:
 - EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2
---

## -description

The OS calls **EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2** to ask the driver to parse a monitor description into a list of modes that the monitor supports. The OS calls this callback version (instead of **EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION**) to allow the driver to report extra information needed for HDR10 or WCG monitor modes.

## -parameters

### -param pInArgs

[in] Pointer to an [**IDARG_IN_PARSEMONITORDESCRIPTION2**](ns-iddcx-idarg_in_parsemonitordescription2.md) structure that contains the input arguments for this callback function.

### -param pOutArgs

[out] Pointer to an [**IDARG_OUT_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_out_parsemonitordescription.md) structure that contains the output arguments for this callback function.

## -returns

**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2** returns an [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) value. If the operation is successful, it returns STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

A version 1.10 or later indirect display driver that supports HDR must expose this function to report modes. Setting the following [**IDDCX_WIRE_BITS_PER_COMPONENT**](ns-iddcx-iddcx_wire_bits_per_component.md) values is equivalent to creating a mode via the pre-1.10 functions:

* **BitsPerComponent.Rgb** to [**IDDCX_BITS_PER_COMPONENT_8**](ne-iddcx-iddcx_bits_per_component.md)
* **BitsPerComponent.YCbCr444**, **BitsPerComponent.YCbCr422** and **BitsPerComponent.YCbCr420** to **IDDCX_BITS_PER_COMPONENT_NONE**

Version 1.10 and later drivers that don't set the [**IDDCX_ADAPTER_FLAGS_CAN_PROCESS_FP16**](ne-iddcx-iddcx_adapter_flags.md) adapter flag can continue to report only the pre-1.10 function.

The [**IDDCX_MONITOR_MODE2::BitsPerComponent**](ns-iddcx-iddcx_monitor_mode2.md) field is designed to allow multiple formats and bit depths to be reported in a single mode. For example, a driver can report 8 and 10 bits per component in RGB by setting both **IDDCX_BITS_PER_COMPONENT_8** and **IDDCX_BITS_PER_COMPONENT_10** in **IDDCX_MONITOR_MODE2::BitsPerComponent::Rgb**. A driver should only report different bits per component as unique modes if other mode details also differ.

Drivers returning modes with SDR WCG or HDR parameters will fail if they have not also reported [**IDDCX_ADAPTER_FLAGS_CAN_PROCESS_FP16**](ne-iddcx-iddcx_adapter_flags.md) in the [**IddCxAdapterInitAsync**](nf-iddcx-iddcxadapterinitasync.md) call. SDR WCG and HDR parameters can be:

* Any value for **IDDCX_WIRE_BITS_PER_COMPONENT::BitsPerComponent.Rgb** other than **IDDCX_BITS_PER_COMPONENT_8**, or
* Any **IDDCX_WIRE_BITS_PER_COMPONENT::BitsPerComponent** value for **YCbCr444**, **YCbCr422**, or **YCbCr420** other than **IDDCX_BITS_PER_COMPONENT_NONE**.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_PARSEMONITORDESCRIPTION2**](ns-iddcx-idarg_in_parsemonitordescription2.md)

[**IDARG_OUT_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_out_parsemonitordescription.md)
