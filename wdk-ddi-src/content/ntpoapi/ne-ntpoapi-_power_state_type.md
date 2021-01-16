---
UID: NE:ntpoapi._POWER_STATE_TYPE
title: _POWER_STATE_TYPE (ntpoapi.h)
description: The POWER_STATE_TYPE enumeration type indicates that a power state value is a system power state or a device power state.
old-location: kernel\power_state_type.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["POWER_STATE_TYPE enumeration"]
ms.keywords: "*PPOWER_STATE_TYPE, DevicePowerState, POWER_STATE_TYPE, POWER_STATE_TYPE enumeration [Kernel-Mode Driver Architecture], PPOWER_STATE_TYPE, PPOWER_STATE_TYPE enumeration pointer [Kernel-Mode Driver Architecture], SystemPowerState, _POWER_STATE_TYPE, kernel.power_state_type, sysenum_bdfdaea1-ec64-4b74-96d0-95641797ebb4.xml, wdm/DevicePowerState, wdm/POWER_STATE_TYPE, wdm/PPOWER_STATE_TYPE, wdm/SystemPowerState"
req.header: ntpoapi.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ntpoapi.h
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
req.typenames: POWER_STATE_TYPE, *PPOWER_STATE_TYPE
f1_keywords:
 - _POWER_STATE_TYPE
 - ntpoapi/_POWER_STATE_TYPE
 - PPOWER_STATE_TYPE
 - ntpoapi/PPOWER_STATE_TYPE
 - POWER_STATE_TYPE
 - ntpoapi/POWER_STATE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _POWER_STATE_TYPE
 - PPOWER_STATE_TYPE
 - POWER_STATE_TYPE
---

# _POWER_STATE_TYPE enumeration (ntpoapi.h)


## -description

The <b>POWER_STATE_TYPE</b> enumeration type indicates that a power state value is a system power state or a device power state.

## -enum-fields

### -field SystemPowerState

Indicates a <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_system_power_state">SYSTEM_POWER_STATE</a> value.

### -field DevicePowerState

Indicates a <a href="/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a> value.

## -remarks

The <b>POWER_STATE_TYPE</b> enumeration type is used in conjunction with a value of type <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_power_state">POWER_STATE</a> to indicate that the power state value is a system power state value or a device power state value. For an example, see <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-posetpowerstate">PoSetPowerState</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_power_state">POWER_STATE</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-posetpowerstate">PoSetPowerState</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_system_power_state">SYSTEM_POWER_STATE</a>

