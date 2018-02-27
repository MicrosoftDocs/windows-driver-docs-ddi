---
UID: NF:d3dkmthk.D3DKMTSetVidPnSourceOwner1
title: D3DKMTSetVidPnSourceOwner1 function
author: windows-driver-content
description: Sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN, and lets output duplication options be specified. Supported starting with Windows 8.
old-location: display\d3dkmtsetvidpnsourceowner1.htm
old-project: display
ms.assetid: ccee5459-f156-41c3-b9a1-8bd7d16c8d19
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMTSetVidPnSourceOwner1, D3DKMTSetVidPnSourceOwner1 callback function [Display Devices], PFND3DKMT_SETVIDPNSOURCEOWNER1, d3dkmthk/D3DKMTSetVidPnSourceOwner1, display.d3dkmtsetvidpnsourceowner1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMTSetVidPnSourceOwner1
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTSetVidPnSourceOwner1 function


## -description


Sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN, and  lets output duplication options be specified. Supported starting with Windows 8.


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTSetVidPnSourceOwner1(
  _In_ const D3DKMT_SETVIDPNSOURCEOWNER1 *pSetVidPnSourceOwner1
);
````


## -parameters




### -param D3DKMT_SETVIDPNSOURCEOWNER1

TBD




#### - pSetVidPnSourceOwner1 [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner1.md">D3DKMT_SETVIDPNSOURCEOWNER1</a> structure that describes the parameters for setting or releasing the video present source.


## -returns



Returns one of the following values:

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
The video present source was successfully set or released.

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
<dt><b>STATUS_GRAPHICS_VIDPN_SOURCE_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The video present source that is specified by an element in the array that the  <b>pVidPnSourceId</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a> specifies is already owned by a display mode manager (DMM) client and cannot be used until the client releases the video present source.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The video present source that is specified by an element in the array that the  <b>pVidPnSourceId</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a> specifies is invalid. 

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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner1.md">D3DKMT_SETVIDPNSOURCEOWNER1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_SETVIDPNSOURCEOWNER1 callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

