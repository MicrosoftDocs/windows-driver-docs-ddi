---
UID: NS:d3dkmthk._D3DKMT_OPENRESOURCE
title: "_D3DKMT_OPENRESOURCE"
author: windows-driver-content
description: The D3DKMT_OPENRESOURCE structure describes parameters for opening a resource.
old-location: display\d3dkmt_openresource.htm
old-project: display
ms.assetid: 5ff63606-ced1-4482-b967-41db4746ac1d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMT_OPENRESOURCE, D3DKMT_OPENRESOURCE, OpenGL_Structs_b069a94a-b78c-4fbf-b78d-7c5b0d025655.xml, D3DKMT_OPENRESOURCE structure [Display Devices], _D3DKMT_OPENRESOURCE, display.d3dkmt_openresource
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
-	D3DKMT_OPENRESOURCE
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENRESOURCE
---

# _D3DKMT_OPENRESOURCE structure


## -description


The D3DKMT_OPENRESOURCE structure describes parameters for opening a resource.


## -syntax


````
typedef struct _D3DKMT_OPENRESOURCE {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hGlobalShare;
  UINT          NumAllocations;
  union {
    D3DDDI_OPENALLOCATIONINFO  *pOpenAllocationInfo;
#if ((DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7) || \
     (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7))
    D3DDDI_OPENALLOCATIONINFO2 *pOpenAllocationInfo2;
#endif 
  };
  VOID          *pPrivateRuntimeData;
  UINT          PrivateRuntimeDataSize;
  VOID          *pResourcePrivateDriverData;
  UINT          ResourcePrivateDriverDataSize;
  VOID          *pTotalPrivateDriverDataBuffer;
  UINT          TotalPrivateDriverDataBufferSize;
  D3DKMT_HANDLE hResource;
} D3DKMT_OPENRESOURCE;
````


## -struct-fields




#### - pOpenAllocationInfo

[in/out] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a> structures that describe each allocation to update.


#### - pOpenAllocationInfo2

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


#### - hDevice

[in] A handle to the device that the resource and allocations are associated with.


#### - hGlobalShare

[in] A handle to the shared resource to open.


#### - NumAllocations

[in] The number of elements in the array that <b>pOpenAllocationInfo</b> specifies, which represents the number of allocations that are associated with the resource.


#### - pPrivateRuntimeData

[in] A pointer to a caller-supplied buffer where the OpenGL runtime copies private data that is associated with the resource.


#### - PrivateRuntimeDataSize

[in] The size, in bytes, of the buffer that <b>pPrivateRuntimeData</b> points to.


#### - pResourcePrivateDriverData

[in/out] A pointer to a buffer that receives the private data that is associated with the resource. This data is per resource and not per allocation.


#### - ResourcePrivateDriverDataSize

[in] The size, in bytes, of the buffer that <b>pResourcePrivateDriverData</b> points to.


#### - pTotalPrivateDriverDataBuffer

[in/out] A pointer to a buffer that receives the private data for all of the allocations that are associated with the resource. The caller should never access this private data directly.


#### - TotalPrivateDriverDataBufferSize

[in/out] On input, the size, in bytes, of the buffer that <b>pTotalPrivateDriverDataBuffer</b> points to. On output, this member specifies the size, in bytes, of data that is written to the buffer that <b>pTotalPrivateDriverDataBuffer</b> points to.


#### - hResource

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the newly opened shared resource that is associated with the allocations.


## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenresource.md">D3DKMTOpenResource</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OPENRESOURCE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

