---
UID: NC:d3dumddi.PFND3DDDI_SETSCISSORRECT
title: PFND3DDDI_SETSCISSORRECT
author: windows-driver-content
description: The SetScissorRect function marks a portion of a render target that rendering is confined to.
old-location: display\setscissorrect.htm
old-project: display
ms.assetid: 779fd7ff-e4d6-45b4-8164-186e9cb89513
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.setscissorrect, SetScissorRect callback function [Display Devices], SetScissorRect, PFND3DDDI_SETSCISSORRECT, PFND3DDDI_SETSCISSORRECT, d3dumddi/SetScissorRect, UserModeDisplayDriver_Functions_bd6b8a3d-d007-4272-9d43-f65c5da3959a.xml
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
-	SetScissorRect
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETSCISSORRECT callback


## -description


The <i>SetScissorRect</i> function marks a portion of a render target that rendering is confined to. 


## -prototype


````
PFND3DDDI_SETSCISSORRECT SetScissorRect;

__checkReturn HRESULT APIENTRY SetScissorRect(
  _In_       HANDLE hDevice,
  _In_ const RECT   *pRect
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pRect [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the 2-D portion of the render target to confine rendering to.


## -returns



<i>SetScissorRect</i> returns S_OK or an appropriate error result if the 2-D resource is not successfully marked.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETSCISSORRECT callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

