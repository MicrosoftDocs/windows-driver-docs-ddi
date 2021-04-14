---
UID: NS:storport._STOR_POWER_CONTROL_HEADER
tech.root: storage
title: STOR_POWER_CONTROL_HEADER
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_POWER_CONTROL_HEADER is a common power control header for both adapter and unit power-related control parameters.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: STOR_POWER_CONTROL_HEADER, *PSTOR_POWER_CONTROL_HEADER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_POWER_CONTROL_HEADER
 - PSTOR_POWER_CONTROL_HEADER
 - STOR_POWER_CONTROL_HEADER
f1_keywords:
 - _STOR_POWER_CONTROL_HEADER
 - storport/_STOR_POWER_CONTROL_HEADER
 - PSTOR_POWER_CONTROL_HEADER
 - storport/PSTOR_POWER_CONTROL_HEADER
 - STOR_POWER_CONTROL_HEADER
 - storport/STOR_POWER_CONTROL_HEADER
dev_langs:
 - c++
---

## -description

**STOR_POWER_CONTROL_HEADER** is a common power control header for both adapter and unit power-related control parameters.

## -struct-fields

### -field Version

The version of the parent structure. Set to 1.

### -field Size

Size of the parent structure, in bytes. For example, if the parent structure is **STOR_ADAPTER_CONTROL_POWER**, set **Size** to  ```sizeof(STOR_ADAPTER_CONTROL_POWER)```.

### -field Address

For a unit, **Address** points to a [**STOR_ADDRESS**](ns-storport-_stor_address.md) structure that holds the address of the unit the control operation is specified for. For adapters, **Address** is NULL.

## -remarks

**STOR_POWER_CONTROL_HEADER** is used when [**HwStorUnitControl**](nc-storport-hw_unit_control.md) and [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) are called with power-related controls.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**STOR_ADAPTER_CONTROL_POWER**](ns-storport-stor_adapter_control_power.md)

[**STOR_POFX_ACTIVE_CONTEXT**](ns-storport-stor_pofx_active_context.md)

[**STOR_POFX_FSTATE_CONTEXT**](ns-storport-stor_pofx_fstate_context.md)

[**STOR_POFX_POWER_CONTROL**](ns-storport-stor_pofx_power_control.md)

[**STOR_POFX_POWER_REQUIRED_CONTEXT**](ns-storport-stor_pofx_power_required_context.md)

[**STOR_POFX_UNIT_POWER_INFO**](ns-storport-stor_pofx_unit_power_info.md)
