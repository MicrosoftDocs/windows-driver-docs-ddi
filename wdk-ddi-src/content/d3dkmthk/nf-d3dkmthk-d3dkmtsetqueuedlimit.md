---
UID: NF:d3dkmthk.D3DKMTSetQueuedLimit
title: D3DKMTSetQueuedLimit function
author: windows-driver-content
description: The D3DKMTSetQueuedLimit function sets or retrieves the limit for the number of operations of the given type that can be queued for the given device.
old-location: display\d3dkmtsetqueuedlimit.htm
old-project: display
ms.assetid: 184473e4-603f-40a0-a4ea-c15d5b0b0b35
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMTSetQueuedLimit, D3DKMTSetQueuedLimit function [Display Devices], D3DKMTSetQueuedLimit, OpenGL_Functions_22227369-eb8b-4ee0-a3d8-97eb0f469d94.xml, display.d3dkmtsetqueuedlimit
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
-	D3DKMTSetQueuedLimit
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTSetQueuedLimit function


## -description


The <b>D3DKMTSetQueuedLimit</b> function sets or retrieves the limit for the number of operations of the given type that can be queued for the given device.


## -syntax


````
NTSTATUS APIENTRY D3DKMTSetQueuedLimit(
  _In_ const D3DKMT_SETQUEUEDLIMIT *pData
);
````


## -parameters




### -param D3DKMT_SETQUEUEDLIMIT

TBD



#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setqueuedlimit.md">D3DKMT_SETQUEUEDLIMIT</a> structure that describes parameters for setting or retrieving the limit of queued operations.


## -returns


<b>D3DKMTSetQueuedLimit</b> returns one of the following values:
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
The limit of queued operations was successfully set or retrieved.

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

<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_queuedlimit_type.md">D3DKMT_QUEUEDLIMIT_TYPE</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setqueuedlimit.md">D3DKMT_SETQUEUEDLIMIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSetQueuedLimit function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

