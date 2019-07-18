---
UID: NS:d3dkmthk._D3DKMT_RELEASEKEYEDMUTEX2
title: _D3DKMT_RELEASEKEYEDMUTEX2 (d3dkmthk.h)
description: Describes a keyed mutex object that the D3DKMTReleaseKeyedMutex2 function releases that includes private data.
old-location: display\d3dkmt_releasekeyedmutex2.htm
ms.assetid: e343b11c-7cd1-4aea-a87c-e33577456851
ms.date: 05/10/2018
ms.keywords: D3DKMT_RELEASEKEYEDMUTEX2, D3DKMT_RELEASEKEYEDMUTEX2 structure [Display Devices], _D3DKMT_RELEASEKEYEDMUTEX2, d3dkmthk/D3DKMT_RELEASEKEYEDMUTEX2, display.d3dkmt_releasekeyedmutex2
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_RELEASEKEYEDMUTEX2"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmthk.h
api_name:
- D3DKMT_RELEASEKEYEDMUTEX2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_RELEASEKEYEDMUTEX2
---

# _D3DKMT_RELEASEKEYEDMUTEX2 structure


## -description


Describes a keyed mutex object that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtreleasekeyedmutex2">D3DKMTReleaseKeyedMutex2</a> function releases that includes private data.


## -struct-fields




### -field hKeyedMutex

[in] A value of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode handle to the keyed mutex object to release.


### -field Key

[in] A 64-bit value that specifies the key value to release the mutex to.


### -field FenceValue

[in] A 64-bit value that specifies the current fence value of the GPU synchronization object.


### -field pPrivateRuntimeData

[in] A pointer to a caller-supplied buffer where the runtime private data associated with the resource is stored.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the buffer pointed to by the <b>pPrivateRuntimeData</b> member.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtreleasekeyedmutex2">D3DKMTReleaseKeyedMutex2</a>
 

 

