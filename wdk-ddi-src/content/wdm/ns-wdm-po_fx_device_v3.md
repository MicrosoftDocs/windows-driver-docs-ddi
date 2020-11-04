    ---
UID: NS:wdm._PO_FX_DEVICE_V3
title: PO_FX_DEVICE_V3
description: 
tech.root: 
ms.assetid: d3c6749b-2661-40a6-b4a7-937710bc36fe
ms.date: 08/19/2019
keywords: ["PO_FX_DEVICE_V3 structure"]
ms.keywords: PO_FX_DEVICE_V3, PO_FX_DEVICE_V3, *PPO_FX_DEVICE_V3, *PPO_FX_DEVICE, PO_FX_DEVICE
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: PO_FX_DEVICE_V3, *PPO_FX_DEVICE_V3
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _PO_FX_DEVICE_V3
 - wdm/_PO_FX_DEVICE_V3
 - PPO_FX_DEVICE_V3
 - wdm/PPO_FX_DEVICE_V3
 - PO_FX_DEVICE_V3
 - wdm/PO_FX_DEVICE_V3
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PO_FX_DEVICE_V3
product:
 - Windows
---

# PO_FX_DEVICE_V3 structure


## -description

The <b>PO_FX_DEVICE_V3</b> structure describes the power attributes of a device to the power management framework (PoFx), DFx (Directed [PoFx](/windows-hardware/drivers/kernel/overview-of-the-power-management-framework))

## -struct-fields

### -field Version

The version number of this structure. If the driver will register for directed power support with DFx, set this member to <b>PO_FX_VERSION_V3</b>.

### -field Flags

Controls whether direct child devices and power child devices can opt out of Directed PoFx.

Possible flag values include:

|Flag|Description|
|-|-|
|**PO_FX_DEVICE_FLAG_DIRECT_CHILDREN_OPTIONAL**|Allows direct child devices of this device to optionally support Directed PoFx. If not set, all direct children must support Directed PoFx for this device to fully support Directed PoFx.|
|**PO_FX_DEVICE_FLAG_POWER_CHILDREN_OPTIONAL**|Allows power child devices of this device to optionally support Directed PoFx. If not provided, all power children must support Directed PoFx for this device to fully support Directed PoFx.|
|**PO_FX_DEVICE_FLAG_DFX_CHILDREN_OPTIONAL**|Sets both **PO_FX_DEVICE_FLAG_DIRECT_CHILDREN_OPTIONAL** and **PO_FX_DEVICE_FLAG_POWER_CHILDREN_OPTIONAL**|

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

### -field DirectedPowerUpCallback

A pointer to the [*PO_FX_DIRECTED_POWER_UP_CALLBACK*](nc-wdm-po_fx_directed_power_up_callback.md) callback routine that is implemented by the device driver.  A device can provide only the `DirectedPower*` callbacks when registering for PoFx. It does not need to implement the rest of the PoFx callbacks.

### -field DirectedPowerDownCallback

A pointer to the [*PO_FX_DIRECTED_POWER_DOWN_CALLBACK*](nc-wdm-po_fx_directed_power_down_callback.md) callback routine that is implemented by the device driver.

### -field DirectedFxTimeoutInSeconds

Provides a hint to the framework specifying a recommended timeout in seconds in which the device should have idled out after software activity is no longer present. The default value is 2 minutes.

### -field DeviceContext

A pointer to a caller-allocated device context. This pointer is passed as a parameter to each driver-implemented callback function that is pointed to by this structure. The device driver uses this context to store information about the current power state of the device. This context is opaque to PoFx.

### -field ComponentCount

The number of elements in the <b>Components</b> array. Additionally, this member specifies the number of components in the device.

### -field Components

This member is the first element in an array of one or more PO_FX_COMPONENT_V2 elements. If the array contains more than one element, the additional elements immediately follow the <b>PO_FX_DEVICE_V2</b> structure. The array contains one element for each component in the device.  The Fx power state of each component can be controlled independently of the Fx power states of the other components in the device. The <b>ANYSIZE_ARRAY</b> constant is defined to be 1 in the Ntdef.h header file.

## -remarks

To register a device with PoFx, a driver calls the [**PoFxRegisterDevice**](./nf-wdm-pofxregisterdevice.md) routine and supplies, as a parameter, a pointer to a <b>PO_FX_DEVICE</b> structure that describes the device.  To use PoFx but not DFx, register with PoFx using either [PO_FX_DEVICE_V2 structure](./ns-wdm-_po_fx_device_v2.md) or PO_FX_DEVICE_V3 structure.

Each element in the <b>Components</b> array describes the power state attributes of one component in the device. Each component in the device is identified by its <b>Components</b> array index. Routines such as  <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxactivatecomponent">PoFxActivateComponent</a> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxcompleteidlecondition">PoFxCompleteIdleCondition</a> use the array index of a component to identify the component.

A device driver is not required to implement all eight callback routines. The driver can set a function pointer in the <b>PO_FX_DEVICE</b> structure to NULL if the driver does not implement the corresponding callback routine. However, certain callback routines must be implemented. Specifically, if one or more components in a device has more than one Fx state, the driver must implement <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a>, <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a>, and <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a> routines. Otherwise, device registration fails and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> returns <b>STATUS_INVALID_PARAMETER</b>.

## -see-also

https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-the-directed-power-management-framework

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