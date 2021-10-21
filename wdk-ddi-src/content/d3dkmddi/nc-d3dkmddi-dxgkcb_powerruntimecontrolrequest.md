---
UID: NC:d3dkmddi.DXGKCB_POWERRUNTIMECONTROLREQUEST
title: DXGKCB_POWERRUNTIMECONTROLREQUEST (d3dkmddi.h)
description: Called by the display miniport driver to exchange information with the Power Engine Plug-in (PEP).
old-location: display\dxgkcbpowerruntimecontrolrequest.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_POWERRUNTIMECONTROLREQUEST callback function"]
ms.keywords: DXGKCB_POWERRUNTIMECONTROLREQUEST, DXGKCB_POWERRUNTIMECONTROLREQUEST callback, DxgkCbPowerRuntimeControlRequest, DxgkCbPowerRuntimeControlRequest callback function [Display Devices], PDXGKCB_POWERRUNTIMECONTROLREQUEST, d3dkmddi/DxgkCbPowerRuntimeControlRequest, display.dxgkcbpowerruntimecontrolrequest
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8 (WDDM 1.2)
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_POWERRUNTIMECONTROLREQUEST
 - d3dkmddi/DXGKCB_POWERRUNTIMECONTROLREQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKCB_POWERRUNTIMECONTROLREQUEST
---

# DXGKCB_POWERRUNTIMECONTROLREQUEST callback function

## -description

A kernel-mode display miniport driver calls **DXGKCB_POWERRUNTIMECONTROLREQUEST** to exchange information with the Power Engine Plug-in (PEP).

## -parameters

### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md) structure in a call to its [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -param PowerControlCode [in]

A pointer to a GUID that defines the meaning of the display miniport driver's control request. For more information, see Remarks.

### -param InBuffer [in, optional]

An optional pointer to an input buffer.

### -param InBufferSize [in]

The size, in bytes, of the optional buffer that **InBuffer** points to. Set to zero if no **InBuffer** is provided.

### -param OutBuffer [in, optional]

An optional pointer to an output buffer.

### -param OutBufferSize [in]

The size, in bytes, of the optional buffer that **OutBuffer** points to. Set to zero if no **OutBuffer** is provided.

### -param BytesReturned [out]

The number of actual bytes returned in the buffer that **OutBuffer** points to. The returned value will be <= **OutBufferSize**.

## -returns

**DXGKCB_POWERRUNTIMECONTROLREQUEST** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

> [!NOTE]
>
> To avoid a possible deadlock, do not call the [**DXGKCB_SETPOWERCOMPONENTACTIVE**](nc-d3dkmddi-dxgkcb_setpowercomponentactive.md) function until this function has returned.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbPowerRuntimeControlRequest** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

Although the driver can use any GUID in the **PowerControlCode** parameter, the following GUIDs that are defined in *D3dkmddi.h* are recommended. By using these GUIDs, the display port driver can issue Event Tracing for Windows (ETW) events, which are useful to profile driver performance issues.

| GUID | Meaning |
| ---- | ------- |
| GUID_DXGKDDI_POWER_VOLTAGE_UP     | Increase the voltage. |
| GUID_DXGKDDI_POWER_VOLTAGE_DOWN   | Decrease the voltage. |
| GUID_DXGKDDI_POWER_VOLTAGE        | Change the voltage, but the driver doesn't know if the change is an increase or decrease. |
| GUID_DXGKDDI_POWER_CLOCK_UP       | Increase the clock setting. |
| GUID_DXGKDDI_POWER_CLOCK_DOWN     | Decrease the clock setting. |
| GUID_DXGKDDI_POWER_CLOCK          | Change the clock setting, but the driver doesn't know if the change is an increase or decrease. |
| GUID_DXGKDDI_POWER_BANDWIDTH_UP   | Increase the bandwidth. |
| GUID_DXGKDDI_POWER_BANDWIDTH_DOWN | Decrease the bandwidth. |
| GUID_DXGKDDI_POWER_BANDWIDTH      | Change the bandwidth, but the driver doesn't know if the change is an increase or decrease. |

These GUIDs do not imply that there is any communication protocol between the display miniport driver and the PEP, nor do they imply that there are any restrictions on the values that can be passed between the display miniport driver and the PEP.

## -see-also

[**DXGKCB_SETPOWERCOMPONENTACTIVE**](nc-d3dkmddi-dxgkcb_setpowercomponentactive.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
