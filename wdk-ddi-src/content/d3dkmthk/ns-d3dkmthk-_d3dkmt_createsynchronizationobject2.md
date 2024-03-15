---
UID: NS:d3dkmthk._D3DKMT_CREATESYNCHRONIZATIONOBJECT2
title: D3DKMT_CREATESYNCHRONIZATIONOBJECT2 (d3dkmthk.h)
description: Learn more about the D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure.
ms.date: 05/10/2018
keywords: ["D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure"]
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
tech.root: display
req.typenames: D3DKMT_CREATESYNCHRONIZATIONOBJECT2
f1_keywords:
 - _D3DKMT_CREATESYNCHRONIZATIONOBJECT2
 - d3dkmthk/_D3DKMT_CREATESYNCHRONIZATIONOBJECT2
 - D3DKMT_CREATESYNCHRONIZATIONOBJECT2
 - d3dkmthk/D3DKMT_CREATESYNCHRONIZATIONOBJECT2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CREATESYNCHRONIZATIONOBJECT2
 - D3DKMT_CREATESYNCHRONIZATIONOBJECT2
---

# D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure

## -description

The **D3DKMT_CREATESYNCHRONIZATIONOBJECT2** structure describes a synchronization object that [**D3DKMTCreateSynchronizationObject2**](nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md) creates.

## -struct-fields

### -field hDevice [in]

A handle to the device that the synchronization object is associated with.

### -field Info [in]

A [**D3DDDI_SYNCHRONIZATIONOBJECTINFO2**](../d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md) structure with additional information about the kernel-mode synchronization object.

### -field hSyncObject [out]

A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode synchronization object.

## -see-also

[**D3DDDI_SYNCHRONIZATIONOBJECTINFO2**](../d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md)

[**D3DKMTCreateSynchronizationObject2**](nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md)
