---
UID: NF:d3dkmthk.D3DKMTGetDeviceState
title: D3DKMTGetDeviceState function
author: windows-driver-content
description: The D3DKMTGetDeviceState function retrieves the state of a device.
old-location: display\d3dkmtgetdevicestate.htm
ms.assetid: 8ea84934-63a7-40bf-8523-ccd2b9e5aceb
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTGetDeviceState, D3DKMTGetDeviceState function [Display Devices], OpenGL_Functions_396da637-bbc6-478c-8ec9-534d82691c45.xml, d3dkmthk/D3DKMTGetDeviceState, display.d3dkmtgetdevicestate
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTGetDeviceState
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTGetDeviceState function


## -description


The <b>D3DKMTGetDeviceState</b> function retrieves the state of a device.


## -parameters




### -param Arg1






#### - pData [in, out]

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548030">D3DKMT_GETDEVICESTATE</a> structure that describes parameters for retrieving the state of a device.


## -returns



<b>D3DKMTGetDeviceState</b> returns one of the following values:

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
The state of the device was successfully retrieved.

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
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548030">D3DKMT_GETDEVICESTATE</a>
 

 

