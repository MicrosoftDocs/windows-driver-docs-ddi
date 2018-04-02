---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES
title: DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES
author: windows-driver-content
description: The pfnGetNumModes function returns the number modes in a specified monitor source mode set.
old-location: display\dxgk_monitorsourcemodeset_interface_pfngetnummodes.htm
old-project: display
ms.assetid: 58daf5be-45c5-493b-9d51-ef48bb123dce
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES, VidPnFunctions_ac29494d-c35e-46bb-bfc1-6aaf70edbc2d.xml, d3dkmddi/pfnGetNumModes, display.dxgk_monitorsourcemodeset_interface_pfngetnummodes, pfnGetNumModes, pfnGetNumModes callback function [Display Devices]
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnGetNumModes
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES callback


## -description


The <b>pfnGetNumModes</b> function returns the number modes in a specified monitor source mode set.


## -parameters




### -param hMonitorSourceModeSet [in]

A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/a64197c0-a61f-4989-9b68-4e06b1a69fd4">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param pNumMonitorSourceModes [out]

A pointer to a SIZE_T-typed variable that receives the number of monitor source modes in the set.


## -returns



The <b>pfnGetNumModes</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_MONITOR_SOURCEMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hMonitorSourceModeSet </i>was invalid.

</td>
</tr>
</table>
 




## -remarks



The D3DKMDT_HMONITORSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/d448c3f4-7adb-4ceb-8c42-8cba3d2cfeae">pfnAcquireFirstModeInfo</a>



<a href="https://msdn.microsoft.com/55c629c5-1d73-40dd-a5aa-73ddcc5236b5">pfnAcquireNextModeInfo</a>
 

 

