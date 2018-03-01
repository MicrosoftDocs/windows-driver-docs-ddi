---
UID: NS:d3dkmthk._D3DKMT_LOCK
title: "_D3DKMT_LOCK"
author: windows-driver-content
description: The D3DKMT_LOCK structure describes parameters for locking an allocation.
old-location: display\d3dkmt_lock.htm
old-project: display
ms.assetid: 0f985d0b-2b98-413d-a736-c507743ac786
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_LOCK, D3DKMT_LOCK structure [Display Devices], OpenGL_Structs_08e60652-b888-4a1e-a9c6-3dee8f0fb50d.xml, _D3DKMT_LOCK, d3dkmthk/D3DKMT_LOCK, display.d3dkmt_lock
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	D3DKMT_LOCK
product: Windows
targetos: Windows
req.typenames: D3DKMT_LOCK
---

# _D3DKMT_LOCK structure


## -description


The D3DKMT_LOCK structure describes parameters for locking an allocation. 


## -syntax


````
typedef struct _D3DKMT_LOCK {
  D3DKMT_HANDLE          hDevice;
  D3DKMT_HANDLE          hAllocation;
  UINT                   PrivateDriverData;
  UINT                   NumPages;
  const UINT             *pPages;
  VOID                   *pData;
  D3DDDICB_LOCKFLAGS     Flags;
  D3DGPU_VIRTUAL_ADDRESS GpuVirtualAddress;
} D3DKMT_LOCK;
````


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that the allocation is associated with.


### -field hAllocation

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation to lock.


### -field PrivateDriverData

[in] A UINT value that specifies 32 bits of private data (for example, MIP level) that is sent from the OpenGL ICD to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a> function.


### -field NumPages

[in] The number of pages in the page list that <b>pPages</b> specifies.


### -field pPages

[in] An array of pages to lock. Each page in the array is described by an integer offset. Zero means the first page in the surface, one means the second, and so on. 


### -field pData

[out] A pointer to the memory that is returned from the display miniport driver and memory manager. When locking a memory page list, the pointer that is returned is a pointer to the first memory page.


### -field Flags

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_lockflags.md">D3DDDICB_LOCKFLAGS</a> structure that identifies, in bit-field flags, how to lock the allocation.

Note that specifying some flags together is invalid and that some flags depend on other flags. For more information about these combinations, see the Remarks section of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_lockflags.md">D3DDDICB_LOCKFLAGS</a>.


### -field GpuVirtualAddress

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtlock.md">D3DKMTLock</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_lockflags.md">D3DDDICB_LOCKFLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_LOCK structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

