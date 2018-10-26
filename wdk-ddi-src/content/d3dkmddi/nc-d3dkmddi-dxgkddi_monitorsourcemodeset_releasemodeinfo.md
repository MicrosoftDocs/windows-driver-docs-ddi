---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO
title: DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO
author: windows-driver-content
description: The pfnReleaseModeInfo function releases a D3DKMDT_MONITOR_SOURCE_MODE structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_monitorsourcemodeset_interface_pfnreleasemodeinfo.htm
ms.assetid: 2c82ec09-e858-4efc-a1c0-a3792e0b5ddf
ms.date: 05/10/2018
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO, DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO callback, VidPnFunctions_215a7f94-e7f6-46a9-9f12-ba7d306c6c18.xml, d3dkmddi/pfnReleaseModeInfo, display.dxgk_monitorsourcemodeset_interface_pfnreleasemodeinfo, pfnReleaseModeInfo, pfnReleaseModeInfo callback function [Display Devices]
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
-	pfnReleaseModeInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO callback function


## -description


The <b>pfnReleaseModeInfo</b> function releases a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that the VidPN manager previously provided to the display miniport driver.


## -parameters




### -param hMonitorSourceModeSet [in]

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/a64197c0-a61f-4989-9b68-4e06b1a69fd4">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param pMonitorSourceModeInfo [in]

[in] A pointer to the D3DKMDT_MONITOR_SOURCE_MODE structure that is to be released.


## -returns



The <b>pfnReleaseModeInfo</b> function returns one of the following values:

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET_MODE</b></dt>
</dl>
</td>
<td width="60%">
The pointer supplied in <i>pMonitorSourceModeInfo</i> was invalid.

</td>
</tr>
</table>
 




## -remarks



When you have finished using a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that you obtained by calling <a href="https://msdn.microsoft.com/d448c3f4-7adb-4ceb-8c42-8cba3d2cfeae">pfnAcquireFirstModeInfo</a> or <a href="https://msdn.microsoft.com/55c629c5-1d73-40dd-a5aa-73ddcc5236b5">pfnAcquireNextModeInfo</a>, you must release the structure by calling <b>pfnReleaseModeInfo</b>.

The D3DKMDT_HMONITORSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/d448c3f4-7adb-4ceb-8c42-8cba3d2cfeae">pfnAcquireFirstModeInfo</a>



<a href="https://msdn.microsoft.com/55c629c5-1d73-40dd-a5aa-73ddcc5236b5">pfnAcquireNextModeInfo</a>
 

 

