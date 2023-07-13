---
UID: NS:d3dukmdt._D3DDDI_SYNCHRONIZATIONOBJECTINFO2
title: D3DDDI_SYNCHRONIZATIONOBJECTINFO2 (d3dukmdt.h)
description: Learn more about the D3DDDI_SYNCHRONIZATIONOBJECTINFO2 structure.
tech.root: display
ms.date: 07/12/2023
keywords: ["D3DDDI_SYNCHRONIZATIONOBJECTINFO2 structure"]
ms.keywords: D3DDDI_SYNCHRONIZATIONOBJECTINFO2, D3DDDI_SYNCHRONIZATIONOBJECTINFO2 structure [Display Devices], D3D_other_Structs_0efa3a96-3e04-4232-bf7a-53c3f038d6ec.xml, _D3DDDI_SYNCHRONIZATIONOBJECTINFO2, d3dukmdt/D3DDDI_SYNCHRONIZATIONOBJECTINFO2, display.d3dddi_synchronizationobjectinfo2
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
req.typenames: D3DDDI_SYNCHRONIZATIONOBJECTINFO2
f1_keywords:
 - _D3DDDI_SYNCHRONIZATIONOBJECTINFO2
 - d3dukmdt/_D3DDDI_SYNCHRONIZATIONOBJECTINFO2
 - D3DDDI_SYNCHRONIZATIONOBJECTINFO2
 - d3dukmdt/D3DDDI_SYNCHRONIZATIONOBJECTINFO2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_SYNCHRONIZATIONOBJECTINFO2
 - D3DDDI_SYNCHRONIZATIONOBJECTINFO2
---

# D3DDDI_SYNCHRONIZATIONOBJECTINFO2 structure

## -description

The **D3DDDI_SYNCHRONIZATIONOBJECTINFO2** structure contains information about a second-generation synchronization object.

## -struct-fields

### -field Type [in]

A value of type [**D3DDDI_SYNCHRONIZATIONOBJECT_TYPE**](ne-d3dukmdt-_d3dddi_synchronizationobject_type.md) that indicates the type of synchronization object.

### -field Flags [in]

A [**D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS**](ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md) structure that specifies, in bit-field flags, attributes of the synchronization object.

### -field SynchronizationMutex

A structure that contains information about a synchronization mutex. If the **Type** member is equal to **D3DDDI_SYNCHRONIZATION_MUTEX**, the union in **D3DDDI_SYNCHRONIZATIONOBJECTINFO2** holds a **SynchronizationMutex** structure.

### -field SynchronizationMutex.InitialState

A Boolean value that indicates whether the synchronization mutex is initially owned by an object. A value of TRUE indicates that the mutex is owned; FALSE indicates that the mutex is not owned.

### -field Semaphore

A structure that contains information about a semaphore. If the **Type** member is equal to **D3DDDI_SEMAPHORE**, the union in **D3DDDI_SYNCHRONIZATIONOBJECTINFO2** holds a **Semaphore** structure.

### -field Semaphore.MaxCount

The maximum number of events that an object can be waiting for.

### -field Semaphore.InitialCount

The initial number of events that an object is waiting for.

### -field Fence

A structure that contains information about a fence. If the **Type** member is equal to **D3DDDI_FENCE**, the union in **D3DDDI_SYNCHRONIZATIONOBJECTINFO2** holds a **Fence** structure.

### -field Fence.FenceValue

A 64-bit value that specifies the initial fence value.

### -field CPUNotification

A structure that contains information about a CPU notification. If the **Type** member is equal to **D3DDDI_CPU_NOTIFICATION**, the union in **D3DDDI_SYNCHRONIZATIONOBJECTINFO2** holds a **CPUNotification** structure.

### -field CPUNotification.Event

The handle to the CPU notification event.

### -field MonitoredFence

