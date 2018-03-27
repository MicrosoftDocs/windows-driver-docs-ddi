---
UID: NS:d3dkmddi._DXGKARG_CREATEOVERLAY
title: "_DXGKARG_CREATEOVERLAY"
author: windows-driver-content
description: The DXGKARG_CREATEOVERLAY structure describes parameters to create an overlay.
old-location: display\dxgkarg_createoverlay.htm
old-project: display
ms.assetid: f95ef083-2b2f-4e13-ad60-6bc7da0fec33
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*INOUT_PDXGKARG_CREATEOVERLAY, DXGKARG_CREATEOVERLAY, DXGKARG_CREATEOVERLAY structure [Display Devices], DmStructs_935ab2cb-070a-4700-8ace-62c4c44c42b5.xml, _DXGKARG_CREATEOVERLAY, d3dkmddi/DXGKARG_CREATEOVERLAY, display.dxgkarg_createoverlay"
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_CREATEOVERLAY
product: Windows
targetos: Windows
req.typenames: DXGKARG_CREATEOVERLAY
---

# _DXGKARG_CREATEOVERLAY structure


## -description


The DXGKARG_CREATEOVERLAY structure describes parameters to create an overlay.


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the overlay is displayed on. 


### -field OverlayInfo

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561988">DXGK_OVERLAYINFO</a> structure that contains parameters that are required to create the overlay.


### -field hOverlay

[out] A handle to the newly created overlay.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561988">DXGK_OVERLAYINFO</a>



<a href="https://msdn.microsoft.com/1ccdd16d-fd76-4039-b538-86c77b4e8cbb">DxgkDdiCreateOverlay</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_CREATEOVERLAY structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

