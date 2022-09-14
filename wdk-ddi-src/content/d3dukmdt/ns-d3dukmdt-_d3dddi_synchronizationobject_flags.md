---
UID: NS:d3dukmdt._D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
title: D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS (d3dukmdt.h)
description: Learn more about the D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS structure.
old-location: display\d3dddi_synchronizationobject_flags.htm
tech.root: display
ms.date: 09/12/2022
keywords: ["D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS structure"]
ms.keywords: D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS, D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS structure [Display Devices], D3D_other_Structs_3d266c5b-53c9-47d1-abe9-f492d05660a4.xml, _D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS, d3dukmdt/D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS, display.d3dddi_synchronizationobject_flags
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
req.typenames: D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
f1_keywords:
 - _D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
 - d3dukmdt/_D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
 - D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
 - d3dukmdt/D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
 - D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS
---

# D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS structure

## -description

The **D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS** structure identifies attributes of a synchronization object.

## -struct-fields

### -field Shared

A UINT value that specifies whether the synchronization object is shared.

If **Shared** is set to 1 (TRUE), the synchronization object is shared. If **Shared** is set to zero (FALSE), the synchronization object is not shared. For more information, see the Remarks section.

### -field NtSecuritySharing

A UINT value that specifies whether the synchronization object is shared with an NT handle, meaning that it does not have a global **D3DKMT_HANDLE** kernel-mode handle to the resource.

If **NtSecuritySharing** is set to 1 (TRUE), the synchronization object is shared but does not have a global **D3DKMT_HANDLE** handle to the resource.

> [!NOTE]
> If **NtSecuritySharing** is set to 1,  **Shared**  must be set to 1. For more information, see the Remarks section.

Supported starting with Windows 8.

### -field CrossAdapter

A UINT value that specifies whether the synchronization object is a shared [cross-adapter resource object on a hybrid system](/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system).

If **CrossAdapter** is set to 1 (TRUE), the synchronization object is a shared cross-adapter object. If **CrossAdapter** is set to zero (FALSE), the synchronization object is not a shared cross-adapter object.

### -field TopOfPipeline

|Value|Meaning|
|--- |--- |
|TRUE|Specifies whether the synchronization object is signaled as soon as the contents of command buffer preceding it is entirely copied to the GPU pipeline, but not necessarily completed execution. This behavior allows reusing command buffers as soon as possible.|
|FALSE|The synchronization object is signaled after the preceding command buffers completed execution.|

This value can only be set to 1 (TRUE) for monitored fence synchronization objects, and it should be set to zero (FALSE) for all other synchronization object types.

Supported starting with Windows 10.

### -field NoSignal

|Value|Meaning|
|--- |--- |
|TRUE|Specifies the device this sync object is created or opened on can only submit wait commands for it. An attempt to submit a signal operation when this flag is set will return STATUS_ACCESS_DENIED.|
|FALSE|The synchronization object can be signaled.|

This value can only be set to 1 (TRUE) for monitored fence synchronization objects, and it should be set to zero (FALSE) for all other synchronization object types.

Supported starting with Windows 10.

### -field NoWait

|Value|Meaning|
|--- |--- |
|TRUE|Specifies the device this sync object is created or opened on can only submit signal commands for it. An attempt to submit a wait operation when this flag is set will return STATUS_ACCESS_DENIED.|
|FALSE|The synchronization object can be waited on.|

This value can only be set to 1 (TRUE) for monitored fence synchronization objects, and it should be set to zero (FALSE) for all other synchronization object types.

This flag cannot be set simultaneously with **NoSignal** flag.

Supported starting with Windows 10.

### -field NoSignalMaxValueOnTdr

|Value|Meaning|
|--- |--- |
|TRUE|Instructs the GPU scheduler to bypass the aforementioned signaling of the monitored fence to the maximum value in TDR cases.|
|FALSE|The GPU scheduler will signal the monitored fence to the maximum value when a device that can potentially signal it is affected by the GPU reset (TDR).|

Supported starting with Windows 10.

### -field NoGPUAccess

When set, the fence will not be mapped into the GPU virtual address space and will always stored as a 64-bit value (regardless of adapter caps). Only packet-based signal/wait operations are supported.

### -field SignalByKmd

When set, the fence can be signled by the kernel-mode driver (KMD). This flag can only be used with [**D3DDDI_CPU_NOTIFICATION**](ne-d3dukmdt-_d3dddi_synchronizationobject_type.md) objects. Supported starting with Windows 11 (WDDM 3.0).

### -field LocalMemoryPreferred

When set, indicates that the fence should be placed in GPU local memory if possible. Supported starting with Windows 11 version 22H2 (WDDM 3.1).

### -field Reserved

This member is reserved and should be set to zero.

### -field D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS_RESERVED0

This member is reserved and should be set to zero.

Supported starting with Windows 8.

### -field Value

A member in the union that is contained in **D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS** that can hold one 32-bit value that identifies attributes of a synchronization object.

## -remarks

Objects to be shared by using the [**D3DKMTShareObjects**](../d3dkmthk/nf-d3dkmthk-d3dkmtshareobjects.md) function must first be created with the **NtSecuritySharing** flag value set. This flag value is available in the [**D3DKMT_CREATEALLOCATIONFLAGS**](../d3dkmthk/ns-d3dkmthk-_d3dkmt_createallocationflags.md), [**D3DKMT_CREATEKEYEDMUTEX2_FLAGS**](../d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md), and **D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS** structures.

Drivers should follow these guidelines on **D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS** flags:

* If the synchronization object is not shared, set both  **Shared** and **NtSecuritySharing** to 0.
* If the synchronization object is shared with a **D3DKMT_HANDLE** data type, set **Shared** = 1 and **NtSecuritySharing** = 0.
* If the synchronization object is shared with an NT handle to the process (and without a global **D3DKMT_HANDLE** kernel-mode handle to the resource), set **Shared** = 1 and **NtSecuritySharing** = 1.

## -see-also

[**D3DDDI_SYNCHRONIZATIONOBJECTINFO2**](ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md)

[**D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS**](ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md)

[**D3DKMTShareObjects**](../d3dkmthk/nf-d3dkmthk-d3dkmtshareobjects.md)

[**D3DKMT_CREATEALLOCATIONFLAGS**](../d3dkmthk/ns-d3dkmthk-_d3dkmt_createallocationflags.md)

[**D3DKMT_CREATEKEYEDMUTEX2_FLAGS**](../d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md)
