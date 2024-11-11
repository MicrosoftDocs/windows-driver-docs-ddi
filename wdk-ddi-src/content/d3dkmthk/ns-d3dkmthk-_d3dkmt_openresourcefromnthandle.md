---
UID: NS:d3dkmthk._D3DKMT_OPENRESOURCEFROMNTHANDLE
title: D3DKMT_OPENRESOURCEFROMNTHANDLE (d3dkmthk.h)
description: Learn more about the D3DKMT_OPENRESOURCEFROMNTHANDLE structure.
ms.date: 11/08/2024
keywords: ["D3DKMT_OPENRESOURCEFROMNTHANDLE structure"]
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3DKMT_OPENRESOURCEFROMNTHANDLE
f1_keywords:
 - _D3DKMT_OPENRESOURCEFROMNTHANDLE
 - d3dkmthk/_D3DKMT_OPENRESOURCEFROMNTHANDLE
 - D3DKMT_OPENRESOURCEFROMNTHANDLE
 - d3dkmthk/D3DKMT_OPENRESOURCEFROMNTHANDLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_OPENRESOURCEFROMNTHANDLE
 - D3DKMT_OPENRESOURCEFROMNTHANDLE
---

# D3DKMT_OPENRESOURCEFROMNTHANDLE structure

## -description

The **D3DKMT_OPENRESOURCEFROMNTHANDLE** structure contains information required to open a shared resource from an NT handle to the process. The shared resource can be a set of allocations, a keyed mutex, or a synchronization object.

## -struct-fields

### -field hDevice [in]

A D3DKMT_HANDLE data type that represents the device.

### -field hNtHandle [in]

An NT handle to the process.

### -field NumAllocations [in]

The number of allocations associated with the resource.

### -field pOpenAllocationInfo2 [in]

This member is reserved and should be set to zero.

### -field PrivateRuntimeDataSize [in]

The size, in bytes, of the buffer pointed to by the **pPrivateRuntimeData** member.

### -field pPrivateRuntimeData [in]

A caller-supplied buffer where the runtime private data associated with this resource will be copied to.

### -field ResourcePrivateDriverDataSize [in]

The size, in bytes, of the  buffer pointed to by the **pResourcePrivateDriverData** member.

### -field pResourcePrivateDriverData [in]

A caller-supplied buffer where the driver private data associated with the resource will be copied to.

### -field TotalPrivateDriverDataBufferSize [in]

The size, in bytes, of the buffer pointed to by the **pTotalPrivateDriverDataBuffer** member.

[out] The size, in bytes, of  the data written to **pTotalPrivateDriverDataBuffer**.

### -field pTotalPrivateDriverDataBuffer [in]

A pointer to a caller-supplied buffer where the driver private data will be stored.

### -field hResource [out]

A handle to the resource in this process.

### -field hKeyedMutex [out]

A handle to the keyed mutex in this process.

### -field pKeyedMutexPrivateRuntimeDat [in]

A buffer that contains initial private data.

The data in this buffer will be copied only if the keyed mutex does not already have private data.

If this member has a value of NULL, the value of the **KeyedMutexPrivateRuntimeDataSize** member must be zero.

### -field KeyedMutexPrivateRuntimeDataSize [in]

The size, in bytes, of the buffer pointed to by the **pKeyedMutexPrivateRuntimeData** member.

### -field hSyncObject [out]

A handle to the synchronization object in this process.

## -see-also

[**D3DDDI_OPENALLOCATIONINFO2**](../d3dukmdt/ns-d3dukmdt-_d3dddi_openallocationinfo2.md)

[**D3DKMTOpenNtHandleFromName**](nf-d3dkmthk-d3dkmtopennthandlefromname.md)

[**D3DKMTShareObjects**](nf-d3dkmthk-d3dkmtshareobjects.md)
