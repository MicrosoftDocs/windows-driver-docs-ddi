---
UID: NF:d3dkmthk.D3DKMTShareObjects
title: D3DKMTShareObjects function (d3dkmthk.h)
description: Learn more about the D3DKMTShareObjects function.
ms.date: 10/02/2024
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTShareObjects
 - d3dkmthk/D3DKMTShareObjects
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - GDI32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTShareObjects
---

# D3DKMTShareObjects function

## -description

**D3DKMTShareObjects** shares resource objects that were created with the [**D3KMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md),  [**D3KMTCreateAllocation2**](nf-d3dkmthk-d3dkmtcreateallocation2.md)[**D3DKMTCreateKeyedMutex2**](nf-d3dkmthk-d3dkmtcreatekeyedmutex2.md), and [**D3DKMTCreateSynchronizationObject2**](nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md) functions.

## -parameters

### -param cObjects [in]

The number of resource objects provided in the **hObjects** parameter. This value must be less than or equal to **D3DKMT_MAX_OBJECTS_PER_HANDLE**.

### -param hObjects [in]

A pointer to an array of local kernel-mode handles that specify the resource objects to be shared. For more information, see **Remarks**.

### -param pObjectAttributes [in]

A pointer to an [**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that specifies attributes of the resource objects.

### -param dwDesiredAccess [in]

Specifies read and write access for the resource.

For GPU synchronization objects, **dwDesiredAccess** can be a combination of the following bit fields (defined in *d3dukmdt.h*).

| Value | Meaning |
| ----- | ------- |
| STANDARD_RIGHTS_READ | The process that opens the sync object can read the state of the sync object. This flag must be specified or the object will be inaccessible. |
| D3DDDI_SYNC_OBJECT_WAIT       | The process that opens the sync object can issue wait operations for the sync object. |
| D3DDDI_SYNC_OBJECT_SIGNAL     | The process that opens the sync object can issue signal operations for the sync object. |
| D3DDDI_SYNC_OBJECT_ALL_ACCESS | The process that opens the sync object can issue any operation for the sync object. |

For shared resources, the desired access can be specified as a combination of the following flags (defined in *d3dkmthk.h*):

| Value | Meaning |
| ----- | ------- |
| STANDARD_RIGHTS_READ         | The process that opens the resource can have read access. This flag must be specified or the object will be inaccessible. |
| SHARED_ALLOCATION_WRITE      | The process that opens the resource can have write access. If this access flag is not specified, the resource will be opened as read-only. |
| SHARED_ALLOCATION_ALL_ACCESS | The process that opens the resource can have all access to the object. |

### -param phSharedNtHandle [out]

A pointer to a shared NT handle that specifies the resource objects.

This parameter will be **NULL** if the **NtSecuritySharing** flag value is not set. For more information, see **Remarks**.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

Objects to be shared using  **D3DKMTShareObjects**  must first be created with the **NtSecuritySharing** flag value set. This flag value is available in the [**D3DKMT_CREATEALLOCATIONFLAGS**](ns-d3dkmthk-_d3dkmt_createallocationflags.md), [**D3DKMT_CREATEKEYEDMUTEX2_FLAGS**](ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md), and [**D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md) structures.

This function must specify handles through the **hObjects** parameter only to the following combinations of input object array types:

- an allocation
- an allocation, a keyed mutex, and a synchronization object
- a synchronization object

The operating system will reject any other input handle combinations.

## -see-also

[**D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md)

[**D3DKMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md)

[**D3DKMTCreateAllocation2**](nf-d3dkmthk-d3dkmtcreateallocation2.md)

[**D3DKMTCreateKeyedMutex2**](nf-d3dkmthk-d3dkmtcreatekeyedmutex2.md)

[**D3DKMTCreateSynchronizationObject2**](nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md)

[**D3DKMT_CREATEALLOCATIONFLAGS**](ns-d3dkmthk-_d3dkmt_createallocationflags.md)

[**D3DKMT_CREATEKEYEDMUTEX2_FLAGS**](ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md)
