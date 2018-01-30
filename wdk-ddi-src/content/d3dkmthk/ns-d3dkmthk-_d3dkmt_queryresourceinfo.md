---
UID: NS:d3dkmthk._D3DKMT_QUERYRESOURCEINFO
title: "_D3DKMT_QUERYRESOURCEINFO"
author: windows-driver-content
description: The D3DKMT_QUERYRESOURCEINFO structure describes parameters for retrieving information about a resource.
old-location: display\d3dkmt_queryresourceinfo.htm
old-project: display
ms.assetid: 14078b2b-8951-48df-912a-e053bc997dde
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMT_QUERYRESOURCEINFO, D3DKMT_QUERYRESOURCEINFO, display.d3dkmt_queryresourceinfo, D3DKMT_QUERYRESOURCEINFO structure [Display Devices], OpenGL_Structs_1bab95d7-d3a4-4380-939f-bca4e2d98478.xml, _D3DKMT_QUERYRESOURCEINFO
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
-	D3DKMT_QUERYRESOURCEINFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_QUERYRESOURCEINFO
---

# _D3DKMT_QUERYRESOURCEINFO structure


## -description


The D3DKMT_QUERYRESOURCEINFO structure describes parameters for retrieving information about a resource.


## -syntax


````
typedef struct _D3DKMT_QUERYRESOURCEINFO {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hGlobalShare;
  VOID          *pPrivateRuntimeData;
  UINT          PrivateRuntimeDataSize;
  UINT          TotalPrivateDriverDataSize;
  UINT          ResourcePrivateDriverDataSize;
  UINT          NumAllocations;
} D3DKMT_QUERYRESOURCEINFO;
````


## -struct-fields




### -field hDevice

[in] A handle to the device that the resource and allocations are associated with.


### -field hGlobalShare

[in] A handle to the shared resource to open.


### -field pPrivateRuntimeData

[in] If non-<b>NULL</b>, a pointer to a buffer that receives the runtime-private data that is supplied at create time. The OpenGL ICD should first call the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryresourceinfo.md">D3DKMTQueryResourceInfo</a> function with <b>pPrivateRuntimeData</b> set to <b>NULL</b> to obtain the buffer size and then call again with the correct size buffer. 


### -field PrivateRuntimeDataSize

[in/out] The size, in bytes, of the buffer that <b>pPrivateRuntimeData</b> points to. If <b>pPrivateRuntimeData</b> is <b>NULL</b>, <b>PrivateRuntimeDataSize</b> is set to the size, in bytes, that is required for the buffer to store the runtime-private data.


### -field TotalPrivateDriverDataSize

[out] The size, in bytes, of the buffer that is required to hold the private driver data for all of the allocations that are associated with the resource.


### -field ResourcePrivateDriverDataSize

[out] The size, in bytes, of the buffer that is required to hold the private driver data for the resource.


### -field NumAllocations

[out] The number of allocations that are associated with the resource.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryresourceinfo.md">D3DKMTQueryResourceInfo</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenresource.md">D3DKMTOpenResource</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_QUERYRESOURCEINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

