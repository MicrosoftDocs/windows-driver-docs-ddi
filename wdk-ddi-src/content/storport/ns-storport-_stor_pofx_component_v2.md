---
UID: NS:storport._STOR_POFX_COMPONENT_V2
title: _STOR_POFX_COMPONENT_V2 (storport.h)
description: The STOR_POFX_COMPONENT_V2 structure describes the power state attributes of a storage device component.
old-location: storage\stor_pofx_component_v2.htm
tech.root: storage
ms.assetid: 2FF6B375-C213-48AC-9497-6CE3F1170BAA
ms.date: 03/29/2018
ms.keywords: "*PSTOR_POFX_COMPONENT_V2, PSTOR_POFX_COMPONENT_V2, PSTOR_POFX_COMPONENT_V2 structure pointer [Storage Devices], STOR_POFX_COMPONENT_V2, STOR_POFX_COMPONENT_V2 structure [Storage Devices], _STOR_POFX_COMPONENT_V2, storage.stor_pofx_component_v2, storport/PSTOR_POFX_COMPONENT_V2, storport/STOR_POFX_COMPONENT"
f1_keywords:
 - "storport/STOR_POFX_COMPONENT_V2"
req.header: storport.h
req.include-header: 
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
- storport.h
api_name:
- STOR_POFX_COMPONENT_V2
product:
- Windows
targetos: Windows
req.typenames: STOR_POFX_COMPONENT_V2, *PSTOR_POFX_COMPONENT_V2
---

# _STOR_POFX_COMPONENT_V2 structure

## -description

The **STOR_POFX_COMPONENT_V2** structure describes the power state attributes of a storage device component.

## -struct-fields

### -field Version

The version number of this structure. Set this member to **STOR_POFX_DEVICE_VERSION_V2**.

### -field Size

The size of this structure. Set this value to **STOR_POFX_COMPONENT_V2_SIZE**.

### -field FStateCount

The number of elements in the array that is pointed to by the **FStates** member. Additionally, this member specifies the number of functional power states (F-state) that the component supports. A component must support at least one F-state (F0).

### -field DeepestWakeableFState

The index of the deepest F-state from which the component can wake. Specify 0 for F0, 1 for F1, and so on. This index must be less than **FStateCount**.

### -field Id

A component ID that uniquely identifies this component with respect to the other components in the device. The driver should specify a nonzero value for this member if the power management framework (PoFx) requires a component ID to distinguish this component from other, similar components in the same device. The component IDs supported by Storport are STORPORT_POFX_ADAPTER_GUID (identifies an adapter) and STORPORT_POFX_LUN_GUID (identifies a unit).

### -field DeepestAdapterPowerRequiredFState

The deepest F-State that this component can be in where the adapter still requires power. This is only relevant for components whose ID is STOR_POFX_LUN_GUID.

### -field DeepestCrashDumpReadyFState

The deepest F-State that the component can be in where the miniport can power up the component in the event a crash occurs and a crash dump needs to be written.

### -field FStates

An array of [STOR_POFX_COMPONENT_IDLE_STATE](ns-storport-_stor_pofx_component_idle_state.md) structures. The length of this array is specified by the **FStateCount** member. Each array element specifies the attributes of an F-state that is supported by the component. Element 0 describes F0, element 1 describes F1, and so on. When more than one idle state structure is required, the additional structures are allocated at the end of the **STOR_ POFX_COMPONENT_V2** structure and the **FStateCount** is set to 1, which is the value of ANYSIZE_ARRAY, plus the count of the additional structures.

#### - DeepestWakeableIdleState

The index of the deepest F-state from which the component can wake. Specify 0 for F0, 1 for F1, and so on. This index must be less than **FStateCount**.

## -remarks

When a miniport driver registers a device with the Storport power management framework, the miniport driver supplies a [STOR_POFX_DEVICE](ns-storport-_stor_pofx_device.md) structure that holds the registration information. This structure contains an array of **STOR_ POFX_COMPONENT** structures. The elements in this array describe the power attributes of the individual components in the device. The power settings of these components are managed based on the information in this array.

The **Id** member contains a component ID that uniquely identifies a component. The component ID is not the same as the component index, which a routine such as [StorPortPoFxActivateComponent](nf-storport-storportpofxactivatecomponent.md) uses to identify a component in a registered device. A component index is an index into the **Components** array in the STOR_POFX_DEVICE structure that the device driver used to register the device. If the **Components** array contains N elements, component indexes are integer values in the range 0 to N–1. In contrast, a component ID is a GUID value.

The ID for the single adapter device component is defined in *storport.h* as STORPORT_POFX_ADAPTER_GUID. The ID for the single unit device component is STORPORT_POFX_LUN_GUID. Use these identifiers when describing either an adapter component or a unit component in the **Id** member.

The F-state requirements are as follows:

* For an adapter device component, the miniport must specify a single component and up to eight F-states for the adapter. [StorPortInitializePoFxPower](nf-storport-storportinitializepofxpower.md) should be called by the miniport only within the context of the miniport's passive initialization routine.
* For a unit device component, the miniport must specify a single component for the unit, and can specify up to two F-states. The unit device must have the F0 state specified and can optionally have one additional F-state. **StorPortInitializePoFxPower** should be called by the miniport only within the context of the miniport's [ScsiUnitPoFxPowerInfo Unit Control](nc-storport-hw_unit_control.md).

For a unit device component, if an additional F-state is included in the **FStates** array, the size member remains set to **STOR_POFX_COMPONENT_SIZE** and does not include the size of the additional [STOR_POFX_COMPONENT_IDLE_STATE](ns-storport-_stor_pofx_component_idle_state.md) structure.

## -see-also

[HW_UNIT_CONTROL](nc-storport-hw_unit_control.md)

[STOR_POFX_COMPONENT](ns-storport-_stor_pofx_component.md)

[STOR_POFX_COMPONENT_IDLE_STATE](ns-storport-_stor_pofx_component_idle_state.md)

[STOR_POFX_DEVICE](ns-storport-_stor_pofx_device.md)

[StorPortInitializePoFxPower](nf-storport-storportinitializepofxpower.md)

[StorPortPoFxActivateComponent](nf-storport-storportpofxactivatecomponent.md)
