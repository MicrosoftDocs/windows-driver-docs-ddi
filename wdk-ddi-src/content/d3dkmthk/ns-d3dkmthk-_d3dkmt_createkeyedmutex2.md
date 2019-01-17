---
UID: NS:d3dkmthk._D3DKMT_CREATEKEYEDMUTEX2
title: "_D3DKMT_CREATEKEYEDMUTEX2"
description: Describes a keyed mutex that the D3DKMTCreateKeyedMutex2 function creates that includes private data.
old-location: display\d3dkmt_createkeyedmutex2.htm
ms.assetid: 6c4c07ff-5e37-4094-9dc3-57082dec8edf
ms.date: 05/10/2018
ms.keywords: D3DKMT_CREATEKEYEDMUTEX2, D3DKMT_CREATEKEYEDMUTEX2 structure [Display Devices], _D3DKMT_CREATEKEYEDMUTEX2, d3dkmthk/D3DKMT_CREATEKEYEDMUTEX2, display.d3dkmt_createkeyedmutex2
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_CREATEKEYEDMUTEX2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATEKEYEDMUTEX2
---

# _D3DKMT_CREATEKEYEDMUTEX2 structure


## -description


Describes a keyed mutex that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439345">D3DKMTCreateKeyedMutex2</a> function creates that includes private data.


## -struct-fields




### -field InitialValue

[in] A 64-bit value that specifies the initial value to create the keyed mutex for.


### -field hSharedHandle

[out] A value of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode shared global handle to the keyed mutex object.


### -field hKeyedMutex

[out] A value of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode handle to the keyed mutex object in the current process.


### -field pPrivateRuntimeData

[in] A pointer to a caller-supplied buffer where the runtime private data associated with the resource is stored.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the buffer pointed to by the <b>pPrivateRuntimeData</b> member.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/hh780254">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a> structure that indicates how to specify a handle to a keyed mutex object.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439345">D3DKMTCreateKeyedMutex2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780254">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>
 

 

