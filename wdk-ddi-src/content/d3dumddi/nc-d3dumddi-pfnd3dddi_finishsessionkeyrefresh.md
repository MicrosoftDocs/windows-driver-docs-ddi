---
UID: NC:d3dumddi.PFND3DDDI_FINISHSESSIONKEYREFRESH
title: PFND3DDDI_FINISHSESSIONKEYREFRESH
author: windows-driver-content
description: The FinishSessionKeyRefresh function indicates that all buffers from that point in time use the updated session key value.
old-location: display\finishsessionkeyrefresh.htm
old-project: display
ms.assetid: e245f6f9-f4ea-429d-8421-be4fef1bf17e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.finishsessionkeyrefresh, FinishSessionKeyRefresh callback function [Display Devices], FinishSessionKeyRefresh, PFND3DDDI_FINISHSESSIONKEYREFRESH, PFND3DDDI_FINISHSESSIONKEYREFRESH, d3dumddi/FinishSessionKeyRefresh, UserModeDisplayDriver_Functions_6b7be711-8539-4b49-99d0-efbd424b33cc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: The FinishSessionKeyRefresh function is supported beginning with the Windows 7 operating system.
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
-	FinishSessionKeyRefresh
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_FINISHSESSIONKEYREFRESH callback


## -description


The <i>FinishSessionKeyRefresh</i> function indicates that all buffers from that point in time use the updated session key value. 


## -prototype


````
PFND3DDDI_FINISHSESSIONKEYREFRESH FinishSessionKeyRefresh;

__checkReturn HRESULT APIENTRY FinishSessionKeyRefresh(
  _In_       HANDLE                            hDevice,
  _In_ const D3DDDIARG_FINISHSESSIONKEYREFRESH *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_finishsessionkeyrefresh.md">D3DDDIARG_FINISHSESSIONKEYREFRESH</a> structure that describes the session. 


## -returns



<i>FinishSessionKeyRefresh</i> returns one of the following values:

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
The session is successfully updated. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>
</td>
<td width="60%">
The driver does not support the <i>FinishSessionKeyRefresh</i> function. 

</td>
</tr>
</table>
 




## -remarks



The hardware and driver can optionally support the <i>FinishSessionKeyRefresh</i> function for all crypto types.

When the Direct3D runtime calls the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_startsessionkeyrefresh.md">StartSessionKeyRefresh</a> function, the driver generates and saves a random number and returns the random number in the buffer that the <b>pRandomNumber</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_startsessionkeyrefresh.md">D3DDDIARG_STARTSESSIONKEYREFRESH</a> structure points to. 

When the runtime subsequently calls the driver's <i>FinishSessionKeyRefresh</i> function, the driver performs an XOR operation of the random number with the session key.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_startsessionkeyrefresh.md">D3DDDIARG_STARTSESSIONKEYREFRESH</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_finishsessionkeyrefresh.md">D3DDDIARG_FINISHSESSIONKEYREFRESH</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_startsessionkeyrefresh.md">StartSessionKeyRefresh</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_FINISHSESSIONKEYREFRESH callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

