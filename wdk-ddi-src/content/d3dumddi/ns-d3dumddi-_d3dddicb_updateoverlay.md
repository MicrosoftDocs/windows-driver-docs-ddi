---
UID: NS:d3dumddi._D3DDDICB_UPDATEOVERLAY
title: "_D3DDDICB_UPDATEOVERLAY"
author: windows-driver-content
description: The D3DDDICB_UPDATEOVERLAY structure describes parameters for modifying an overlay.
old-location: display\d3dddicb_updateoverlay.htm
old-project: display
ms.assetid: efa54d23-99bc-49ea-b8a3-7ea5b00e36d8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_UPDATEOVERLAY, D3DDDICB_UPDATEOVERLAY structure [Display Devices], D3D_param_Structs_b9e39db9-44ba-45d5-9500-dd9d5d8cc4bb.xml, _D3DDDICB_UPDATEOVERLAY, d3dumddi/D3DDDICB_UPDATEOVERLAY, display.d3dddicb_updateoverlay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDICB_UPDATEOVERLAY
product: Windows
targetos: Windows
req.typenames: D3DDDICB_UPDATEOVERLAY
---

# _D3DDDICB_UPDATEOVERLAY structure


## -description


The D3DDDICB_UPDATEOVERLAY structure describes parameters for modifying an overlay.


## -struct-fields




### -field hKernelOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the <a href="https://msdn.microsoft.com/fbd5b3af-0963-4e41-8be3-41e3e1ecf8bc">pfnCreateOverlayCb</a> function and that identifies the kernel-mode overlay object to modify. 


### -field OverlayInfo

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544577">D3DDDI_KERNELOVERLAYINFO</a> structure that describes modification information for the kernel-mode overlay object. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544577">D3DDDI_KERNELOVERLAYINFO</a>



<a href="https://msdn.microsoft.com/fbd5b3af-0963-4e41-8be3-41e3e1ecf8bc">pfnCreateOverlayCb</a>



<a href="https://msdn.microsoft.com/17f89cea-350c-43f6-a60d-32fc2d299dd7">pfnUpdateOverlayCb</a>
 

 

