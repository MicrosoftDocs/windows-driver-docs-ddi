---
UID: NS:d3dkmthk._D3DKMT_QUERYRESOURCEINFO
title: "_D3DKMT_QUERYRESOURCEINFO" (d3dkmthk.h)
description: The D3DKMT_QUERYRESOURCEINFO structure describes parameters for retrieving information about a resource.
old-location: display\d3dkmt_queryresourceinfo.htm
ms.assetid: 14078b2b-8951-48df-912a-e053bc997dde
ms.date: 05/10/2018
ms.keywords: D3DKMT_QUERYRESOURCEINFO, D3DKMT_QUERYRESOURCEINFO structure [Display Devices], OpenGL_Structs_1bab95d7-d3a4-4380-939f-bca4e2d98478.xml, _D3DKMT_QUERYRESOURCEINFO, d3dkmthk/D3DKMT_QUERYRESOURCEINFO, display.d3dkmt_queryresourceinfo
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_QUERYRESOURCEINFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_QUERYRESOURCEINFO
---

# _D3DKMT_QUERYRESOURCEINFO structure


## -description


The D3DKMT_QUERYRESOURCEINFO structure describes parameters for retrieving information about a resource.


## -struct-fields




### -field hDevice

[in] A handle to the device that the resource and allocations are associated with.


### -field hGlobalShare

[in] A handle to the shared resource to open.


### -field pPrivateRuntimeData

[in] If non-<b>NULL</b>, a pointer to a buffer that receives the runtime-private data that is supplied at create time. The OpenGL ICD should first call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547124">D3DKMTQueryResourceInfo</a> function with <b>pPrivateRuntimeData</b> set to <b>NULL</b> to obtain the buffer size and then call again with the correct size buffer. 


### -field PrivateRuntimeDataSize

[in/out] The size, in bytes, of the buffer that <b>pPrivateRuntimeData</b> points to. If <b>pPrivateRuntimeData</b> is <b>NULL</b>, <b>PrivateRuntimeDataSize</b> is set to the size, in bytes, that is required for the buffer to store the runtime-private data.


### -field TotalPrivateDriverDataSize

[out] The size, in bytes, of the buffer that is required to hold the private driver data for all of the allocations that are associated with the resource.


### -field ResourcePrivateDriverDataSize

[out] The size, in bytes, of the buffer that is required to hold the private driver data for the resource.


### -field NumAllocations

[out] The number of allocations that are associated with the resource.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547065">D3DKMTOpenResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547124">D3DKMTQueryResourceInfo</a>
 

 

