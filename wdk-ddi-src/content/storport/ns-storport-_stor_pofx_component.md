---
UID: NS:storport._STOR_POFX_COMPONENT
title: "_STOR_POFX_COMPONENT"
author: windows-driver-content
description: The STOR_POFX_COMPONENT structure describes the power state attributes of a storage device component.
old-location: storage\stor_pofx_component.htm
old-project: storage
ms.assetid: D44FF0C7-D82C-4CDD-A5F9-BBD8257C6771
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PSTOR_POFX_COMPONENT, PSTOR_POFX_COMPONENT, STOR_POFX_COMPONENT structure [Storage Devices], storage.stor_pofx_component, storport/PSTOR_POFX_COMPONENT, PSTOR_POFX_COMPONENT structure pointer [Storage Devices], _STOR_POFX_COMPONENT, STOR_POFX_COMPONENT, storport/STOR_POFX_COMPONENT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	STOR_POFX_COMPONENT
product: Windows
targetos: Windows
req.typenames: "*PSTOR_POFX_COMPONENT, STOR_POFX_COMPONENT"
req.product: Windows 10 or later.
---

# _STOR_POFX_COMPONENT structure


## -description


The <b>STOR_POFX_COMPONENT</b> structure describes the power state attributes of a storage device component.


## -syntax


````
typedef struct _PO_FX_COMPONENT {
  ULONG                          Version;
  USHORT                         Size;
  ULONG                          FStateCount;
  ULONG                          DeepestWakeableIdleState;
  GUID                           Id;
  STOR_POFX_COMPONENT_IDLE_STATE FStates[ANYSIZE_ARRAY];
} STOR_POFX_COMPONENT, *PSTOR_POFX_COMPONENT;
````


## -struct-fields




### -field Version

The version number of this structure. Set this member to <b>STOR_POFX_DEVICE_VERSION_V1</b>.


### -field Size

The size of this structure. Set this value to <b>STOR_POFX_COMPONENT_SIZE</b>.


### -field FStateCount

The number of elements in the array that is pointed to by the <b>FStates</b> member. Additionally, this member specifies the number of functional power states (F-state) that the component supports. A component must support at least one F-state (F0).


### -field DeepestWakeableFState

 


### -field Id

A component ID that uniquely identifies this component with respect to the other components in the device. The driver should specify a nonzero value for this member if the power management framework (PoFx) requires a component ID to distinguish this component from other, similar components in the same device. The component IDs supported by Storport are STORPORT_POFX_ADAPTER_GUID and STORPORT_POFX_LUN_GUID.


### -field FStates

A array of  <a href="..\storport\ns-storport-_stor_pofx_component_idle_state.md">STOR_POFX_COMPONENT_IDLE_STATE</a> structures. The length of this array is specified by the <b>FStateCount</b> member. Each array element specifies the attributes of an F-state that is supported by the component. Element 0 describes F0, element 1 describes F1, and so on. When more than one idle state structure is required, the additional structures are allocated at the end of the <b>STOR_ POFX_COMPONENT</b> structure and the <b>FStateCount</b> is set to 1, the value of ANYSIZE_ARRAY, plus the count of the additional structures.


#### - DeepestWakeableIdleState

The index of the deepest F-state from which the component can wake. Specify 0 for F0, 1 for F1, and so on. This index must be less than <b>FStateCount</b>.


## -remarks


When a miniport driver registers a device with the Storport power management framework, the miniport driver supplies a <a href="..\storport\ns-storport-_stor_pofx_device.md">STOR_POFX_DEVICE</a> structure that holds the registration information. This structure contains an array of <b>STOR_ POFX_COMPONENT</b> structures. The elements in this array describe the power attributes of the individual components in the device. The power settings of these components are managed based on the information in this array.

The <b>Id</b> member contains a component ID that uniquely identifies a component. The component ID is not the same as the component index, which a routine such as <a href="..\storport\nf-storport-storportpofxactivatecomponent.md">StorPortPoFxActivateComponent</a> uses to identify a component in a registered device. A component index is an index into the <b>Components</b> array in the <a href="..\storport\ns-storport-_stor_pofx_device.md">STOR_POFX_DEVICE</a> structure that the device driver used to register the device. If the <b>Components</b> array contains N elements, component indexes are integer values in the range 0 to N–1. In contrast, a component ID is a GUID value.

The ID for the single adapter device component is defined in <i>storport.h</i> as STORPORT_POFX_ADAPTER_GUID. The ID for the single unit device component is STORPORT_POFX_LUN_GUID. Use these identifiers when describing either an adapter component or a unit component in the <b>Id</b> member.

For a adapter device component, a maximum of one F-state (F0) is permitted. For a unit device component, two F-states are allowed. The unit device must have the F0 state specified and optionally have one additional F-state.

For a unit device component, if an additional F-state is included in the <b>FStates</b> array, the size member remains set to <b>STOR_POFX_COMPONENT_SIZE</b> and does not include the size of the additional <a href="..\storport\ns-storport-_stor_pofx_component_idle_state.md">STOR_POFX_COMPONENT_IDLE_STATE</a> structure. 



## -see-also

<a href="..\storport\nf-storport-storportpofxactivatecomponent.md">StorPortPoFxActivateComponent</a>

<a href="..\storport\ns-storport-_stor_pofx_device.md">STOR_POFX_DEVICE</a>

<a href="..\storport\ns-storport-_stor_pofx_component_idle_state.md">STOR_POFX_COMPONENT_IDLE_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_POFX_COMPONENT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

