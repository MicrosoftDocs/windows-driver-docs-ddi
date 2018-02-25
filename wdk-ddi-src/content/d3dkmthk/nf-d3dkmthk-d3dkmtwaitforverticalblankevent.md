---
UID: NF:d3dkmthk.D3DKMTWaitForVerticalBlankEvent
title: D3DKMTWaitForVerticalBlankEvent function
author: windows-driver-content
description: The D3DKMTWaitForVerticalBlankEvent function waits for the vertical blanking interval to occur and then returns.
old-location: display\d3dkmtwaitforverticalblankevent.htm
old-project: display
ms.assetid: aa40633e-1881-4bf4-a57b-f7ee3ce23438
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , 3, B, D, D3DKMTWaitForVerticalBlankEvent, D3DKMTWaitForVerticalBlankEvent function [Display Devices], E, F, K, M, OpenGL_Functions_9e2c6684-7429-43d7-b43a-0f11aea6807f.xml, T, V, W, a, c, d3dkmthk/D3DKMTWaitForVerticalBlankEvent, display.d3dkmtwaitforverticalblankevent, e, i, k, l, n, o, r, t, v"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTWaitForVerticalBlankEvent
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTWaitForVerticalBlankEvent function


## -description


The <b>D3DKMTWaitForVerticalBlankEvent</b> function waits for the vertical blanking interval to occur and then returns.


## -syntax


````
NTSTATUS APIENTRY D3DKMTWaitForVerticalBlankEvent(
  _In_ const D3DKMT_WAITFORVERTICALBLANKEVENT *pData
);
````


## -parameters




### -param D3DKMT_WAITFORVERTICALBLANKEVENT

TBD




#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_waitforverticalblankevent.md">D3DKMT_WAITFORVERTICALBLANKEVENT</a> structure that describes parameters for waiting for the vertical blank to occur.


## -returns



<b>D3DKMTWaitForVerticalBlankEvent</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The vertical blanking interval successfully occurred.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_waitforverticalblankevent.md">D3DKMT_WAITFORVERTICALBLANKEVENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTWaitForVerticalBlankEvent function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

