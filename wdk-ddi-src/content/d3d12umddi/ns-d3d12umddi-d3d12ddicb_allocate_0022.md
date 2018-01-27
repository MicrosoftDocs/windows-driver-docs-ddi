---
UID: NS:d3d12umddi.D3D12DDICB_ALLOCATE_0022
title: D3D12DDICB_ALLOCATE_0022
author: windows-driver-content
description: Specifies information for use in an allocation callback function.
old-location: display\d3d12ddicb_allocate_0022.htm
old-project: display
ms.assetid: C39262BA-D1CE-4634-974A-ACCE8D321830
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDICB_ALLOCATE_0022, D3D12DDICB_ALLOCATE_0022 structure [Display Devices], d3d12umddi/D3D12DDICB_ALLOCATE_0022, display.d3d12ddicb_allocate_0022
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	D3d12umddi.h
apiname: 
-	D3D12DDICB_ALLOCATE_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDICB_ALLOCATE_0022
---

# D3D12DDICB_ALLOCATE_0022 structure


## -description


Specifies information for use in an allocation callback function. 


## -syntax


````
typedef struct D3D12DDICB_ALLOCATE_0022 {
  const VOID                    *pPrivateDriverData;
  UINT                          PrivateDriverDataSize;
  HANDLE                        hResource;
  D3DKMT_HANDLE                 hKMResource;
  UINT                          NumAllocations;
  D3D12DDI_ALLOCATION_INFO_0022 *pAllocationInfo;
} D3D12DDICB_ALLOCATE_0022;
````


## -struct-fields




### -field pPrivateDriverData

A pointer to a buffer that contains optional private driver data.


### -field PrivateDriverDataSize

Size of the private driver data.


### -field hResource

The handle of a resource. 


### -field hKMResource

A handle of a kernel resource. 


### -field NumAllocations

The number of allocations.


### -field pAllocationInfo

Allocation as a <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_allocation_info_0022.md">D3D12DDI_ALLOCATION_INFO_0022</a> structure. 


## -see-also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_allocation_info_0022.md">D3D12DDI_ALLOCATION_INFO_0022</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDICB_ALLOCATE_0022 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

