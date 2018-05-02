---
UID: NS:d3d12umddi.D3D12DDI_RESOURCE_ALLOCATION_INFO_0022
title: D3D12DDI_RESOURCE_ALLOCATION_INFO_0022
author: windows-driver-content
description: Specifies information for resource allocation.
old-location: display\d3d12ddi_resource_allocation_info_0022.htm
old-project: display
ms.assetid: 71CDBF47-B32D-4084-B2F6-9F8C037FCB79
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D12DDI_RESOURCE_ALLOCATION_INFO_0022, D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 structure [Display Devices], d3d12umddi/D3D12DDI_RESOURCE_ALLOCATION_INFO_0022, display.d3d12ddi_resource_allocation_info_0022
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
-	D3D12DDI_RESOURCE_ALLOCATION_INFO_0022
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_RESOURCE_ALLOCATION_INFO_0022
---

# D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 structure


## -description


Specifies information for resource allocation.


## -struct-fields




### -field ResourceDataSize

The data size of  the resource. 


### -field AdditionalDataHeaderSize

 


### -field AdditionalDataSize

The additional data size.


### -field ResourceDataAlignment

The data alignment of the resource.


### -field AdditionalDataHeaderAlignment

The data alignment of the additional header.


### -field AdditionalDataAlignment

The additional data alignment. 


### -field Layout

The texture layout as a <a href="https://msdn.microsoft.com/F039A0D9-D1AE-4940-B67D-30CC6344EC7D">D3D12DDI_TEXTURE_LAYOUT</a> value. 


### -field MipLevelSwizzleTransition

The MIP level for a swizzle transition.


### -field PlaneSliceSwizzleTransition

The plane slice for a swizzle transition. 


#### - UINT64

The additional size of the data header.


## -see-also




<a href="https://msdn.microsoft.com/F039A0D9-D1AE-4940-B67D-30CC6344EC7D">D3D12DDI_TEXTURE_LAYOUT</a>
 

 

