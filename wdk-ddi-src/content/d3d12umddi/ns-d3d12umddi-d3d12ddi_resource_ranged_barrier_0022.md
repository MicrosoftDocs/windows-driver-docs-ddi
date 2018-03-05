---
UID: NS:d3d12umddi.D3D12DDI_RESOURCE_RANGED_BARRIER_0022
title: D3D12DDI_RESOURCE_RANGED_BARRIER_0022
author: windows-driver-content
description: Describes a resource ranged barrier.
old-location: display\d3d12ddi_resource_ranged_barrier_0022.htm
old-project: display
ms.assetid: 759BA42A-2F38-42D3-A245-8DEA2919DC39
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_RESOURCE_RANGED_BARRIER_0022, D3D12DDI_RESOURCE_RANGED_BARRIER_0022 structure [Display Devices], d3d12umddi/D3D12DDI_RESOURCE_RANGED_BARRIER_0022, display.d3d12ddi_resource_ranged_barrier_0022
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
-	D3D12DDI_RESOURCE_RANGED_BARRIER_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_RESOURCE_RANGED_BARRIER_0022
---

# D3D12DDI_RESOURCE_RANGED_BARRIER_0022 structure


## -description


Describes a resource ranged barrier.


## -syntax


````
typedef struct D3D12DDI_RESOURCE_RANGED_BARRIER_0022 {
  D3D12DDI_HRESOURCE hResource;
  UINT               Subresource;
  D3D12DDI_RANGE     Range;
} D3D12DDI_RESOURCE_RANGED_BARRIER_0022;
````


## -struct-fields




### -field hResource

The handle of a resource. A null value means that the entire GPU cache must be flushed or invalidated. A non-null value means that the flush or invalidate action affects a smaller subset of the cache that can contain data for that resource. 


### -field Subresource

A subresource. If the <i>Subresource</i> value  is -1 or _ALL_SUBRESOURCES, then a flush or invalidate action need only affect the part of the cache where the entire <i>hResource</i> may reside. If <i>Subresource</i> is not  _ALL_SUBRESOURCES,  a valid subresource index is specified and the <i>Range</i> may further constrain the impact of the operation. 


### -field Range

A range as a <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_range.md">D3D12DDI_RANGE</a> structure. If the resource is a texture with an adapter-dependent layout, the range must be (0, UINT64_MAX), because only the driver knows where a particular subresource resides. When the resource is a buffer or texture with well-specified layout, the range fits within the subresource extent. Empty ranges are never passed.


## -see-also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_range.md">D3D12DDI_RANGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_RESOURCE_RANGED_BARRIER_0022 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

