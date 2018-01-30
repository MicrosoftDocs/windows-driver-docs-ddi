---
UID: NC:d3dumddi.PFND3DDDI_DECODEBEGINFRAME
title: PFND3DDDI_DECODEBEGINFRAME
author: windows-driver-content
description: The DecodeBeginFrame function notifies the user-mode display driver that decoding can begin on the specified Microsoft DirectX Video Accelerator (VA) decode device.
old-location: display\decodebeginframe.htm
old-project: display
ms.assetid: 3e6153aa-7b21-429d-8908-1ff3a4d25e17
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.decodebeginframe, DecodeBeginFrame callback function [Display Devices], DecodeBeginFrame, PFND3DDDI_DECODEBEGINFRAME, PFND3DDDI_DECODEBEGINFRAME, d3dumddi/DecodeBeginFrame, UserModeDisplayDriver_Functions_3fab4933-b0fb-4a3f-8316-2c698775dda5.xml
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
-	DecodeBeginFrame
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DECODEBEGINFRAME callback


## -description


The <b>DecodeBeginFrame</b> function notifies the user-mode display driver that decoding can begin on the specified Microsoft DirectX Video Accelerator (VA) decode device.


## -prototype


````
PFND3DDDI_DECODEBEGINFRAME DecodeBeginFrame;

__checkReturn HRESULT APIENTRY DecodeBeginFrame(
  _In_ HANDLE                     hDevice,
  _In_ D3DDDIARG_DECODEBEGINFRAME *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodebeginframe.md">D3DDDIARG_DECODEBEGINFRAME</a> structure that describes information for the DirectX VA decoder to start decoding a frame.


## -returns


<b>DecodeBeginFrame</b> returns one of the following values:
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
Decoding successfully began.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table> 



## -remarks


The <b>DecodeBeginFrame</b> function notifies the user-mode display driver that its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeexecute.md">DecodeExecute</a> function can be called on the specified decode device.



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeexecute.md">DecodeExecute</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodebeginframe.md">D3DDDIARG_DECODEBEGINFRAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DECODEBEGINFRAME callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

