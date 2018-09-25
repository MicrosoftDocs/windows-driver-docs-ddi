---
UID: NS:d3dkmthk._D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN
title: "_D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN"
author: windows-driver-content
description: The D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure identifies a bit-block transfer (bitblt) present-history operation.
old-location: display\d3dkmt_bltmodel_presenthistorytoken.htm
ms.assetid: 841c1e6f-4561-4c37-a509-d9c0e9054022
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN, D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure [Display Devices], OpenGL_Structs_45310e71-a7c5-42c6-be41-e48e30203c42.xml, _D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN, display.d3dkmt_bltmodel_presenthistorytoken
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system.
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
-	d3dkmthk.h
api_name:
-	D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN
---

# _D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure


## -description


The D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure identifies a bit-block transfer (bitblt) present-history operation.


## -struct-fields




### -field hLogicalSurface

[in] A 64-bit value that specifies the handle to a logical surface to copy from. 


### -field hPhysicalSurface

[in] A 64-bit value that specifies the handle to a physical surface to copy to. 


### -field EventId

[in] A 64-bit value that identifies the bitblt event. 


### -field DirtyRegions

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff547937">D3DKMT_DIRTYREGIONS</a> structure that identifies the active rectangles (dirty regions) of the bitblt surface. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547937">D3DKMT_DIRTYREGIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548188">D3DKMT_PRESENTHISTORYTOKEN</a>
 

 

