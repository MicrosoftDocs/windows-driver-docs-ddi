---
UID: NS:wdm._PO_FX_COMPONENT_V2
title: "_PO_FX_COMPONENT_V2"
author: windows-driver-content
description: The PO_FX_COMPONENT structure describes the power state attributes of a component in a device.
old-location: kernel\po_fx_component.htm
old-project: kernel
ms.assetid: 4ACCA041-C638-4124-AFC1-3F34671C9EF8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPO_FX_COMPONENT, *PPO_FX_COMPONENT_V2, PO_FX_COMPONENT, PO_FX_COMPONENT structure [Kernel-Mode Driver Architecture], PO_FX_COMPONENT_V2, PO_FX_COMPONENT_V2 structure [Kernel-Mode Driver Architecture], PPO_FX_COMPONENT_V2, PPO_FX_COMPONENT_V2 structure pointer [Kernel-Mode Driver Architecture], _PO_FX_COMPONENT_V2, kernel.po_fx_component, wdm/PO_FX_COMPONENT, wdm/PO_FX_COMPONENT_V2, wdm/PPO_FX_COMPONENT_V2"
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
-	PO_FX_COMPONENT_V2
product: Windows
targetos: Windows
req.typenames: PO_FX_COMPONENT_V2, *PPO_FX_COMPONENT_V2
req.product: Windows 10 or later.
---

# _PO_FX_COMPONENT_V2 structure


## -description


The <b>PO_FX_COMPONENT</b> structure describes the power state attributes of a component in a device.


## -syntax


````
typedef struct _PO_FX_COMPONENT_V2 {
  GUID                        Id;
#if PO_FX_VERSION_V2
  ULONGLONG                   Flags;
#endif 
  ULONG                       IdleStateCount;
  ULONG                       DeepestWakeableIdleState;
  PPO_FX_COMPONENT_IDLE_STATE IdleStates;
#if PO_FX_VERSION_V2
  ULONG                       ProviderCount;
  PULONG                      Providers;
#endif 
} PO_FX_COMPONENT_V2, *PPO_FX_COMPONENT_V2, PO_FX_COMPONENT;
````


## -struct-fields




### -field Id

A component ID that uniquely identifies this component with respect to the other components in the device. The driver should specify a nonzero value for this member if the power management framework (PoFx) requires a component ID to distinguish this component from other, similar components in the same device. This member is optional. If this member is not used, it must be set to all zeros.


#### - Flags

This member can be set to the following flag bit: <b>PO_FX_COMPONENT_FLAG_F0_ON_DX</b>. For more information, see Remarks.


### -field DeepestWakeableIdleState

The index of the deepest Fx state from which the component can wake. Specify 0 for F0, 1 for F1, and so on. This index must be less than <b>IdleStateCount</b>.


### -field IdleStateCount

The number of elements in the array that is pointed to by the <b>IdleStates</b> member. Additionally, this member specifies the number of Fx power states that the component supports. A component must support at least one Fx state (F0).


### -field IdleStates

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_idle_state.md">PO_FX_COMPONENT_IDLE_STATE</a> array. The length of this array is specified by the <b>IdleStateCount</b> member. Each array element specifies the attributes of an Fx power state that is supported by the component. Element 0 describes F0, element 1 describes F1, and so on.


#### - ProviderCount

A value that specifies the number of components this component depends on. For more information, see <i>Component dependencies</i> under Remarks.


#### - Providers

A pointer to an array of component indexes this component depends on. For more information, see <i>Component dependencies</i> under Remarks.


## -remarks



When a device driver registers a device with PoFx, the driver supplies a <a href="..\wudfwdm\ns-wudfwdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that holds the registration information. This structure contains an array of <b>PO_FX_COMPONENT</b> structures. The elements in this array describe the power attributes of the individual components in the device. PoFx uses the information in this array to manage the power settings of these components.

The <b>Id</b> member contains a component ID that PoFx can use to uniquely identify a component. Do not confuse the component ID with the component index, which a routine such as <a href="..\wdm\nf-wdm-pofxactivatecomponent.md">PoFxActivateComponent</a> uses to identify a component in a registered device. A component index is an index into the <b>Components</b> array in the <b>PO_FX_DEVICE</b> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes are integer values in the range 0 to N–1. In contrast, a component ID is a GUID value.

The <b>Flags</b> member may be set to the <b>PO_FX_COMPONENT_FLAG_F0_ON_DX</b> value if the driver specified support for <b>PO_FX_VERSION_V2</b> during registration with PoFx (that is, during the call to the <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> routine, the driver specified the value <b>PO_FX_VERSION_V2</b> for the <b>Version</b> member of the <a href="..\wudfwdm\ns-wudfwdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that was passed to the <i>Device</i> parameter).  If the <b>PO_FX_COMPONENT_FLAG_F0_ON_DX</b> flag is specified, PoFx will place the component into the F0 power state during Dx transitions and for wait/wake IRPs.
Before dispatching a Dx IRP or wait/wake IRP to the device stack (whichever event happens first), the power manager will transition the component into the F0 state. The component will be kept in F0 until the wake/wait IRP is canceled or completed, or the Dx IRP is completed and driver has called the <a href="..\wdm\nf-wdm-pofxreportdevicepoweredon.md">PoFxReportDevicePoweredOn</a> routine (whichever event happens last).

<h3><a id="Component_dependencies"></a><a id="component_dependencies"></a><a id="COMPONENT_DEPENDENCIES"></a>Component dependencies</h3>
PoFx supports logical component dependencies within a device (but not across different devices). During device registration for each component, the driver can supply a number (the <i>ProviderCount</i> member) and an array of component indexes (the <i>Providers</i> member) this component depends on; these are known as <i>providers</i>. PoFx guarantees that the component will not become active until all of its providers are active.


Component dependencies form a directed graph where an edge points from a dependent component to a provider and represents a dependency. During device registration, PoFx validates the dependency graph: cycles and repeated edges are not allowed and the depth of the graph for the depth-first search traversal cannot exceed four. PoFx also sets the components’ active reference count according to the dependency graph; that is, each provider’s active reference count is incremented once for each component that depends on it.


During the component activation, PoFx asynchronously activates all providers first. After a component is active, PoFx checks every dependent component and continues their activation if necessary.


When the component transitions to the idle state, PoFx first makes the dependent components idle. After the driver completes the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a> and the platform extension plug-in (PEP) is notified that the component is idle, PoFx recursively traverses the dependency graph in breadth-first traversal and asynchronously idles each provider.





## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450935">Component-Level Power Management</a>



<a href="..\wudfwdm\ns-wudfwdm-_po_fx_device_v1.md">PO_FX_DEVICE</a>



<a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_idle_state.md">PO_FX_COMPONENT_IDLE_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_COMPONENT_V2 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

