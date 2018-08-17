---
UID: NC:d3dkmddi.DXGKDDI_RECOMMENDMONITORMODES
title: DXGKDDI_RECOMMENDMONITORMODES
author: windows-driver-content
description: The DxgkDdiRecommendMonitorModes function inspects the monitor source mode set that is associated with a particular video present target and possibly adds modes to the set.
old-location: display\dxgkddirecommendmonitormodes.htm
ms.assetid: 1fa29ab6-1faa-4be6-ae87-4cac9057471d
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGKDDI_RECOMMENDMONITORMODES, DXGKDDI_RECOMMENDMONITORMODES callback, DmFunctions_0e8f1382-ec41-4953-8e1e-f2a5121acc0c.xml, DxgkDdiRecommendMonitorModes, DxgkDdiRecommendMonitorModes callback function [Display Devices], d3dkmddi/DxgkDdiRecommendMonitorModes, display.dxgkddirecommendmonitormodes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiRecommendMonitorModes
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_RECOMMENDMONITORMODES callback function


## -description


The <i>DxgkDdiRecommendMonitorModes</i> function inspects the monitor source mode set that is associated with a particular video present target and possibly adds modes to the set.


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pRecommendMonitorModes








#### - pRecommendMonitorModesArg [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557636">DXGKARG_RECOMMENDMONITORMODES</a> structure that contains function arguments.


## -returns



<i>DxgkDdiRecommendMonitorModes</i> returns one of the following values:

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
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The function failed because it was unable to allocate enough memory.

</td>
</tr>
</table>
 

The miniport driver should pass through any error code that it gets from the operating system for which it does not have a fallback code path.




## -remarks



<i>DxgkDdiRecommendMonitorModes</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568435">Monitor Source Mode Set Interface</a>
 

 

