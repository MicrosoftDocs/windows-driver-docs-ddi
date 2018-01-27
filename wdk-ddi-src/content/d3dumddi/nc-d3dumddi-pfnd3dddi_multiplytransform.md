---
UID: NC:d3dumddi.PFND3DDDI_MULTIPLYTRANSFORM
title: PFND3DDDI_MULTIPLYTRANSFORM
author: windows-driver-content
description: The MultiplyTransform function modifies the current transform.
old-location: display\multiplytransform.htm
old-project: display
ms.assetid: 69d94062-5655-4d49-a116-7fa7e2b51a91
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.multiplytransform, MultiplyTransform callback function [Display Devices], MultiplyTransform, PFND3DDDI_MULTIPLYTRANSFORM, PFND3DDDI_MULTIPLYTRANSFORM, d3dumddi/MultiplyTransform, UserModeDisplayDriver_Functions_4058eef2-8ccd-46e2-ad8d-fd0905811651.xml
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
-	MultiplyTransform
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_MULTIPLYTRANSFORM callback


## -description


The <i>MultiplyTransform</i> function modifies the current transform.


## -prototype


````
PFND3DDDI_MULTIPLYTRANSFORM MultiplyTransform;

__checkReturn HRESULT APIENTRY MultiplyTransform(
  _In_       HANDLE                      hDevice,
  _In_ const D3DDDIARG_MULTIPLYTRANSFORM *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_multiplytransform.md">D3DDDIARG_MULTIPLYTRANSFORM</a> structure that describes how to modify the current transform.


## -returns


<i>MultiplyTransform</i> returns S_OK or an appropriate error result if the transform is not successfully modified.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_multiplytransform.md">D3DDDIARG_MULTIPLYTRANSFORM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_MULTIPLYTRANSFORM callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

