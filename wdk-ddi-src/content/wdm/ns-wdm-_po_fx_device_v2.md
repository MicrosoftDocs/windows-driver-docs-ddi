---
UID: NS:wdm._PO_FX_DEVICE_V2
title: "_PO_FX_DEVICE_V2"
author: windows-driver-content
description: The PO_FX_DEVICE structure describes the power attributes of a device to the power management framework (PoFx).
old-location: kernel\po_fx_device.htm
old-project: kernel
ms.assetid: E2413C3A-79D3-47E3-A664-80869A721F37
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPO_FX_DEVICE, *PPO_FX_DEVICE_V2, PO_FX_DEVICE, PO_FX_DEVICE structure [Kernel-Mode Driver Architecture], PO_FX_DEVICE_V1, PO_FX_DEVICE_V1 structure [Kernel-Mode Driver Architecture], PO_FX_DEVICE_V2, PPO_FX_DEVICE_V1, PPO_FX_DEVICE_V1 structure pointer [Kernel-Mode Driver Architecture], _PO_FX_DEVICE_V2, kernel.po_fx_device, wdm/PO_FX_DEVICE, wdm/PO_FX_DEVICE_V1, wdm/PPO_FX_DEVICE_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	PO_FX_DEVICE_V1
product: Windows
targetos: Windows
req.typenames: PO_FX_DEVICE_V2, *PPO_FX_DEVICE_V2
req.product: Windows 10 or later.
---

# _PO_FX_DEVICE_V2 structure


## -description


The <b>PO_FX_DEVICE</b> structure describes the power attributes of a device to the power management framework (PoFx).


## -syntax


````
typedef struct _PO_FX_DEVICE_V1 {
  ULONG                                      Version;
  ULONG                                      ComponentCount;
#if PO_FX_VERSION_V2
  ULONGLONG                                  Flags;
#endif 
  PPO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK ComponentActiveConditionCallback;
  PPO_FX_COMPONENT_IDLE_CONDITION_CALLBACK   ComponentIdleConditionCallback;
  PPO_FX_COMPONENT_IDLE_STATE_CALLBACK       ComponentIdleStateCallback;
  PPO_FX_DEVICE_POWER_REQUIRED_CALLBACK      DevicePowerRequiredCallback;
  PPO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK  DevicePowerNotRequiredCallback;
  PPO_FX_POWER_CONTROL_CALLBACK              PowerControlCallback;
  PVOID                                      DeviceContext;
  PO_FX_COMPONENT                            Components[ANYSIZE_ARRAY];
} PO_FX_DEVICE_V1, *PPO_FX_DEVICE_V1, PO_FX_DEVICE;
````


## -struct-fields




### -field Version

The version number of this structure. If the driver will register for performance state support with PoFx, set this member to <b>PO_FX_VERSION_V2</b>. Otherwise, set this member to <b>PO_FX_VERSION_V1</b>.


#### - Flags

Set to 0. Currently, no flags are defined for this member.




### -field ComponentActiveConditionCallback

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406416">ComponentActiveConditionCallback</a> callback routine that is implemented by the device driver.


### -field ComponentIdleConditionCallback

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a> callback routine that is implemented by the device driver.


### -field ComponentIdleStateCallback

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a> callback routine that is implemented by the device driver.


### -field DevicePowerRequiredCallback

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450949">DevicePowerRequiredCallback</a> callback routine that is implemented by the device driver.


### -field DevicePowerNotRequiredCallback

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450946">DevicePowerNotRequiredCallback</a> callback routine that is implemented by the device driver.


### -field PowerControlCallback

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439564">PowerControlCallback</a> callback routine that is implemented by the device driver.


### -field DeviceContext

A pointer to a caller-allocated device context. This pointer is passed as a parameter to each driver-implemented callback function that is pointed to by this structure. The device driver uses this context to store information about the current power state of the device. This context is opaque to PoFx.


### -field ComponentCount

The number of elements in the <b>Components</b> array. Additionally, this member specifies the number of components in the device.


### -field Components

This member is the first element in an array of one or more <a href="..\wdm\ns-wdm-_po_fx_component_v2.md">PO_FX_COMPONENT</a> elements. If the array contains more than one element, the additional elements immediately follow the <b>PO_FX_DEVICE</b> structure. The array contains one element for each component in the device.  The Fx power state of each component can be controlled independently of the Fx power states of the other components in the device. The <b>ANYSIZE_ARRAY</b> constant is defined to be 1 in the Ntdef.h header file.


## -remarks



To register a device with PoFx, a driver calls the <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> routine and supplies, as a parameter, a pointer to a <b>PO_FX_DEVICE</b> structure that describes the device.

Each element in the <b>Components</b> array describes the power state attributes of one component in the device. Each component in the device is identified by its <b>Components</b> array index. Routines such as  <a href="..\wdm\nf-wdm-pofxactivatecomponent.md">PoFxActivateComponent</a> and <a href="..\wdm\nf-wdm-pofxcompleteidlecondition.md">PoFxCompleteIdleCondition</a> use the array index of a component to identify the component.

A device driver is not required to implement all six callback routines. The driver can set a function pointer in the <b>PO_FX_DEVICE</b> structure to NULL if the driver does not implement the corresponding callback routine. However, certain callback routines must be implemented. Specifically, if one or more components in a device has more than one Fx state, the driver must implement <a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh406416">ComponentActiveConditionCallback</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a> routines. Otherwise, device registration fails and <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> returns <b>STATUS_INVALID_PARAMETER</b>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406416">ComponentActiveConditionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a>



<a href="..\wdm\nf-wdm-pofxcompleteidlecondition.md">PoFxCompleteIdleCondition</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a>



<a href="..\wdm\ns-wdm-_po_fx_component_v2.md">PO_FX_COMPONENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450946">DevicePowerNotRequiredCallback</a>



<a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450949">DevicePowerRequiredCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439564">PowerControlCallback</a>



<a href="..\wdm\nf-wdm-pofxactivatecomponent.md">PoFxActivateComponent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_DEVICE_V1 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

