---
UID: NC:d3dumddi.PFND3DDDI_STARTSESSIONKEYREFRESH
title: PFND3DDDI_STARTSESSIONKEYREFRESH
author: windows-driver-content
description: The StartSessionKeyRefresh function returns a random number that the driver's FinishSessionKeyRefresh function subsequently uses to perform an exclusive OR operation (XOR) with the session key.
old-location: display\startsessionkeyrefresh.htm
old-project: display
ms.assetid: 986d8f46-3b4f-41b2-938e-4f3adbfe057a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3DDDI_STARTSESSIONKEYREFRESH, PFND3DDDI_STARTSESSIONKEYREFRESH callback, StartSessionKeyRefresh, StartSessionKeyRefresh callback function [Display Devices], UserModeDisplayDriver_Functions_c68a1081-f350-4439-8c1c-91d9c54469bd.xml, d3dumddi/StartSessionKeyRefresh, display.startsessionkeyrefresh
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: StartSessionKeyRefresh is supported beginning with the Windows 7 operating system.
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
-	StartSessionKeyRefresh
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_STARTSESSIONKEYREFRESH callback function


## -description


The <i>StartSessionKeyRefresh</i> function returns a random number that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451648">FinishSessionKeyRefresh</a> function subsequently uses to perform an exclusive OR operation (XOR) with the session key. 


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543375">D3DDDIARG_STARTSESSIONKEYREFRESH</a> structure that contains information about the random number. 


## -returns



<i>StartSessionKeyRefresh</i> returns one of the following values:

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
The random number is successfully returned. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>
</td>
<td width="60%">
The driver does not support the <i>StartSessionKeyRefresh</i> function. 

</td>
</tr>
</table>
 




## -remarks



The hardware and driver can optionally support <i>StartSessionKeyRefresh</i> for all crypto types.  

When the Direct3D runtime calls the driver's <i>StartSessionKeyRefresh</i> function, the driver generates and saves a random number and returns the random number in the buffer that the <b>pRandomNumber</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543375">D3DDDIARG_STARTSESSIONKEYREFRESH</a> structure points to.

When the runtime subsequently calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451648">FinishSessionKeyRefresh</a> function, the driver performs an XOR operation of the random number with the session key.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543375">D3DDDIARG_STARTSESSIONKEYREFRESH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451648">FinishSessionKeyRefresh</a>
 

 

