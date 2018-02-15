---
UID: NS:d3dkmthk._D3DKMT_CREATEDEVICE
title: "_D3DKMT_CREATEDEVICE"
author: windows-driver-content
description: The D3DKMT_CREATEDEVICE structure describes a kernel-mode device context.
old-location: display\d3dkmt_createdevice.htm
old-project: display
ms.assetid: 9a624373-e483-484f-b9d1-f9d7aed1caa8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DKMT_CREATEDEVICE, display.d3dkmt_createdevice, d3dkmthk/D3DKMT_CREATEDEVICE, D3DKMT_CREATEDEVICE, D3DKMT_CREATEDEVICE structure [Display Devices], OpenGL_Structs_ed68c4a8-21a9-4754-8909-666a581f7759.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_CREATEDEVICE
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATEDEVICE
---

# _D3DKMT_CREATEDEVICE structure


## -description


The D3DKMT_CREATEDEVICE structure describes a kernel-mode device context.


## -syntax


````
typedef struct _D3DKMT_CREATEDEVICE {
  union {
    D3DKMT_HANDLE hAdapter;
    VOID          *pAdapter;
  };
  D3DKMT_CREATEDEVICEFLAGS Flags;
  D3DKMT_HANDLE            hDevice;
  VOID                     *pCommandBuffer;
  UINT                     CommandBufferSize;
  D3DDDI_ALLOCATIONLIST    *pAllocationList;
  UINT                     AllocationListSize;
  D3DDDI_PATCHLOCATIONLIST *pPatchLocationList;
  UINT                     PatchLocationListSize;
} D3DKMT_CREATEDEVICE;
````


## -struct-fields




### -field hAdapter

[in] A handle to the graphics adapter that the device context is created on. This handle identifies the adapter for user-mode creation. 


### -field pAdapter

[in] A pointer to a block of memory for the graphics adapter that the device context is created on. This pointer identifies the adapter for kernel-mode creation. 


### -field Flags

[in] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createdeviceflags.md">D3DKMT_CREATEDEVICEFLAGS</a> structure that indicates, in bit-field flags, the type of device context to be created.


### -field hDevice

[out] A handle to the device context that the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) supplied and that is returned from the call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a> function.


### -field pCommandBuffer

[out] A pointer to command buffer memory that the OpenGL ICD places commands into. The <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a> function returns this memory pointer.


### -field CommandBufferSize

[out] The size, in bytes, of the memory block that <b>pCommandBuffer</b> points to. The <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a> function returns this size value.


### -field pAllocationList

[out] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationlist.md">D3DDDI_ALLOCATIONLIST</a> structures that the OpenGL ICD inserts referenced allocations in.

The <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a> function returns this value. 


### -field AllocationListSize

[out] The number of elements in the array of allocations that is pointed to by <b>pAllocationList</b>. This quantity of allocations is available when submitting the command buffer that is pointed to by <b>pCommandBuffer</b> to the display miniport driver. 

The <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a> function returns this value. 


### -field pPatchLocationList

[out] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_patchlocationlist.md">D3DDDI_PATCHLOCATIONLIST</a> structures that the OpenGL ICD inserts patching information in.

The <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a> function returns this value. 


### -field PatchLocationListSize

[out] The number of elements in the patch-location list that is pointed to by <b>pPatchLocationList</b>. This quantity of patch locations is available when submitting the command buffer that is pointed to by <b>pCommandBuffer</b> to the display miniport driver. 

The <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a> function returns this value. 


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createdeviceflags.md">D3DKMT_CREATEDEVICEFLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATEDEVICE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

