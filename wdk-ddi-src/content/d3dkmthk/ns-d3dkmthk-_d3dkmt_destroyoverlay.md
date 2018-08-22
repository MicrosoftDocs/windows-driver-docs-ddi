---
UID: NS:d3dkmthk._D3DKMT_DESTROYOVERLAY
title: "_D3DKMT_DESTROYOVERLAY"
author: windows-driver-content
description: The D3DKMT_DESTROYOVERLAY structure contains the handle to the overlay to destroy.
old-location: display\d3dkmt_destroyoverlay.htm
ms.assetid: b1b8554f-8d6b-4c2e-b6b8-fcbfc97f5dd9
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMT_DESTROYOVERLAY, D3DKMT_DESTROYOVERLAY structure [Display Devices], OpenGL_Structs_57b46d39-5b2c-4d58-9daa-e1460168fe55.xml, _D3DKMT_DESTROYOVERLAY, d3dkmthk/D3DKMT_DESTROYOVERLAY, display.d3dkmt_destroyoverlay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_DESTROYOVERLAY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DESTROYOVERLAY
---

# _D3DKMT_DESTROYOVERLAY structure


## -description


The D3DKMT_DESTROYOVERLAY structure contains the handle to the overlay to destroy.


## -struct-fields




### -field hDevice

[in] A handle to the device that the overlay is associated with.


### -field hOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the create-overlay function and that identifies the kernel-mode overlay object to destroy. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546925">D3DKMTDestroyOverlay</a>
 

 

