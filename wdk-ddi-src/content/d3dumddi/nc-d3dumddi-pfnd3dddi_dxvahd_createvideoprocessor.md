---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR
title: PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR
author: windows-driver-content
description: The CreateVideoProcessor function creates a Microsoft DirectX Video Acceleration (DirectX VA) video processor that is used to process high-definition video.
old-location: display\createvideoprocessor.htm
old-project: display
ms.assetid: 68a7c394-4b0f-4446-a54b-5aee6cf8a913
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.createvideoprocessor, CreateVideoProcessor callback function [Display Devices], CreateVideoProcessor, PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR, PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR, d3dumddi/CreateVideoProcessor, UserModeDisplayDriver_Functions_ce6a0d51-9da3-43d9-ac23-c2e250ca4cfa.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateVideoProcessor is supported beginning with the Windows 7 operating system.
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
-	CreateVideoProcessor
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR callback


## -description


The <b>CreateVideoProcessor</b> function creates a Microsoft DirectX Video Acceleration (DirectX VA) video processor that is used to process high-definition video. 


## -prototype


````
PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR CreateVideoProcessor;

__checkReturn HRESULT APIENTRY CreateVideoProcessor(
  _In_    HANDLE                                hDevice,
  _Inout_ D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR *pData
)
{ ... }
````


## -parameters




### -param HANDLE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_createvideoprocessor.md">D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR</a> structure. On input, contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.


## -returns



<b>CreateVideoProcessor</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The video processor is successfully created. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor.md">CreateVideoProcessor</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_createvideoprocessor.md">D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_destroyvideoprocessor.md">DestroyVideoProcessor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

