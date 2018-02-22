---
UID: NS:d3d12umddi.D3D12DDI_RESOURCE_ALLOCATION_INFO_0022
title: D3D12DDI_RESOURCE_ALLOCATION_INFO_0022
author: windows-driver-content
description: Specifies information for resource allocation.
old-location: display\d3d12ddi_resource_allocation_info_0022.htm
old-project: display
ms.assetid: 71CDBF47-B32D-4084-B2F6-9F8C037FCB79
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3d12umddi/D3D12DDI_RESOURCE_ALLOCATION_INFO_0022, display.d3d12ddi_resource_allocation_info_0022, D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 structure [Display Devices], D3D12DDI_RESOURCE_ALLOCATION_INFO_0022
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
-	D3D12DDI_RESOURCE_ALLOCATION_INFO_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_RESOURCE_ALLOCATION_INFO_0022
---

# D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 structure


## -description


Specifies information for resource allocation.


## -syntax


````
typedef struct D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 {
  UINT64                   ResourceDataSize;
  AdditionalDataHeaderSize UINT64;
  UINT64                   AdditionalDataSize;
  UINT32                   ResourceDataAlignment;
  UINT32                   AdditionalDataHeaderAlignment;
  UINT32                   AdditionalDataAlignment;
  D3D12DDI_TEXTURE_LAYOUT  Layout;
  UINT8                    MipLevelSwizzleTransition[5];
  UINT8                    PlaneSliceSwizzleTransition[2];
} D3D12DDI_RESOURCE_ALLOCATION_INFO_0022;
````


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

The texture layout as a <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_texture_layout.md">D3D12DDI_TEXTURE_LAYOUT</a> value. 


### -field MipLevelSwizzleTransition

The MIP level for a swizzle transition.


### -field PlaneSliceSwizzleTransition

The plane slice for a swizzle transition. 


#### - UINT64

The additional size of the data header.


## -see-also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_texture_layout.md">D3D12DDI_TEXTURE_LAYOUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

