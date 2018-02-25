---
UID: NS:d3d10umddi._D3D11_1DDI_GETCAPTUREHANDLEDATA
title: "_D3D11_1DDI_GETCAPTUREHANDLEDATA"
author: windows-driver-content
description: Defines a resource allocation in a call to the GetCaptureHandle function.
old-location: display\d3d11_1ddi_getcapturehandledata.htm
old-project: display
ms.assetid: f12ace3a-2bb4-433b-b987-2027a48f4c14
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 1, 3, A, C, D, D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA structure [Display Devices], E, G, H, I, L, N, P, R, T, U, _, _D3D11_1DDI_GETCAPTUREHANDLEDATA, d3d10umddi/D3D11_1DDI_GETCAPTUREHANDLEDATA, display.d3d11_1ddi_getcapturehandledata"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_GETCAPTUREHANDLEDATA
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# _D3D11_1DDI_GETCAPTUREHANDLEDATA structure


## -description


Defines a resource allocation in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md">GetCaptureHandle</a> function.


## -syntax


````
typedef struct _D3D11_1DDI_GETCAPTUREHANDLEDATA {
  D3D10DDI_HRESOURCE hResource;
  UINT               ArrayIndex;
  D3DKMT_HANDLE      hAllocation;
  UINT               DataOffset;
  UINT               DataSize;
} D3D11_1DDI_GETCAPTUREHANDLEDATA;
````


## -struct-fields




### -field hResource

[in] The handle to the resource for which the allocation handle is to be obtained.

The Direct3D version 11 and later runtime will have already verified that this resource was created using the <b>D3D11_DDI_BIND_CAPTURE</b> value in the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a> enumeration.


### -field ArrayIndex

[in] The array element from which the data is to be obtained.

If the resource was not created as a texture array, this value is zero. For a texture array, the Direct3D version 11 and later runtime will have already verified that the array is valid.


### -field hAllocation

[out] The driver-provided address of the kernel mode allocation handle associated with this allocation.


### -field DataOffset

[out] The driver-provided offset of the requested data within the allocation.

If the resource was not created as a texture array, this value is typically zero.  For a texture array, this value is the offset of the array element data within the allocation.


### -field DataSize

[out] The driver-provided size of the requested data within the allocation.

If the resource was not created as a texture array, this value is typically the size of the allocation, in bytes.  For a texture array, this value is the size of the element data within the allocation.


## -remarks



When the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md">GetCaptureHandle</a> function is called, the driver updates the structure with the kernel mode allocation handle associated with the specified resource, as well as the size of the resource data and its offset within an allocated block of memory.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md">GetCaptureHandle</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_GETCAPTUREHANDLEDATA structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

