---
UID: NC:d3dumddi.PFND3DDDI_DESTROYOVERLAY
title: PFND3DDDI_DESTROYOVERLAY
author: windows-driver-content
description: The DestroyOverlay function disables the overlay hardware and frees the overlay handle.
old-location: display\destroyoverlay.htm
old-project: display
ms.assetid: 63004d19-e2cd-462c-8fa5-ea4dd6e29735
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroyoverlay, DestroyOverlay callback function [Display Devices], DestroyOverlay, PFND3DDDI_DESTROYOVERLAY, PFND3DDDI_DESTROYOVERLAY, d3dumddi/DestroyOverlay, UserModeDisplayDriver_Functions_e3dd8286-aff0-40c0-8cf2-84ecc706df90.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	DestroyOverlay
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYOVERLAY callback


## -description


The <b>DestroyOverlay</b> function disables the overlay hardware and frees the overlay handle.


## -prototype


````
PFND3DDDI_DESTROYOVERLAY DestroyOverlay;

__checkReturn HRESULT APIENTRY DestroyOverlay(
  _In_       HANDLE                   hDevice,
  _In_ const D3DDDIARG_DESTROYOVERLAY *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_destroyoverlay.md">D3DDDIARG_DESTROYOVERLAY</a> structure that contains the overlay handle.


## -returns



<b>DestroyOverlay</b> returns S_OK or an appropriate error result if the overlay hardware is not disabled.




## -remarks



Overlays are independent from the resources that are displayed by using the overlays.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_destroyoverlay.md">D3DDDIARG_DESTROYOVERLAY</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYOVERLAY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

