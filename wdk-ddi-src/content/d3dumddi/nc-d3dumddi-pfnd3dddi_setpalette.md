---
UID: NC:d3dumddi.PFND3DDDI_SETPALETTE
title: PFND3DDDI_SETPALETTE
author: windows-driver-content
description: The SetPalette function associates a palette with a texture.
old-location: display\setpalette.htm
old-project: display
ms.assetid: 5d1c8c2d-7886-4876-b48e-1e6b252ae8f7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETPALETTE, SetPalette, SetPalette callback function [Display Devices], UserModeDisplayDriver_Functions_9366fa90-a9d7-4c03-9c96-a8bc4eba6abb.xml, d3dumddi/SetPalette, display.setpalette
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	SetPalette
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETPALETTE callback


## -description


The <i>SetPalette</i> function associates a palette with a texture.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543327">D3DDDIARG_SETPALETTE</a> structure that describes the parameters for the set-palette operation.


## -returns



<i>SetPalette</i> returns S_OK or an appropriate error result if the palette is not successfully associated with the texture.




## -remarks



The user-mode display driver uses the members in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543327">D3DDDIARG_SETPALETTE</a> structure that is pointed to by <i>pData</i> to map an association between a palette handle and a surface handle and to specify the characteristics of the palette.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543327">D3DDDIARG_SETPALETTE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETPALETTE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

