---
UID: NS:d3dkmddi._DXGK_ALLOCATIONUSAGEHINT
title: "_DXGK_ALLOCATIONUSAGEHINT"
author: windows-driver-content
description: The DXGK_ALLOCATIONUSAGEHINT structure contains allocation usage and version information that is used as a hint about how to use an allocation.
old-location: display\dxgk_allocationusagehint.htm
old-project: display
ms.assetid: 04cceb5e-d185-4f43-a627-71a61a45b8aa
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGK_ALLOCATIONUSAGEHINT, DXGK_ALLOCATIONUSAGEHINT structure [Display Devices], DmStructs_9597c610-bb79-496c-b7b3-9fb5abb30a46.xml, _DXGK_ALLOCATIONUSAGEHINT, d3dkmddi/DXGK_ALLOCATIONUSAGEHINT, display.dxgk_allocationusagehint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	d3dkmddi.h
api_name:
-	DXGK_ALLOCATIONUSAGEHINT
product: Windows
targetos: Windows
req.typenames: DXGK_ALLOCATIONUSAGEHINT
---

# _DXGK_ALLOCATIONUSAGEHINT structure


## -description


The DXGK_ALLOCATIONUSAGEHINT structure contains allocation usage and version information that is used as a hint about how to use an allocation.


## -struct-fields




### -field Version

[out] A positive integer that indicates the version of the allocation.


### -field v1

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560986">DXGK_ALLOCATIONUSAGEINFO1</a> structure that describes how an allocation can be used in direct memory access (DMA) buffering.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560986">DXGK_ALLOCATIONUSAGEINFO1</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>
 

 

