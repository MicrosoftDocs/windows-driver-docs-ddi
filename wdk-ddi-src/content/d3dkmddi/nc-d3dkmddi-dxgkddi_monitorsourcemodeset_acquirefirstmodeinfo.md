---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO
title: DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO
author: windows-driver-content
description: The pfnAcquireFirstModeInfo function returns a descriptor of the first mode in a specified monitor source mode set.
old-location: display\dxgk_monitorsourcemodeset_interface_pfnacquirefirstmodeinfo.htm
old-project: display
ms.assetid: d448c3f4-7adb-4ceb-8c42-8cba3d2cfeae
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO, DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO callback, VidPnFunctions_81493c6c-3b78-4c4b-969c-276a459a198d.xml, d3dkmddi/pfnAcquireFirstModeInfo, display.dxgk_monitorsourcemodeset_interface_pfnacquirefirstmodeinfo, pfnAcquireFirstModeInfo, pfnAcquireFirstModeInfo callback function [Display Devices]
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
-	pfnAcquireFirstModeInfo
product: Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO callback function


## -description


The <b>pfnAcquireFirstModeInfo</b> function returns a descriptor of the first mode in a specified monitor source mode set.


## -parameters




### -param hMonitorSourceModeSet [in]

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/a64197c0-a61f-4989-9b68-4e06b1a69fd4">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param ppFirstMonitorSourceModeInfo [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a> structure. The structure contains a variety of information about the monitor source mode, including its ID and video signal characteristics.


## -returns



The <b>pfnAcquireFirstModeInfo</b> function returns one of the following values:

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



When you have finished using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a> structure, you must release the structure by calling <a href="https://msdn.microsoft.com/2c82ec09-e858-4efc-a1c0-a3792e0b5ddf">pfnReleaseModeInfo</a>.

You can enumerate all the modes that belong to a VidPN monitor source mode set object by calling <b>pfnAcquireFirstModeInfo</b> and then making a sequence of calls to <a href="https://msdn.microsoft.com/55c629c5-1d73-40dd-a5aa-73ddcc5236b5">pfnAcquireNextModeInfo</a>.

The D3DKMDT_HMONITORSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/55c629c5-1d73-40dd-a5aa-73ddcc5236b5">pfnAcquireNextModeInfo</a>



<a href="https://msdn.microsoft.com/2c82ec09-e858-4efc-a1c0-a3792e0b5ddf">pfnReleaseModeInfo</a>
 

 

