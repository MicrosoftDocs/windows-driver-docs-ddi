---
UID: NC:d3dumddi.PFND3DDDI_GETCAPTUREALLOCATIONHANDLE
title: PFND3DDDI_GETCAPTUREALLOCATIONHANDLE
author: windows-driver-content
description: The GetCaptureAllocationHandle function maps the given capture resource handle to a kernel-mode allocation handle.
old-location: display\getcaptureallocationhandle.htm
old-project: display
ms.assetid: fb12a12b-6fb7-46d4-aa71-4c88d34d6ff9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: GetCaptureAllocationHandle, GetCaptureAllocationHandle callback function [Display Devices], PFND3DDDI_GETCAPTUREALLOCATIONHANDLE, UserModeDisplayDriver_Functions_839ce10f-1df9-4d62-a877-d64215b82370.xml, d3dumddi/GetCaptureAllocationHandle, display.getcaptureallocationhandle
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
-	GetCaptureAllocationHandle
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_GETCAPTUREALLOCATIONHANDLE callback


## -description


The <i>GetCaptureAllocationHandle</i> function maps the given capture resource handle to a kernel-mode allocation handle.


## -prototype


````
PFND3DDDI_GETCAPTUREALLOCATIONHANDLE GetCaptureAllocationHandle;

__checkReturn HRESULT APIENTRY GetCaptureAllocationHandle(
  _In_    HANDLE                               hDevice,
  _Inout_ D3DDDIARG_GETCAPTUREALLOCATIONHANDLE *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaptureallocationhandle.md">D3DDDIARG_GETCAPTUREALLOCATIONHANDLE</a> structure that describes parameters for retrieving an allocation handle from a capture resource handle.


## -returns



<i>GetCaptureAllocationHandle</i> returns one of the following values:

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
The given resource is in GPU-accessible memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>GetCaptureAllocationHandle</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaptureallocationhandle.md">D3DDDIARG_GETCAPTUREALLOCATIONHANDLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_GETCAPTUREALLOCATIONHANDLE callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

