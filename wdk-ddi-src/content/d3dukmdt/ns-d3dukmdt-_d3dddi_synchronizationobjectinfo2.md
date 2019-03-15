---
UID: NS:d3dukmdt._D3DDDI_SYNCHRONIZATIONOBJECTINFO2
title: _D3DDDI_SYNCHRONIZATIONOBJECTINFO2 (d3dukmdt.h)
description: The D3DDDI_SYNCHRONIZATIONOBJECTINFO2 structure contains information about a second-generation synchronization object.
old-location: display\d3dddi_synchronizationobjectinfo2.htm
tech.root: display
ms.assetid: dc1c6a67-320c-41f8-91ad-cdbcde191a81
ms.date: 05/10/2018
ms.keywords: D3DDDI_SYNCHRONIZATIONOBJECTINFO2, D3DDDI_SYNCHRONIZATIONOBJECTINFO2 structure [Display Devices], D3D_other_Structs_0efa3a96-3e04-4232-bf7a-53c3f038d6ec.xml, _D3DDDI_SYNCHRONIZATIONOBJECTINFO2, d3dukmdt/D3DDDI_SYNCHRONIZATIONOBJECTINFO2, display.d3dddi_synchronizationobjectinfo2
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDI_SYNCHRONIZATIONOBJECTINFO2 is supported beginning with the Windows 7 operating system.
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
- d3dukmdt.h
api_name:
- D3DDDI_SYNCHRONIZATIONOBJECTINFO2
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_SYNCHRONIZATIONOBJECTINFO2
---

# _D3DDDI_SYNCHRONIZATIONOBJECTINFO2 structure


## -description


The <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> structure contains information about a second-generation synchronization object.


## -struct-fields




### -field Type

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff544669">D3DDDI_SYNCHRONIZATIONOBJECT_TYPE</a> that indicates the type of synchronization object.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544662">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a> structure that specifies, in bit-field flags, attributes of the synchronization object. 


### -field SynchronizationMutex

A structure that contains information about a synchronization mutex. If the <b>Type</b> member is equal to <b>D3DDDI_SYNCHRONIZATION_MUTEX</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>SynchronizationMutex</b> structure, which contains the following member:


### -field SynchronizationMutex.InitialState

A Boolean value that indicates whether the synchronization mutex is initially owned by an object. A value of <b>TRUE</b> indicates that the mutex is owned; <b>FALSE</b> indicates that the mutex is not owned. 


### -field Semaphore

A structure that contains information about a semaphore. If the <b>Type</b> member is equal to <b>D3DDDI_SEMAPHORE</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>Semaphore</b> structure, which contains the following members:


### -field Semaphore.MaxCount

The maximum number of events that an object can be waiting for. 


### -field Semaphore.InitialCount

The initial number of events that an object is waiting for. 


### -field Fence

A structure that contains information about a fence. If the <b>Type</b> member is equal to <b>D3DDDI_FENCE</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>Fence</b> structure, which contains the following member:


### -field Fence.FenceValue

A 64-bit value that specifies the initial fence value. 


### -field CPUNotification

A structure that contains information about a CPU notification. If the <b>Type</b> member is equal to <b>D3DDDI_CPU_NOTIFICATION</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>CPUNotification</b> structure, which contains the following member:


### -field CPUNotification.Event

The handle to the CPU notification event. 


### -field MonitoredFence

A structure that contains information about a monitored fence. If the <b>Type</b> member is equal to <b>D3DDDI_MONITORED_FENCE</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>MonitoredFence</b> structure.

Supported starting with Windows 10.


### -field MonitoredFence.InitialFenceValue

[in] A 64-bit value that specifies the initial fence value. 

Supported starting with Windows 10.


### -field MonitoredFence.FenceValueCPUVirtualAddress

[out] A read-only mapping of the fence value for the CPU. This is a user mode address readable from the process that created the monitored fence object. For 32 bit platforms that support 64 bit atomic reads via methods such as <code>InterlockedCompareExchange64(pointer,0,0)</code>, the mapping will be made read-write instead of read-only to avoid an access violation during the interlocked operation. Depending on the value of <b>No64BitAtomics</b> cap, this address points to either a 32 bit or a 64 bit underlying value.

Supported starting with Windows 10.


### -field MonitoredFence.FenceValueGPUVirtualAddress

[out] A read-write mapping of the fence value for the GPU. A driver can signal a new fence value by inserting a GPU write command for this address into a command buffer, and the DirectX graphics kernel will unblock waiters for this fence object value. Depending on the value of <b>No64BitAtomics</b> cap, this address points to either a 32 bit or a 64 bit underlying value.

Supported starting with Windows 10.


### -field MonitoredFence.EngineAffinity

[in] A bit field, where each bit position (starting from zero) defines a physical adapter index in an link display adapter (LDA) link where the GPU virtual address will be committed. Zero means that the GPU virtual address will be committed to all physical adapters.

Supported starting with Windows 10.


### -field PeriodicMonitoredFence

A structure that contains information about a periodic monitored fence. If the <b>Type</b> member is equal to <b>D3DDDI_PERIODIC_MONITORED_FENCE</b>, the union in <b>D3DDDI_SYNCHRONIZATIONOBJECTINFO2</b> holds a <b>MonitoredFence</b> structure.

Supported starting with Windows 10.



#### VidPnTargetID

[out] The output ID that the compositor wishes to receive notifications for.


### -field PeriodicMonitoredFence.hAdapter

[in] A handle to the adapter associated with VidPnSourceID


### -field PeriodicMonitoredFence.VidPnTargetId

 


### -field PeriodicMonitoredFence.Time

[out] Represents an offset before the VSync (time of VSync – Time parameter). The Time value may not be longer than a VSync interval (1 / DisplayModeRefresh). Time is specified in units of 100ns.


### -field PeriodicMonitoredFence.FenceValueCPUVirtualAddress

[in] Read-only mapping of the fence value for the CPU


### -field PeriodicMonitoredFence.FenceValueGPUVirtualAddress

[in] Read-only mapping of the fence value for the GPU


### -field PeriodicMonitoredFence.EngineAffinity

[in] Defines physical adapters where the GPU VA will be mapped


### -field Reserved

A structure that is reserved for future use. This structure contains the following member:


### -field Reserved.Reserved

An array of 64-bit values that are reserved for future use.


### -field SharedHandle

[out] A handle to the shared synchronization object if a shared handle currently exists. The shared handle is returned from the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546879">D3DKMTCreateSynchronizationObject2</a> function. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544662">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544669">D3DDDI_SYNCHRONIZATIONOBJECT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546879">D3DKMTCreateSynchronizationObject2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547854">D3DKMT_CREATESYNCHRONIZATIONOBJECT2</a>
 

 

