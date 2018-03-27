---
UID: NC:d3dkmddi.DXGKDDI_GETSCANLINE
title: DXGKDDI_GETSCANLINE
author: windows-driver-content
description: The DxgkDdiGetScanLine function determines whether the specified video present target of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.
old-location: display\dxgkddigetscanline.htm
old-project: display
ms.assetid: e37bb3c6-a0b6-409f-8a82-20ec7a931c6a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_GETSCANLINE, DmFunctions_135e90a4-1b44-4cd6-92fe-626dd389af9b.xml, DxgkDdiGetScanLine, DxgkDdiGetScanLine callback function [Display Devices], d3dkmddi/DxgkDdiGetScanLine, display.dxgkddigetscanline
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiGetScanLine
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_GETSCANLINE callback


## -description


The <i>DxgkDdiGetScanLine</i> function determines whether the specified video present target of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pGetScanLine [in, out]

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557594">DXGKARG_GETSCANLINE</a> structure that contains the vertical blanking status of a video present target.


## -returns



<i>DxgkDdiGetScanLine</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



<i>DxgkDdiGetScanLine</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557594">DXGKARG_GETSCANLINE</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_GETSCANLINE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

