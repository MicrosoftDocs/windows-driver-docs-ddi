---
UID: NE:d3d10umddi.D3D10_DDI_MAP
title: D3D10_DDI_MAP
author: windows-driver-content
description: The D3D10_DDI_MAP enumeration type contains values that identify the access levels to map to a subresource in a call to the driver's ResourceMap function.
old-location: display\d3d10_ddi_map.htm
old-project: display
ms.assetid: f544ae60-b9c4-497c-8cb5-a2f9500a0cde
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D10_DDI_MAP, D3D10_DDI_MAP enumeration [Display Devices], D3D10_DDI_MAP_READ, D3D10_DDI_MAP_READWRITE, D3D10_DDI_MAP_WRITE, D3D10_DDI_MAP_WRITE_DISCARD, D3D10_DDI_MAP_WRITE_NOOVERWRITE, UMDisplayDriver_Dx10param_Structs_7bf6d24a-def5-4d66-9b15-fee9a619597b.xml, d3d10umddi/D3D10_DDI_MAP, d3d10umddi/D3D10_DDI_MAP_READ, d3d10umddi/D3D10_DDI_MAP_READWRITE, d3d10umddi/D3D10_DDI_MAP_WRITE, d3d10umddi/D3D10_DDI_MAP_WRITE_DISCARD, d3d10umddi/D3D10_DDI_MAP_WRITE_NOOVERWRITE, display.d3d10_ddi_map
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	D3D10_DDI_MAP
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_MAP
---

# D3D10_DDI_MAP enumeration


## -description


The D3D10_DDI_MAP enumeration type contains values that identify the access levels to map to a subresource in a call to the driver's <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function.


## -enum-fields




### -field D3D10_DDI_MAP_READ

Read access is requested for the CPU to the subresource.


### -field D3D10_DDI_MAP_WRITE

Write access is requested for the CPU to the subresource.


### -field D3D10_DDI_MAP_READWRITE

Read and write access is requested for the CPU to the subresource.


### -field D3D10_DDI_MAP_WRITE_DISCARD

Write access is requested for the CPU to the subresource. However, the contents of the subresource become undefined during this operation because the requesting application might completely write over the entire region of memory. You can use this access level only with dynamic resources. 


### -field D3D10_DDI_MAP_WRITE_NOOVERWRITE

Write access is requested for the CPU to the subresource. However, the requesting application will not overwrite any data that was previously used by the GPU. You can use this access level only with dynamic vertex and index buffers. 


## -see-also




<a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a>
 

 

