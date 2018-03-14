---
UID: NA:wudfwdm
ms.assetid: 09d3bb45-c5d1-38ed-82eb-ef09ddbc1057
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wudfwdm.h header



This header is used by Windows kernel, Windows Driver Framework. For more information, see
- [Windows kernel](../_kernel/index.md)
- [Windows Driver Framework](../_wdf/index.md)

Wudfwdm.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [AppendTailList function](nf-wudfwdm-appendtaillist.md) | The AppendTailList routine appends a doubly linked list of LIST_ENTRY structures to the tail of another doubly linked list of LIST_ENTRY structures. |
| [InitializeListHead function](nf-wudfwdm-initializelisthead.md) | The InitializeListHead routine initializes a LIST_ENTRY structure that represents the head of a doubly linked list. |
| [InsertHeadList function](nf-wudfwdm-insertheadlist.md) | The InsertHeadList routine inserts an entry at the head of a doubly linked list of LIST_ENTRY structures. |
| [InsertTailList function](nf-wudfwdm-inserttaillist.md) | The InsertTailList routine inserts an entry at the tail of a doubly linked list of LIST_ENTRY structures. |
| [IsListEmpty function](nf-wudfwdm-islistempty.md) | The IsListEmpty routine indicates whether a doubly linked list of LIST_ENTRY structures is empty. |
| [PopEntryList function](nf-wudfwdm-popentrylist.md) | The PopEntryList routine removes the first entry from a singly linked list of SINGLE_LIST_ENTRY structures. |
| [PushEntryList function](nf-wudfwdm-pushentrylist.md) | The PushEntryList routine inserts an entry at the beginning of a singly linked list of SINGLE_LIST_ENTRY structures. |
| [READ_REGISTER_BUFFER_UCHAR function](nf-wudfwdm-read_register_buffer_uchar.md) | The READ_REGISTER_BUFFER_UCHAR routine reads a number of bytes from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_ULONG function](nf-wudfwdm-read_register_buffer_ulong.md) | The READ_REGISTER_BUFFER_ULONG routine reads a number of ULONG values from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_ULONG64 function](nf-wudfwdm-read_register_buffer_ulong64.md) | The READ_REGISTER_BUFFER_ULONG64 function reads a number of ULONG64 values from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_USHORT function](nf-wudfwdm-read_register_buffer_ushort.md) | The READ_REGISTER_BUFFER_USHORT routine reads a number of USHORT values from the specified register address into a buffer. |
| [READ_REGISTER_UCHAR function](nf-wudfwdm-read_register_uchar.md) | The READ_REGISTER_UCHAR routine reads a byte from the specified register address. |
| [READ_REGISTER_ULONG function](nf-wudfwdm-read_register_ulong.md) | The READ_REGISTER_ULONG routine reads a ULONG value from the specified register address. |
| [READ_REGISTER_ULONG64 function](nf-wudfwdm-read_register_ulong64.md) | The READ_REGISTER_ULONG64 function reads a ULONG64 value from the specified register address. |
| [READ_REGISTER_USHORT function](nf-wudfwdm-read_register_ushort.md) | The READ_REGISTER_USHORT routine reads a USHORT value from the specified register address. |
| [RemoveEntryList function](nf-wudfwdm-removeentrylist.md) | The RemoveEntryList routine removes an entry from a doubly linked list of LIST_ENTRY structures. |
| [RemoveHeadList function](nf-wudfwdm-removeheadlist.md) | The RemoveHeadList routine removes an entry from the beginning of a doubly linked list of LIST_ENTRY structures. |
| [RemoveTailList function](nf-wudfwdm-removetaillist.md) | The RemoveTailList routine removes an entry from the end of a doubly linked list of LIST_ENTRY structures. |
| [RtlAppendUnicodeStringToString function](nf-wudfwdm-rtlappendunicodestringtostring.md) | The RtlAppendUnicodeStringToString routine concatenates two Unicode strings. |
| [RtlAppendUnicodeToString function](nf-wudfwdm-rtlappendunicodetostring.md) | The RtlAppendUnicodeToString routine concatenates the supplied Unicode string to a buffered Unicode string. |
| [RtlCompareUnicodeString function](nf-wudfwdm-rtlcompareunicodestring.md) | The RtlCompareUnicodeString routine compares two Unicode strings. |
| [RtlCopyUnicodeString function](nf-wudfwdm-rtlcopyunicodestring.md) | The RtlCopyUnicodeString routine copies a source string to a destination string. |
| [RtlEqualUnicodeString function](nf-wudfwdm-rtlequalunicodestring.md) | The RtlEqualUnicodeString routine compares two Unicode strings to determine whether they are equal. |
| [RtlFreeUnicodeString function](nf-wudfwdm-rtlfreeunicodestring.md) | The RtlFreeUnicodeString routine releases storage that was allocated by RtlAnsiStringToUnicodeString or RtlUpcaseUnicodeString. |
| [RtlInitUnicodeString function](nf-wudfwdm-rtlinitunicodestring.md) | For more information, see the WdmlibRtlInitUnicodeStringEx function. |
| [RtlInt64ToUnicodeString function](nf-wudfwdm-rtlint64tounicodestring.md) | The RtlInt64ToUnicodeString routine converts a specified unsigned 64-bit integer value to a Unicode string that represents the value in a specified base. |
| [RtlIntegerToUnicodeString function](nf-wudfwdm-rtlintegertounicodestring.md) | The RtlIntegerToUnicodeString routine converts an unsigned integer value to a null-terminated string of one or more Unicode characters in the specified base. |
| [RtlUnicodeStringToInteger function](nf-wudfwdm-rtlunicodestringtointeger.md) | The RtlUnicodeStringToInteger routine converts a Unicode string representation of a number to the equivalent integer value. |
| [WRITE_REGISTER_BUFFER_UCHAR function](nf-wudfwdm-write_register_buffer_uchar.md) | The WRITE_REGISTER_BUFFER_UCHAR routine writes a number of bytes from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_ULONG function](nf-wudfwdm-write_register_buffer_ulong.md) | The WRITE_REGISTER_BUFFER_ULONG routine writes a number of ULONG values from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_ULONG64 function](nf-wudfwdm-write_register_buffer_ulong64.md) | The WRITE_REGISTER_BUFFER_ULONG64 function writes a number of ULONG64 values from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_USHORT function](nf-wudfwdm-write_register_buffer_ushort.md) | The WRITE_REGISTER_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified register. |
| [WRITE_REGISTER_UCHAR function](nf-wudfwdm-write_register_uchar.md) | The WRITE_REGISTER_UCHAR routine writes a byte to the specified address. |
| [WRITE_REGISTER_ULONG function](nf-wudfwdm-write_register_ulong.md) | The WRITE_REGISTER_ULONG routine writes a ULONG value to the specified address. |
| [WRITE_REGISTER_ULONG64 function](nf-wudfwdm-write_register_ulong64.md) | The WRITE_REGISTER_ULONG64 function writes a ULONG64 value to the specified address. |
| [WRITE_REGISTER_USHORT function](nf-wudfwdm-write_register_ushort.md) | The WRITE_REGISTER_USHORT routine writes a USHORT value to the specified address. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [DRIVER_INITIALIZE callback](nc-wudfwdm-driver_initialize.md) | DriverEntry is the first routine called after a driver is loaded, and is responsible for initializing the driver. |
| [PINTERFACE_DEREFERENCE callback](nc-wudfwdm-pinterface_dereference.md) | The InterfaceDereference routine decrements the reference count on a driver-defined interface. |
| [PINTERFACE_REFERENCE callback](nc-wudfwdm-pinterface_reference.md) | The InterfaceReference routine increments the reference count on a driver-defined interface. |
| [PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK callback](nc-wudfwdm-po_fx_component_active_condition_callback.md) | The ComponentActiveConditionCallback callback routine notifies the driver that the specified component completed a transition from the idle condition to the active condition. |
| [PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK callback](nc-wudfwdm-po_fx_component_critical_transition_callback.md) | The ComponentCriticalTransitionCallback callback routine handles a transition of the specified component between the F0 (fully on) and low-power Fx component power states. |
| [PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK callback](nc-wudfwdm-po_fx_component_idle_condition_callback.md) | The ComponentIdleConditionCallback callback routine notifies the driver that the specified component completed a transition from the active condition to the idle condition. |
| [PO_FX_COMPONENT_IDLE_STATE_CALLBACK callback](nc-wudfwdm-po_fx_component_idle_state_callback.md) | The ComponentIdleStateCallback callback routine notifies the driver of a pending change to the Fx power state of the specified component. |
| [PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK callback](nc-wudfwdm-po_fx_device_power_not_required_callback.md) | The DevicePowerNotRequiredCallback callback routine notifies the device driver that the device is not required to stay in the D0 power state. |
| [PO_FX_DEVICE_POWER_REQUIRED_CALLBACK callback](nc-wudfwdm-po_fx_device_power_required_callback.md) | The DevicePowerRequiredCallback callback routine notifies the device driver that the device must enter and remain in the D0 power state. |
| [PO_FX_POWER_CONTROL_CALLBACK callback](nc-wudfwdm-po_fx_power_control_callback.md) | The PowerControlCallback callback routine performs a power control operation that is requested by the power management framework (PoFx). |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_CM_FULL_RESOURCE_DESCRIPTOR structure](ns-wudfwdm-_cm_full_resource_descriptor.md) | The CM_FULL_RESOURCE_DESCRIPTOR structure specifies a set of system hardware resources of various types, assigned to a device that is connected to a specific bus. This structure is contained within a CM_RESOURCE_LIST structure. |
| [_CM_PARTIAL_RESOURCE_DESCRIPTOR structure](ns-wudfwdm-_cm_partial_resource_descriptor.md) | The CM_PARTIAL_RESOURCE_DESCRIPTOR structure specifies one or more system hardware resources, of a single type, assigned to a device. |
| [_CM_PARTIAL_RESOURCE_LIST structure](ns-wudfwdm-_cm_partial_resource_list.md) | The CM_PARTIAL_RESOURCE_LIST structure specifies a set of system hardware resources, of various types, assigned to a device. This structure is contained within a CM_FULL_RESOURCE_DESCRIPTOR structure. |
| [_CM_RESOURCE_LIST structure](ns-wudfwdm-_cm_resource_list.md) | The CM_RESOURCE_LIST structure specifies all of the system hardware resources assigned to a device. |
| [_IO_STATUS_BLOCK structure](ns-wudfwdm-_io_status_block.md) | A driver sets an IRP's I/O status block to indicate the final status of an I/O request, before calling IoCompleteRequest for the IRP. |
| [_OBJECT_ATTRIBUTES structure](ns-wudfwdm-_object_attributes.md) | The OBJECT_ATTRIBUTES structure specifies attributes that can be applied to objects or object handles by routines that create objects and/or return handles to objects. |
| [_PO_FX_COMPONENT_IDLE_STATE structure](ns-wudfwdm-_po_fx_component_idle_state.md) | The PO_FX_COMPONENT_IDLE_STATE structure specifies the attributes of an Fx power state of a component in a device. |
| [_PO_FX_COMPONENT_PERF_INFO structure](ns-wudfwdm-_po_fx_component_perf_info.md) | The PO_FX_COMPONENT_PERF_INFO structure describes all the sets of performance states for a single component within a device. |
| [_PO_FX_COMPONENT_PERF_SET structure](ns-wudfwdm-_po_fx_component_perf_set.md) | The PO_FX_COMPONENT_PERF_SET structure represents a set of performance states for a single component within a device. |
| [_PO_FX_COMPONENT_V1 structure](ns-wudfwdm-_po_fx_component_v1.md) | The PO_FX_COMPONENT structure describes the power state attributes of a component in a device. |
| [_PO_FX_COMPONENT_V2 structure](ns-wudfwdm-_po_fx_component_v2.md) | The PO_FX_COMPONENT structure describes the power state attributes of a component in a device. |
| [_PO_FX_DEVICE_V1 structure](ns-wudfwdm-_po_fx_device_v1.md) | The PO_FX_DEVICE structure describes the power attributes of a device to the power management framework (PoFx). |
| [_PO_FX_DEVICE_V2 structure](ns-wudfwdm-_po_fx_device_v2.md) | The PO_FX_DEVICE structure describes the power attributes of a device to the power management framework (PoFx). |
| [_PO_FX_PERF_STATE structure](ns-wudfwdm-_po_fx_perf_state.md) | The PO_FX_PERF_STATE structure represents a performance state for a single component within a device. |
| [_PO_FX_PERF_STATE_CHANGE structure](ns-wudfwdm-_po_fx_perf_state_change.md) | The PO_FX_PERF_STATE_CHANGE structure contains information about a change to a performance state that is being requested by calling the PoFxIssueComponentPerfStateChange or PoFxIssueComponentPerfStateChangeMultiple routine. |
| [_UNICODE_STRING structure](ns-wudfwdm-_unicode_string.md) | The UNICODE_STRING structure is used to define Unicode strings. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [DEVICE_REGISTRY_PROPERTY enumeration](ne-wudfwdm-device_registry_property.md) | The DEVICE_REGISTRY_PROPERTY enumeration identifies device properties that are stored in the registry. |
| [_INTERFACE_TYPE enumeration](ne-wudfwdm-_interface_type.md) | The INTERFACE_TYPE enumeration indicates the bus type. |
| [_KINTERRUPT_MODE enumeration](ne-wudfwdm-_kinterrupt_mode.md) | The KINTERRUPT_MODE enumeration type indicates whether an interrupt is level-triggered or edge-triggered. |
| [_MEMORY_CACHING_TYPE enumeration](ne-wudfwdm-_memory_caching_type.md) | The MEMORY_CACHING_TYPE enumeration type specifies the permitted caching behavior when allocating or mapping memory. |
| [_POOL_TYPE enumeration](ne-wudfwdm-_pool_type.md) | The POOL_TYPE enumeration type specifies the type of system memory to allocate. |
| [_PO_FX_PERF_STATE_TYPE enumeration](ne-wudfwdm-_po_fx_perf_state_type.md) | The PO_FX_PERF_STATE_TYPE enumeration contains values that describe the type of performance states in a PO_FX_COMPONENT_PERF_SET. |
| [_PO_FX_PERF_STATE_UNIT enumeration](ne-wudfwdm-_po_fx_perf_state_unit.md) | The PO_FX_PERF_STATE_UNIT enumeration contains values that describe the type of unit that is controlled by the performance states in a PO_FX_COMPONENT_PERF_SET. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [ARGUMENT_PRESENT macro](nf-wudfwdm-argument_present.md) | The ARGUMENT_PRESENT macro takes an argument pointer and returns FALSE if the pointer is NULL. Otherwise, it returns TRUE. |
| [InitializeObjectAttributes macro](nf-wudfwdm-initializeobjectattributes.md) | The InitializeObjectAttributes macro initializes the opaque OBJECT_ATTRIBUTES structure, which specifies the properties of an object handle to routines that open handles. |
| [RtlIntPtrToUnicodeString macro](nf-wudfwdm-rtlintptrtounicodestring.md) | The RtlIntPtrToUnicodeString routine converts a specified ULONG_PTR value to a Unicode string that represents the value in a specified base. |
