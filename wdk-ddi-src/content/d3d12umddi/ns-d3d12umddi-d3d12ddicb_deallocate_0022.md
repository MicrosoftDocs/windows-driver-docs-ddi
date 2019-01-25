---
UID: NS:d3d12umddi.D3D12DDICB_DEALLOCATE_0022
title: D3D12DDICB_DEALLOCATE_0022 (d3d12umddi.h)
description: Specifies values for use with a deallocation callback function.
old-location: display\d3d12ddicb_deallocate_0022.htm
ms.assetid: 977868D1-02E1-4460-9194-2079B986045E
ms.date: 05/10/2018
ms.keywords: D3D12DDICB_DEALLOCATE_0022, D3D12DDICB_DEALLOCATE_0022 structure [Display Devices], d3d12umddi/D3D12DDICB_DEALLOCATE_0022, display.d3d12ddicb_deallocate_0022
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
-	D3D12DDICB_DEALLOCATE_0022
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDICB_DEALLOCATE_0022
---

# D3D12DDICB_DEALLOCATE_0022 structure


## -description


Specifies values for use with a deallocation callback function. 


## -struct-fields




### -field hResource

The handle of a resource.


### -field NumAllocations


### -field HandleList

A pointer to a list of kernel handles.


### -field Flags

Flags to use for deallocation, as specified in the <a href="https://msdn.microsoft.com/17E3C01A-0716-4B3C-B4B3-72B055FB40EA">D3D12DDI_DEALLOCATE_FLAGS_0022</a> enumeration.


## -see-also




<a href="https://msdn.microsoft.com/17E3C01A-0716-4B3C-B4B3-72B055FB40EA">D3D12DDI_DEALLOCATE_FLAGS_0022</a>
 

 

