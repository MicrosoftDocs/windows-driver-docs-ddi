---
UID: NC:d3dumddi.PFND3DDDI_FINISHSESSIONKEYREFRESH
title: PFND3DDDI_FINISHSESSIONKEYREFRESH
author: windows-driver-content
description: The FinishSessionKeyRefresh function indicates that all buffers from that point in time use the updated session key value.
old-location: display\finishsessionkeyrefresh.htm
old-project: display
ms.assetid: e245f6f9-f4ea-429d-8421-be4fef1bf17e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FinishSessionKeyRefresh, FinishSessionKeyRefresh callback function [Display Devices], PFND3DDDI_FINISHSESSIONKEYREFRESH, PFND3DDDI_FINISHSESSIONKEYREFRESH callback, UserModeDisplayDriver_Functions_6b7be711-8539-4b49-99d0-efbd424b33cc.xml, d3dumddi/FinishSessionKeyRefresh, display.finishsessionkeyrefresh
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	FinishSessionKeyRefresh
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_FINISHSESSIONKEYREFRESH callback function


## -description


The <i>FinishSessionKeyRefresh</i> function indicates that all buffers from that point in time use the updated session key value. 


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543120">D3DDDIARG_FINISHSESSIONKEYREFRESH</a> structure that describes the session. 


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

When the Direct3D runtime calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451696">StartSessionKeyRefresh</a> function, the driver generates and saves a random number and returns the random number in the buffer that the <b>pRandomNumber</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543375">D3DDDIARG_STARTSESSIONKEYREFRESH</a> structure points to. 

When the runtime subsequently calls the driver's <i>FinishSessionKeyRefresh</i> function, the driver performs an XOR operation of the random number with the session key.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543120">D3DDDIARG_FINISHSESSIONKEYREFRESH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543375">D3DDDIARG_STARTSESSIONKEYREFRESH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451696">StartSessionKeyRefresh</a>
 

 

