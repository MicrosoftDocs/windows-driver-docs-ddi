---
UID: NC:d3d10umddi.PFND3D10DDI_GENMIPS
title: PFND3D10DDI_GENMIPS
author: windows-driver-content
description: The GenMips function generates the lower MIP-map levels on the specified shader-resource view.
old-location: display\genmips.htm
old-project: display
ms.assetid: abd045f2-9c05-4579-8d80-aba31523157d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.genmips, GenMips callback function [Display Devices], GenMips, PFND3D10DDI_GENMIPS, PFND3D10DDI_GENMIPS, d3d10umddi/GenMips, UserModeDisplayDriverDx10_Functions_56ecca1c-6b70-4ed8-9831-aec5fa5416cf.xml
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
-	GenMips
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---

# PFND3D10DDI_GENMIPS callback


## -description


The <i>GenMips</i> function generates the lower MIP-map levels on the specified shader-resource view. 


## -prototype


````
PFND3D10DDI_GENMIPS GenMips;

VOID APIENTRY GenMips(
  _In_ D3D10DDI_HDEVICE             hDevice,
  _In_ D3D10DDI_HSHADERRESOURCEVIEW hShaderResourceView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D10DDI_HSHADERRESOURCEVIEW






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hShaderResourceView [in]

 A handle to the MIP-map texture surface.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. The driver can set E_FAIL if the base resource was not created with the appropriate flags or can set E_INVALIDARG if the MIP type was incorrectly specified.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_GENMIPS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

