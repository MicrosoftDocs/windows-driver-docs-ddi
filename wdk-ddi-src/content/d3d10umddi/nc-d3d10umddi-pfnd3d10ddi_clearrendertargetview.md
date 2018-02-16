---
UID: NC:d3d10umddi.PFND3D10DDI_CLEARRENDERTARGETVIEW
title: PFND3D10DDI_CLEARRENDERTARGETVIEW
author: windows-driver-content
description: The ClearRenderTargetView function clears the specified render-target view by setting it to a constant value.
old-location: display\clearrendertargetview.htm
old-project: display
ms.assetid: 9dc95dd2-01ad-45d7-9e75-049026b25968
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.clearrendertargetview, ClearRenderTargetView callback function [Display Devices], ClearRenderTargetView, PFND3D10DDI_CLEARRENDERTARGETVIEW, PFND3D10DDI_CLEARRENDERTARGETVIEW, d3d10umddi/ClearRenderTargetView, UserModeDisplayDriverDx10_Functions_b9129a55-a400-45b7-a3a9-da477170c99c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
apiname:
-	ClearRenderTargetView
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_CLEARRENDERTARGETVIEW callback


## -description


The <b>ClearRenderTargetView</b> function clears the specified render-target view by setting it to a constant value. 


## -prototype


````
PFND3D10DDI_CLEARRENDERTARGETVIEW ClearRenderTargetView;

VOID APIENTRY ClearRenderTargetView(
  _In_ D3D10DDI_HDEVICE           hDevice,
  _In_ D3D10DDI_HRENDERTARGETVIEW hRenderTargetView,
  _In_ FLOAT                      pColorRGBA
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D10DDI_HRENDERTARGETVIEW


### -param FLOAT[4]








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRenderTargetView [in]

 A handle to the render-target view to clear. 


#### - pColorRGBA [in]

 A four-element array of single-precision float vectors that the driver uses to clear a render-target view. Array element 0 is red (R), 1 is green (G), 2 is blue (B), and 3 is alpha (A).


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>ClearRenderTargetView</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CLEARRENDERTARGETVIEW callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

