---
UID: NS:wdm._PO_FX_DEVICE_V2
title: _PO_FX_DEVICE_V2 (wdm.h)
description: The PO_FX_DEVICE structure describes the power attributes of a device to the power management framework (PoFx).
old-location: kernel\po_fx_device.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PO_FX_DEVICE_V2 structure"]
ms.keywords: "*PPO_FX_DEVICE, *PPO_FX_DEVICE_V2, PO_FX_DEVICE, PO_FX_DEVICE structure [Kernel-Mode Driver Architecture], PO_FX_DEVICE_V1, PO_FX_DEVICE_V1 structure [Kernel-Mode Driver Architecture], PO_FX_DEVICE_V2, PPO_FX_DEVICE_V1, PPO_FX_DEVICE_V1 structure pointer [Kernel-Mode Driver Architecture], _PO_FX_DEVICE_V2, kernel.po_fx_device, wdm/PO_FX_DEVICE, wdm/PO_FX_DEVICE_V1, wdm/PPO_FX_DEVICE_V1"
req.header: wdm.h
req.include-header: Wudfwdm.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.typenames: PO_FX_DEVICE_V2, *PPO_FX_DEVICE_V2
f1_keywords:
 - _PO_FX_DEVICE_V2
 - wdm/_PO_FX_DEVICE_V2
 - PPO_FX_DEVICE_V2
 - wdm/PPO_FX_DEVICE_V2
 - PO_FX_DEVICE_V2
 - wdm/PO_FX_DEVICE_V2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - PO_FX_DEVICE_V1
---

# _PO_FX_DEVICE_V2 structure


## -description

The <b>PO_FX_DEVICE</b> structure describes the power attributes of a device to the power management framework (PoFx).

## -struct-fields

### -field Version

The version number of this structure. If the driver will register for performance state support with PoFx, set this member to <b>PO_FX_VERSION_V2</b>. Otherwise, set this member to <b>PO_FX_VERSION_V1</b>.


#### - Flags

Set to 0. Currently, no flags are defined for this member.

### -field ComponentActiveConditionCallback

A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a> callback routine that is implemented by the device driver.

### -field ComponentIdleConditionCallback

A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a> callback routine that is implemented by the device driver.

### -field ComponentIdleStateCallback

A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a> callback routine that is implemented by the device driver.

### -field DevicePowerRequiredCallback

A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_required_callback">DevicePowerRequiredCallback</a> callback routine that is implemented by the device driver.

### -field DevicePowerNotRequiredCallback

A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_not_required_callback">DevicePowerNotRequiredCallback</a> callback routine that is implemented by the device driver.

### -field PowerControlCallback

A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_power_control_callback">PowerControlCallback</a> callback routine that is implemented by the device driver.

### -field DeviceContext

A pointer to a caller-allocated device context. This pointer is passed as a parameter to each driver-implemented callback function that is pointed to by this structure. The device driver uses this context to store information about the current power state of the device. This context is opaque to PoFx.

### -field ComponentCount

The number of elements in the <b>Components</b> array. Additionally, this member specifies the number of components in the device.

### -field Components

This member is the first element in an array of one or more <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_v1">PO_FX_COMPONENT</a> elements. If the array contains more than one element, the additional elements immediately follow the <b>PO_FX_DEVICE</b> structure. The array contains one element for each component in the device.  The Fx power state of each component can be controlled independently of the Fx power states of the other components in the device. The <b>ANYSIZE_ARRAY</b> constant is defined to be 1 in the Ntdef.h header file.

## -remarks

To register a device with PoFx, a driver calls the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine and supplies, as a parameter, a pointer to a <b>PO_FX_DEVICE</b> structure that describes the device.

Each element in the <b>Components</b> array describes the power state attributes of one component in the device. Each component in the device is identified by its <b>Components</b> array index. Routines such as  <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxactivatecomponent">PoFxActivateComponent</a> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxcompleteidlecondition">PoFxCompleteIdleCondition</a> use the array index of a component to identify the component.

A device driver is not required to implement all six callback routines. The driver can set a function pointer in the <b>PO_FX_DEVICE</b> structure to NULL if the driver does not implement the corresponding callback routine. However, certain callback routines must be implemented. Specifically, if one or more components in a device has more than one Fx state, the driver must implement <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a>, <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a>, and <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a> routines. Otherwise, device registration fails and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> returns <b>STATUS_INVALID_PARAMETER</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_not_required_callback">DevicePowerNotRequiredCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_required_callback">DevicePowerRequiredCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_v1">PO_FX_COMPONENT</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxactivatecomponent">PoFxActivateComponent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxcompleteidlecondition">PoFxCompleteIdleCondition</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_power_control_callback">PowerControlCallback</a>
