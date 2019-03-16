---
UID: NS:d3dukmdt._D3DDDI_ALLOCATIONINFO
title: _D3DDDI_ALLOCATIONINFO (d3dukmdt.h)
description: The D3DDDI_ALLOCATIONINFO structure describes an allocation.
old-location: display\d3dddi_allocationinfo.htm
tech.root: display
ms.assetid: 69181a7c-62bd-4df0-95fc-fe6c3ab14209
ms.date: 05/10/2018
ms.keywords: D3DDDI_ALLOCATIONINFO, D3DDDI_ALLOCATIONINFO structure [Display Devices], D3D_other_Structs_5125c057-c4b7-45fd-b7d9-9ebcfce4fff7.xml, _D3DDDI_ALLOCATIONINFO, d3dukmdt/D3DDDI_ALLOCATIONINFO, display.d3dddi_allocationinfo
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dukmdt.h
api_name:
- D3DDDI_ALLOCATIONINFO
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_ALLOCATIONINFO
---

# _D3DDDI_ALLOCATIONINFO structure


## -description


The D3DDDI_ALLOCATIONINFO structure describes an allocation.


## -struct-fields




### -field hAllocation

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation. This kernel-mode allocation handle is associated with the kernel-mode resource handle (if non-<b>NULL</b>) that the Microsoft Direct3D runtime's <a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a> function returns in the <b>hKMResource</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544137">D3DDDICB_ALLOCATE</a> structure. The user-mode display driver can use this kernel-mode allocation handle to reference the allocation in the command buffer.


### -field pSystemMem

[in] A pointer to system memory that the Direct3D runtime preallocated. Otherwise, this member is <b>NULL</b> if the allocation is to use video memory. 

If the allocation is in system memory, the user-mode display driver should assign the buffer in the <b>pSysMem</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544651">D3DDDI_SURFACEINFO</a> structure for the resource to <b>pSystemMem</b>. This buffer is specified when the Direct3D runtime calls the user-mode display driver's <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function to create resources. 


### -field pPrivateDriverData

[in/out] A pointer to buffer that contains optional private data that might be required by the display miniport driver to create the allocation. The display miniport driver can also return data in the buffer. When the contents of the buffer are passed to the display miniport driver, the contents must be in a format that the display miniport driver can process. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology if the allocation is for the primary surface. The driver should set <b>VidPnSourceId</b> only for primary allocation types and not for any other type of allocation. If the driver sets <b>VidPnSourceId</b> for any other allocation type in a call to the <a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a> function, <b>pfnAllocateCb</b> returns D3DDDI_ID_NOTAPPLICABLE.

When the DirectX graphics kernel subsystem initiates the creation of the allocation for the shared primary surface, the display miniport driver can determine the identification number from the <b>VidPnSourceId</b> member of the <a href="https://msdn.microsoft.com/edf59add-0155-4619-9c7c-fdb63b954f85">D3DKMDDI_SHAREDPRIMARYSURFACEDATA</a> structure that the <b>pPrivateDriverData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a> structure points to. 


### -field Flags

[in] A union that contains either a structure (with the first three members that are described in the following list) or a 32-bit value (in the <b>Value</b> member) that indentifies the type of allocation:


### -field Flags.Primary

[in] A UINT that specifies whether the allocation is part of the desktop. Such an allocation is implicitly accessible to the CPU. A primary allocation can be either pinned down at creation or not pinned down at creation. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Flags.Stereo

[in] Supported beginning with Windows 8.

A UINT that specifies whether the allocation is a stereo primary allocation. The <b>Stereo</b> member can be set only when the <b>Primary</b> member is set.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Flags.Reserved

[in] Supported beginning with Windows 8.

This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.


[in] This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.



### -field Flags.Value

[in] A 32-bit value that identifies the type of allocation. 


## -remarks



When the user-mode display driver sets the <b>Primary</b> bit-field flag in the <b>Flags</b> member of D3DDDI_ALLOCATIONINFO, certain restrictions apply to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a> structure in the <b>pAllocationInfo</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a> structure for the allocation in a call to the display miniport driver's <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function. These restrictions include the following: 

<ul>
<li>
The allocation is allocated according to preferences; otherwise, the allocation defaults to the supported write segment set, and all of the specified segments in the write segment set must be CPU-accessible.

</li>
<li>The display miniport driver cannot set the following bit-field flags in the  <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a>:<ul>
<li><b>PermanentSysMem</b></li>
<li><b>Cached</b></li>
<li><b>Protected</b></li>
<li><b>ExistingSysMem</b></li>
<li><b>ExistingKernelSysMem</b></li>
</ul>
</li>
</ul>
The D3DDDI_ID_NOTAPPLICABLE constant is defined in D3dukmdt.h.




## -see-also




<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544137">D3DDDICB_ALLOCATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544651">D3DDDI_SURFACEINFO</a>



<a href="https://msdn.microsoft.com/edf59add-0155-4619-9c7c-fdb63b954f85">D3DKMDDI_SHAREDPRIMARYSURFACEDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a>
 

 

