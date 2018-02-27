---
UID: NS:d3d12umddi.D3D12DDICB_DEALLOCATE_0022
title: D3D12DDICB_DEALLOCATE_0022
author: windows-driver-content
description: Specifies values for use with a deallocation callback function.
old-location: display\d3d12ddicb_deallocate_0022.htm
old-project: display
ms.assetid: 977868D1-02E1-4460-9194-2079B986045E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDICB_DEALLOCATE_0022, D3D12DDICB_DEALLOCATE_0022 structure [Display Devices], d3d12umddi/D3D12DDICB_DEALLOCATE_0022, display.d3d12ddicb_deallocate_0022
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
-	D3D12DDICB_DEALLOCATE_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDICB_DEALLOCATE_0022
---

# D3D12DDICB_DEALLOCATE_0022 structure


## -description


Specifies values for use with a deallocation callback function. 


## -syntax


````
typedef struct D3D12DDICB_DEALLOCATE_0022 {
  HANDLE                         hResource;
  UINT                           NumAllocations;
  const D3DKMT_HANDLE            *HandleList;
  D3D12DDI_DEALLOCATE_FLAGS_0022 Flags;
} D3D12DDICB_DEALLOCATE_0022;
````


## -struct-fields




### -field hResource

The handle of a resource.


### -field NumAllocations


### -field HandleList

A pointer to a list of kernel handles.


### -field Flags

Flags to use for deallocation, as specified in the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_deallocate_flags_0022.md">D3D12DDI_DEALLOCATE_FLAGS_0022</a> enumeration.


## -see-also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_deallocate_flags_0022.md">D3D12DDI_DEALLOCATE_FLAGS_0022</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDICB_DEALLOCATE_0022 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

