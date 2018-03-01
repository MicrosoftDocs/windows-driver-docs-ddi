---
UID: NS:d3dkmthk._D3DKMT_CREATECONTEXT
title: "_D3DKMT_CREATECONTEXT"
author: windows-driver-content
description: The D3DKMT_CREATECONTEXT structure describes a kernel-mode device context to create.
old-location: display\d3dkmt_createcontext.htm
old-project: display
ms.assetid: 867705b9-a721-48a6-b1bc-6a75d5a03a21
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_CREATECONTEXT, D3DKMT_CREATECONTEXT structure [Display Devices], OpenGL_Structs_5a3cc128-be06-4189-a389-95813c2d3e28.xml, _D3DKMT_CREATECONTEXT, d3dkmthk/D3DKMT_CREATECONTEXT, display.d3dkmt_createcontext
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
-	D3DKMT_CREATECONTEXT
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATECONTEXT
---

# _D3DKMT_CREATECONTEXT structure


## -description


The D3DKMT_CREATECONTEXT structure describes a kernel-mode device context to create.


## -syntax


````
typedef struct _D3DKMT_CREATECONTEXT {
  D3DKMT_HANDLE             hDevice;
  UINT                      NodeOrdinal;
  UINT                      EngineAffinity;
  D3DDDI_CREATECONTEXTFLAGS Flags;
  VOID                      *pPrivateDriverData;
  UINT                      PrivateDriverDataSize;
  D3DKMT_CLIENTHINT         ClientHint;
  D3DKMT_HANDLE             hContext;
  VOID                      *pCommandBuffer;
  UINT                      CommandBufferSize;
  D3DDDI_ALLOCATIONLIST     *pAllocationList;
  UINT                      AllocationListSize;
  D3DDDI_PATCHLOCATIONLIST  *pPatchLocationList;
  UINT                      PatchLocationListSize;
  D3DGPU_VIRTUAL_ADDRESS    CommandBuffer;
} D3DKMT_CREATECONTEXT;
````


## -struct-fields




### -field hDevice

[in] A handle to the device to create the device context on. 


### -field NodeOrdinal

[in] The zero-based index of the node that the context is scheduled on.


### -field EngineAffinity

[in] The engine affinity for the context.


### -field Flags

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_createcontextflags.md">D3DDDI_CREATECONTEXTFLAGS</a> structure that indicates, in bit-field flags, how to create the context. 


### -field pPrivateDriverData

[in] A pointer to private data that is passed to the display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


### -field ClientHint

[in] A D3DKMT_CLIENTHINT-typed value that indicates the type of client that creates the context. The following table lists the possible values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DKMT_CLIENTHINT_UNKNOWN (0)

</td>
<td>
The client is unknown.

</td>
</tr>
<tr>
<td>
D3DKMT_CLIENTHINT_OPENGL (1)

</td>
<td>
The client is the OpenGL runtime.

</td>
</tr>
<tr>
<td>
D3DKMT_CLIENTHINT_CDD (2)

</td>
<td>
This value is for internal use only. Do not use.

</td>
</tr>
<tr>
<td>
D3DKMT_CLIENTHINT_DX7 (7)

</td>
<td>
The client is the Microsoft DirectX 7.0 runtime.

</td>
</tr>
<tr>
<td>
D3DKMT_CLIENTHINT_DX8 (8)

</td>
<td>
The client is the DirectX 8.0 runtime.

</td>
</tr>
<tr>
<td>
D3DKMT_CLIENTHINT_DX9 (9)

</td>
<td>
The client is the DirectX 9.0 runtime.

</td>
</tr>
<tr>
<td>
D3DKMT_CLIENTHINT_DX10 (10)

</td>
<td>
The client is the DirectX 10.0 runtime.

</td>
</tr>
</table>
 


### -field hContext

[out] A handle to the device context that the DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) supplied and that is returned from the call to the <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createcontext.md">D3DKMTCreateContext</a> function.


### -field pCommandBuffer

[out] A pointer to command buffer memory that the OpenGL ICD places commands into. The <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createcontext.md">D3DKMTCreateContext</a> function returns this memory pointer.


### -field CommandBufferSize

[out] The size, in bytes, of the memory block that <b>pCommandBuffer</b> points to. The <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createcontext.md">D3DKMTCreateContext</a> function returns this size value.


### -field pAllocationList

[out] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationlist.md">D3DDDI_ALLOCATIONLIST</a> structures that the OpenGL ICD inserts referenced allocations in.

The <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createcontext.md">D3DKMTCreateContext</a> function returns this array. 


### -field AllocationListSize

[out] The number of elements in the array of allocations that <b>pAllocationList</b> points to. This quantity of allocations is available when the DirectX graphics kernel subsystem submits the command buffer that is pointed to by <b>pCommandBuffer</b> to the display miniport driver. 

The <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createcontext.md">D3DKMTCreateContext</a> function returns this number. 


### -field pPatchLocationList

[out] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_patchlocationlist.md">D3DDDI_PATCHLOCATIONLIST</a> structures that the OpenGL ICD inserts patching information in.

The <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createcontext.md">D3DKMTCreateContext</a> function returns this array. 


### -field PatchLocationListSize

[out] The number of elements in the patch-location list that <b>pPatchLocationList</b> points to. This quantity of patch locations is available when the DirectX graphics kernel subsystem submits the command buffer that is pointed to by <b>pCommandBuffer</b> to the display miniport driver. 

The <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createcontext.md">D3DKMTCreateContext</a> function returns this number. 


### -field CommandBuffer

[out] A pointer to command buffer memory that the OpenGL ICD places commands into. The <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createcontext.md">D3DKMTCreateContext</a> function returns this memory pointer.


## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationlist.md">D3DDDI_ALLOCATIONLIST</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_createcontextflags.md">D3DDDI_CREATECONTEXTFLAGS</a>



<a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createcontext.md">D3DKMTCreateContext</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_patchlocationlist.md">D3DDDI_PATCHLOCATIONLIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATECONTEXT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

