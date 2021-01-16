---
UID: NS:wdm._FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
title: _FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS (wdm.h)
description: The FUNCTION_LEVEL_DEVICE_RESET_PARAMETER structure is used as an argument to the DeviceReset routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface.
old-location: kernel\function_level_device_reset_parameters.htm
tech.root: kernel
ms.date: 11/15/2018
keywords: ["FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS structure"]
ms.keywords: "*PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS structure [Kernel-Mode Driver Architecture], PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS structure pointer [Kernel-Mode Driver Architecture], _FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, kernel.function_level_device_reset_parameters, wdm/FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, wdm/PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS"
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
req.irql: 
targetos: Windows
req.typenames: FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, *PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
f1_keywords:
 - _FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
 - wdm/_FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
 - PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
 - wdm/PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
 - FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
 - wdm/FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
 - PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
 - FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
---

# _FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS structure


## -description

The <b>FUNCTION_LEVEL_DEVICE_RESET_PARAMETER</b> structure  is used as an argument to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pdevice_reset_handler">DeviceReset</a> routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface. This structure specifies a callback routine that is called  when a function-level device reset is completed, and a context structure that is passed to the callback routine. For more information, see [Working with the GUID_DEVICE_RESET_INTERFACE_STANDARD](/windows-hardware/drivers/kernel/working-with-guid-device-reset-interface-standard)

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field DeviceResetCompletion

Pointer to a completion callback routine to be called when a function-level device reset is completed. The function prototype for this callback routine is defined as follows:


```
typedef
VOID
(*PDEVICE_RESET_COMPLETION)(
    _In_ NTSTATUS Status,
    _Inout_opt_ PVOID Context
    );
```

### -field CompletionContext

Points to a caller-supplied context structure to be passed to the <i>DeviceResetCompletion</i> callback.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_reset_interface_standard">DEVICE_RESET_INTERFACE_STANDARD</a>

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pdevice_reset_handler">DeviceReset</a>

[Working with the GUID_DEVICE_RESET_INTERFACE_STANDARD](/windows-hardware/drivers/kernel/working-with-guid-device-reset-interface-standard)

