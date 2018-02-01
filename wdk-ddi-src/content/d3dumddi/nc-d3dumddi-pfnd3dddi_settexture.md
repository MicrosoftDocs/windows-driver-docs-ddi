---
UID: NC:d3dumddi.PFND3DDDI_SETTEXTURE
title: PFND3DDDI_SETTEXTURE
author: windows-driver-content
description: The SetTexture function inserts a texture at a particular stage in a multiple-texture group.
old-location: display\settexture.htm
old-project: display
ms.assetid: b2ed86c5-cd4f-4aaa-a062-4c7ae4e088df
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.settexture, SetTexture callback function [Display Devices], SetTexture, PFND3DDDI_SETTEXTURE, PFND3DDDI_SETTEXTURE, d3dumddi/SetTexture, UserModeDisplayDriver_Functions_f85a8797-cbcc-40df-a339-af69ce128e95.xml
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
-	SetTexture
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETTEXTURE callback


## -description


The <i>SetTexture</i> function inserts a texture at a particular stage in a multiple-texture group.


## -prototype


````
PFND3DDDI_SETTEXTURE SetTexture;

__checkReturn HRESULT APIENTRY SetTexture(
  _In_ HANDLE hDevice,
  _In_ UINT   Stage,
  _In_ HANDLE hTexture
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param UINT



### -param HANDLE






#### - Stage [in]

 The stage in a multiple-texture group that indicates where to insert the texture that is specified by the <i>hTexture</i> handle. This parameter can be an integer in the range from 0 through 7, with the highest-numbered texture being closest to the frame buffer.


#### - hTexture [in]

 A handle to the texture to insert.


## -returns


<i>SetTexture</i> returns S_OK or an appropriate error result if the texture is not successfully inserted.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETTEXTURE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

