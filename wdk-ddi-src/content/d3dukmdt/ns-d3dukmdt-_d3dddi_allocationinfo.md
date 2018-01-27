---
UID: NS:d3dukmdt._D3DDDI_ALLOCATIONINFO
title: _D3DDDI_ALLOCATIONINFO
author: windows-driver-content
description: The D3DDDI_ALLOCATIONINFO structure describes an allocation.
old-location: display\d3dddi_allocationinfo.htm
old-project: display
ms.assetid: 69181a7c-62bd-4df0-95fc-fe6c3ab14209
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D_other_Structs_5125c057-c4b7-45fd-b7d9-9ebcfce4fff7.xml, D3DDDI_ALLOCATIONINFO structure [Display Devices], D3DDDI_ALLOCATIONINFO, _D3DDDI_ALLOCATIONINFO, display.d3dddi_allocationinfo, d3dukmdt/D3DDDI_ALLOCATIONINFO
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dukmdt.h
apiname: 
-	D3DDDI_ALLOCATIONINFO
product: Windows
targetos: Windows
req.typenames: D3DDDI_ALLOCATIONINFO
---

# _D3DDDI_ALLOCATIONINFO structure


## -description


The D3DDDI_ALLOCATIONINFO structure describes an allocation.


## -syntax


````
typedef struct _D3DDDI_ALLOCATIONINFO {
  D3DKMT_HANDLE                  hAllocation;
  const VOID                     *pSystemMem;
  VOID                           *pPrivateDriverData;
  UINT                           PrivateDriverDataSize;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  union {
    struct {
      UINT Primary  :1;
#if ((DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8) || \
     (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN8))
      UINT Stereo  :1;
      UINT Reserved  :30;
#else 
      UINT Reserved  :31;
#endif 
    };
    UINT Value;
  } Flags;
} D3DDDI_ALLOCATIONINFO;
````


## -struct-fields




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


### -field hAllocation

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation. This kernel-mode allocation handle is associated with the kernel-mode resource handle (if non-<b>NULL</b>) that the Microsoft Direct3D runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function returns in the <b>hKMResource</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_allocate.md">D3DDDICB_ALLOCATE</a> structure. The user-mode display driver can use this kernel-mode allocation handle to reference the allocation in the command buffer.


### -field pSystemMem

[in] A pointer to system memory that the Direct3D runtime preallocated. Otherwise, this member is <b>NULL</b> if the allocation is to use video memory. 

If the allocation is in system memory, the user-mode display driver should assign the buffer in the <b>pSysMem</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_surfaceinfo.md">D3DDDI_SURFACEINFO</a> structure for the resource to <b>pSystemMem</b>. This buffer is specified when the Direct3D runtime calls the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function to create resources. 


### -field pPrivateDriverData

[in/out] A pointer to buffer that contains optional private data that might be required by the display miniport driver to create the allocation. The display miniport driver can also return data in the buffer. When the contents of the buffer are passed to the display miniport driver, the contents must be in a format that the display miniport driver can process. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology if the allocation is for the primary surface. The driver should set <b>VidPnSourceId</b> only for primary allocation types and not for any other type of allocation. If the driver sets <b>VidPnSourceId</b> for any other allocation type in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function, <b>pfnAllocateCb</b> returns D3DDDI_ID_NOTAPPLICABLE.

When the DirectX graphics kernel subsystem initiates the creation of the allocation for the shared primary surface, the display miniport driver can determine the identification number from the <b>VidPnSourceId</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata.md">D3DKMDDI_SHAREDPRIMARYSURFACEDATA</a> structure that the <b>pPrivateDriverData</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure points to. 


## -remarks


When the user-mode display driver sets the <b>Primary</b> bit-field flag in the <b>Flags</b> member of D3DDDI_ALLOCATIONINFO, certain restrictions apply to the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure in the <b>pAllocationInfo</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a> structure for the allocation in a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function. These restrictions include the following: 
<ul>
<li>
The allocation is allocated according to preferences; otherwise, the allocation defaults to the supported write segment set, and all of the specified segments in the write segment set must be CPU-accessible.

</li>
<li>The display miniport driver cannot set the following bit-field flags in the  <b>Flags</b> member of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>:<ul>
<li><b>PermanentSysMem</b></li>
<li><b>Cached</b></li>
<li><b>Protected</b></li>
<li><b>ExistingSysMem</b></li>
<li><b>ExistingKernelSysMem</b></li>
</ul>
</li>
</ul>The D3DDDI_ID_NOTAPPLICABLE constant is defined in D3dukmdt.h.



## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata.md">D3DKMDDI_SHAREDPRIMARYSURFACEDATA</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_surfaceinfo.md">D3DDDI_SURFACEINFO</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_allocate.md">D3DDDICB_ALLOCATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_ALLOCATIONINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

