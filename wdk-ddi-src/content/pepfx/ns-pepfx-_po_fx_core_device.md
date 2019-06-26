---
UID: NS:pepfx._PO_FX_CORE_DEVICE
title: _PO_FX_CORE_DEVICE (pepfx.h)
description: The PO_FX_CORE_DEVICE structure contains information about the power-state attributes of the components in a core system resource, and provides a software interface for power-managing these components.
old-location: kernel\po_fx_core_device.htm
tech.root: kernel
ms.assetid: 46C16795-412B-48E7-A7E8-E474CEC51849
ms.date: 04/30/2018
ms.keywords: "*PPO_FX_CORE_DEVICE, PO_FX_CORE_DEVICE, PO_FX_CORE_DEVICE structure [Kernel-Mode Driver Architecture], PPO_FX_CORE_DEVICE, PPO_FX_CORE_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PO_FX_CORE_DEVICE, kernel.po_fx_core_device, pepfx/PO_FX_CORE_DEVICE, pepfx/PPO_FX_CORE_DEVICE"
ms.topic: struct
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PO_FX_CORE_DEVICE
product:
- Windows
targetos: Windows
req.typenames: PO_FX_CORE_DEVICE, *PPO_FX_CORE_DEVICE
---

# _PO_FX_CORE_DEVICE structure


## -description


The <b>PO_FX_CORE_DEVICE</b> structure contains information about the power-state attributes of the components in a core system resource, and provides a software interface for power-managing these components.


## -struct-fields




### -field Version

The version number of this structure.


### -field ComponentCount

The number of elements in the <b>Components</b> array at the end of this structure. This count includes all elements of the array, and includes both the first element, which is a member of this structure,  and any additional elements that follow the end of this structure.


### -field ComponentActiveConditionCallback

A pointer to a  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a> callback routine. PoFx calls this routine to notify the driver that the specified component completed a transition from the idle condition to the active condition.


### -field ComponentIdleConditionCallback

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a> callback routine. PoFx calls this routine to notify the driver that the specified component completed a transition from the active condition to the idle condition.


### -field ComponentCriticalTransitionCallback

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-po_fx_component_critical_transition_callback">ComponentCriticalTransitionCallback</a> callback routine. PoFx calls this routine to notify the driver that the specified component is about to make a transition between the idle condition and the active condition.


### -field ComponentIdleStateCallback

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a> callback routine. PoFx calls this routine to notify the driver of a pending change to the F<i>x</i> power state of the specified component.


### -field DeviceContext

A pointer to a PEP-defined device context. PoFx supplies this pointer as the first parameter in calls to the <i>ComponentActiveConditionCallback</i>, <i>ComponentIdleConditionCallback</i>, <i>ComponentCriticalTransitionCallback</i>, and <i>ComponentIdleStateCallback</i> routines. This context is opaque to PoFx.


### -field Components

The first element in an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_po_fx_component_v1">PO_FX_COMPONENT</a> structures. Each element in the array describes the power attributes of a component in the device. If the array contains more than one element, the additional elements immediately follow the end of the <b>PO_FX_CORE_DEVICE</b> structure. The number of elements in the array is specified in the <b>ComponentCount</b> member of the <b>PO_FX_CORE_DEVICE</b> structure.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/nf-pepfx-pofxregistercoredevice">PoFxRegisterCoreDevice</a> routine.

A <i>core system resource</i> is a hardware device, such as a timer or an interrupt controller, that is managed by the Windows hardware abstraction layer (HAL).

For more information about component transitions between the active condition and the idle condition, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/component-level-power-management">Component-Level Power Management</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-po_fx_component_critical_transition_callback">ComponentCriticalTransitionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_po_fx_component_v1">PO_FX_COMPONENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/nf-pepfx-pofxregistercoredevice">PoFxRegisterCoreDevice</a>
 

 

