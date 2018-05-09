---
UID: NS:d3d12umddi.D3D12DDICB_ALLOCATE_0022
title: D3D12DDICB_ALLOCATE_0022
author: windows-driver-content
description: Specifies information for use in an allocation callback function.
old-location: display\d3d12ddicb_allocate_0022.htm
old-project: display
ms.assetid: C39262BA-D1CE-4634-974A-ACCE8D321830
ms.author: windowsdriverdev
ms.date: 4/16/2018
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDICB_ALLOCATE_0022
product:
- Windows
targetos: Windows
req.typenames: D3D12DDICB_ALLOCATE_0022
---

# D3D12DDICB_ALLOCATE_0022 structure


## -description


Specifies information for use in an allocation callback function. 


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

Allocation as a <a href="https://msdn.microsoft.com/A600C402-EB77-4C44-8349-96DAF11B807C">D3D12DDI_ALLOCATION_INFO_0022</a> structure. 


## -see-also




<a href="https://msdn.microsoft.com/A600C402-EB77-4C44-8349-96DAF11B807C">D3D12DDI_ALLOCATION_INFO_0022</a>
 

 

