---
UID: NC:d3dkmthk.PFND3DKMT_CHECKMONITORPOWERSTATE
title: PFND3DKMT_CHECKMONITORPOWERSTATE
author: windows-driver-content
description: The D3DKMTCheckMonitorPowerState function verifies the power state of a monitor.
old-location: display\d3dkmtcheckmonitorpowerstate.htm
old-project: display
ms.assetid: 8f218b63-304e-4f25-88d8-ea1326c613ee
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTCheckMonitorPowerState, D3DKMTCheckMonitorPowerState callback function [Display Devices], OpenGL_Functions_d05a2b63-fe81-45f0-908d-94043416b1d0.xml, PFND3DKMT_CHECKMONITORPOWERSTATE, PFND3DKMT_CHECKMONITORPOWERSTATE callback, d3dkmthk/D3DKMTCheckMonitorPowerState, display.d3dkmtcheckmonitorpowerstate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMTCheckMonitorPowerState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DKMT_CHECKMONITORPOWERSTATE callback function


## -description


The <b>D3DKMTCheckMonitorPowerState</b> function verifies the power state of a monitor.


## -parameters




### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547301">D3DKMT_CHECKMONITORPOWERSTATE</a> structure that describes the connection to the monitor for which to check the power state. 


## -returns



<b>D3DKMTCheckMonitorPowerState</b> returns one of the following values:

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
The power state of the monitor was successfully verified.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547301">D3DKMT_CHECKMONITORPOWERSTATE</a>
 

 

