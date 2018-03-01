---
UID: NS:d3dumddi._DXVADDI_DECODEINPUT
title: "_DXVADDI_DECODEINPUT"
author: windows-driver-content
description: The DXVADDI_DECODEINPUT structure describes a render target format that is supported by a Microsoft DirectX Video Acceleration (DirectX VA) decode type.
old-location: display\dxvaddi_decodeinput.htm
old-project: display
ms.assetid: 6f62ce8d-058b-4838-bc7a-fae84c1b5111
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA2_Structs_9b88e486-0ea5-4fc3-bac9-1f7fcc2f5492.xml, DXVADDI_DECODEINPUT, DXVADDI_DECODEINPUT structure [Display Devices], _DXVADDI_DECODEINPUT, d3dumddi/DXVADDI_DECODEINPUT, display.dxvaddi_decodeinput
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DXVADDI_DECODEINPUT
product: Windows
targetos: Windows
req.typenames: DXVADDI_DECODEINPUT
---

# _DXVADDI_DECODEINPUT structure


## -description


The DXVADDI_DECODEINPUT structure describes a render target format that is supported by a Microsoft DirectX Video Acceleration (DirectX VA) decode type. 


## -syntax


````
typedef struct _DXVADDI_DECODEINPUT {
  const GUID        *pGuid;
  DXVADDI_VIDEODESC VideoDesc;
} DXVADDI_DECODEINPUT;
````


## -struct-fields




### -field pGuid

[in] A pointer to the GUID that represents the DirectX VA decode type.


### -field VideoDesc

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_videodesc.md">DXVADDI_VIDEODESC</a> structure for the render target that is supported by the decode type that <b>pGuid</b> points to. 


## -remarks



A pointer to the DXVADDI_DECODEINPUT structure is specified in the <b>pInfo</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> structure--along with a D3DDDICAPS_GETDECODECOMPRESSEDBUFFERINFO value in the <b>Type</b> member of D3DDDIARG_GETCAPS--in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function to retrieve information about the types of compressed buffers that are required to decode video. The compressed buffer information is returned in a pointer to a <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodebufferinfo.md">DXVADDI_DECODEBUFFERINFO</a> structure through the <b>pData</b> member of D3DDDIARG_GETCAPS.




## -see-also

<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodebufferinfo.md">DXVADDI_DECODEBUFFERINFO</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_DECODEINPUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

