---
UID: NC:d3dumddi.PFND3DDDI_FLIPOVERLAY
title: PFND3DDDI_FLIPOVERLAY
author: windows-driver-content
description: The FlipOverlay function causes the overlay hardware to start displaying the given new allocation.
old-location: display\flipoverlay.htm
old-project: display
ms.assetid: 8490ebdd-f993-4c77-b6da-d57ef5e5d05f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: FlipOverlay, FlipOverlay callback function [Display Devices], PFND3DDDI_FLIPOVERLAY, UserModeDisplayDriver_Functions_4a2c5f7b-8d52-465f-84ea-a1fc4f53381b.xml, d3dumddi/FlipOverlay, display.flipoverlay
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
-	FlipOverlay
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_FLIPOVERLAY callback


## -description


The <i>FlipOverlay</i> function causes the overlay hardware to start displaying the given new allocation.


## -prototype


````
PFND3DDDI_FLIPOVERLAY FlipOverlay;

__checkReturn HRESULT APIENTRY FlipOverlay(
  _In_       HANDLE                hDevice,
  _In_ const D3DDDIARG_FLIPOVERLAY *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_flipoverlay.md">D3DDDIARG_FLIPOVERLAY</a> structure that describes the new allocation to display by using the overlay.


## -returns



<i>FlipOverlay</i> returns S_OK or an appropriate error result if the new allocation is not successfully displayed.




## -remarks



Overlays are independent from the resources that are displayed by using the overlays.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_flipoverlay.md">D3DDDIARG_FLIPOVERLAY</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_FLIPOVERLAY callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

