---
UID: NS:d3dukmdt.D3DDDI_MAKERESIDENT
title: D3DDDI_MAKERESIDENT
author: windows-driver-content
description: D3DDDI_MAKERESIDENT is used with MakeResident (pfnMakeResidentCb or D3DKMTMakeResident) to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
old-location: display\d3dddi_makeresident.htm
old-project: display
ms.assetid: 16F04DFD-3AF6-48E0-9BCF-9FE0FC397F91
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_MAKERESIDENT, D3DDDI_MAKERESIDENT structure [Display Devices], d3dukmdt/D3DDDI_MAKERESIDENT, display.d3dddi_makeresident
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dukmdt.h
api_name:
-	D3DDDI_MAKERESIDENT
product: Windows
targetos: Windows
req.typenames: D3DDDI_MAKERESIDENT
---

# D3DDDI_MAKERESIDENT structure


## -description


<b>D3DDDI_MAKERESIDENT</b> is used with <b>MakeResident</b> (<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_makeresidentcb.md">pfnMakeResidentCb</a> or <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtmakeresident.md">D3DKMTMakeResident</a>) to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.


## -syntax


````
typedef struct D3DDDI_MAKERESIDENT {
  D3DKMT_HANDLE             hPagingQueue;
  UINT                      NumAllocations;
  const D3DKMT_HANDLE       *AllocationList;
  const UINT                *PriorityList;
  D3DDDI_MAKERESIDENT_FLAGS Flags;
  UINT64                    PagingFenceValue;
  UINT64                    NumBytesToTrim;
} D3DDDI_MAKERESIDENT;
````


## -struct-fields




### -field hPagingQueue

[in] Paging queue on the device that created the input allocations. This queue will be used for residency operations.


### -field NumAllocations

[in/out] On input, the number of allocation handles in the <b>AllocationList</b> array and allocation priority values in the <b>PriorityList</b> array. On output,
                                                    the number of allocations successfully made resident.


### -field AllocationList

[in] An array of <b>NumAllocations</b> allocation handles to make resident. All allocations must be created on the device <b>hPagingQueue</b> is created for.


### -field PriorityList

[in] An array of <b>NumAllocations</b> specifying residency priority for each of the input allocations. This value is currently ignored and may be set to <b>NULL</b>.


### -field Flags

[in] Specifies memory residency behavior as documented in <a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_makeresident_flags.md">D3DDDI_MAKERESIDENT_FLAGS</a>.


### -field PagingFenceValue

[out] When <b>MakeResident</b> returns <b>E_PENDING</b>, this member indicates the paging queue fence value to wait on. 


### -field NumBytesToTrim

[out] When <b>MakeResident</b> returns <b>E_OUTOFMEMORY</b>, this member indicates the number of bytes over budget the application would be if the allocation(s) were made resident. 


## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_makeresident_flags.md">D3DDDI_MAKERESIDENT_FLAGS</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtmakeresident.md">D3DKMTMakeResident</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_makeresidentcb.md">pfnMakeResidentCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_MAKERESIDENT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