A structure that contains information about a monitored fence. If the **Type** member is equal to **D3DDDI_MONITORED_FENCE**, the union in **D3DDDI_SYNCHRONIZATIONOBJECTINFO2** holds a **MonitoredFence** structure.

Supported starting with Windows 10.

### -field MonitoredFence.InitialFenceValue [in]

A 64-bit value that specifies the initial fence value.

Supported starting with Windows 10.

### -field MonitoredFence.FenceValueCPUVirtualAddress [out]

A read-only mapping of the fence value for the CPU. This is a user mode address readable from the process that created the monitored fence object. For 32 bit platforms that support 64 bit atomic reads via methods such as ```InterlockedCompareExchange64(pointer,0,0)```, the mapping will be made read-write instead of read-only to avoid an access violation during the interlocked operation. Depending on the value of **No64BitAtomics** cap, this address points to either a 32 bit or a 64 bit underlying value.

Supported starting with Windows 10.

### -field MonitoredFence.FenceValueGPUVirtualAddress [out]

A read-write mapping of the fence value for the GPU. A driver can signal a new fence value by inserting a GPU write command for this address into a command buffer, and the DirectX graphics kernel will unblock waiters for this fence object value. Depending on the value of **No64BitAtomics** cap, this address points to either a 32 bit or a 64 bit underlying value.

Supported starting with Windows 10.

### -field MonitoredFence.EngineAffinity [in]

A bit field, where each bit position (starting from zero) defines a physical adapter index in an link display adapter (LDA) link where the GPU virtual address will be committed. Zero means that the GPU virtual address will be committed to all physical adapters.

Supported starting with Windows 10.

### -field PeriodicMonitoredFence

A structure that contains information about a periodic monitored fence. If the **Type** member is equal to **D3DDDI_PERIODIC_MONITORED_FENCE**, the union in **D3DDDI_SYNCHRONIZATIONOBJECTINFO2** holds a **MonitoredFence** structure.

Supported starting with Windows 10.

#### VidPnTargetID

[out] The output ID that the compositor wishes to receive notifications for.

### -field PeriodicMonitoredFence.hAdapter [in]

A handle to the adapter associated with VidPnSourceID

### -field PeriodicMonitoredFence.VidPnTargetId

### -field PeriodicMonitoredFence.Time [out]

Represents an offset before the VSync (time of VSync – Time parameter). The Time value may not be longer than a VSync interval (1 / DisplayModeRefresh). Time is specified in units of 100ns.

### -field PeriodicMonitoredFence.FenceValueCPUVirtualAddress [in]

Read-only mapping of the fence value for the CPU

### -field PeriodicMonitoredFence.FenceValueGPUVirtualAddress [in]

Read-only mapping of the fence value for the GPU

### -field PeriodicMonitoredFence.EngineAffinity [in]

Defines physical adapters where the GPU VA will be mapped

### -field Reserved

A structure that is reserved for future use. This structure contains the following member:

### -field Reserved.Reserved

An array of 64-bit values that are reserved for future use.

### -field SharedHandle [out]

A handle to the shared synchronization object if a shared handle currently exists. The driver should share synchronization objects using NT handles. It should set the [**D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS::NtSecuritySharing**](ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md) to indicate that the object will be shared using NT handles and call [**D3DKMTShareObjects**](../d3dkmthk/nf-d3dkmthk-d3dkmtshareobjects.md) to get an NT handle. Using global handles is not secure. Any process can guess a global handle and open a shared objects. Global handles are supported only for compatibility reasons with old D3D runtimes.

## -see-also

[**D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS**](ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md)

[**D3DDDI_SYNCHRONIZATIONOBJECT_TYPE**](ne-d3dukmdt-_d3dddi_synchronizationobject_type.md)

[**D3DKMTCreateSynchronizationObject**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatesynchronizationobject.md)

[**D3DKMT_CREATESYNCHRONIZATIONOBJECT2**](../d3dkmthk/ns-d3dkmthk-_d3dkmt_createsynchronizationobject2.md)
