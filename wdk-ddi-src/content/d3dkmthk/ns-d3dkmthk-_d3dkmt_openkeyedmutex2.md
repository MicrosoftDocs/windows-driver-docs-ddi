---
UID: NS:d3dkmthk._D3DKMT_OPENKEYEDMUTEX2
title: _D3DKMT_OPENKEYEDMUTEX2 (d3dkmthk.h)
description: Describes a keyed mutex that the D3DKMTOpenKeyedMutex2 function opens.
old-location: display\d3dkmt_openkeyedmutex2.htm
ms.assetid: 7d746cac-42fd-4fb3-9384-ea690c2235f8
ms.date: 05/10/2018
ms.keywords: D3DKMT_OPENKEYEDMUTEX2, D3DKMT_OPENKEYEDMUTEX2 structure [Display Devices], _D3DKMT_OPENKEYEDMUTEX2, d3dkmthk/D3DKMT_OPENKEYEDMUTEX2, display.d3dkmt_openkeyedmutex2
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_OPENKEYEDMUTEX2"
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
- D3DKMT_OPENKEYEDMUTEX2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_OPENKEYEDMUTEX2
---

# _D3DKMT_OPENKEYEDMUTEX2 structure


## -description


Describes a keyed mutex that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex2">D3DKMTOpenKeyedMutex2</a> function opens.


## -struct-fields




### -field hSharedHandle

[in] A D3DKMT_HANDLE data type that represents a global handle to a keyed mutex.


### -field hKeyedMutex

[out] A D3DKMT_HANDLE data type that represents a handle to the keyed mutex in this process.


### -field pPrivateRuntimeData

[in] A buffer that contains initial private data. This buffer is copied only if the keyed mutex does not already have private data.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the <b>pPrivateRuntimeData</b> member.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex2">D3DKMTOpenKeyedMutex2</a>
 

 

