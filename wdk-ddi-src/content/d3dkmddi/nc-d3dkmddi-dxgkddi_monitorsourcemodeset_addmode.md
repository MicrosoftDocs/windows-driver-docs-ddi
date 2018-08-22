---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_ADDMODE
title: DXGKDDI_MONITORSOURCEMODESET_ADDMODE
author: windows-driver-content
description: The pfnAddMode function adds a monitor source mode to a specified monitor source mode set object.
old-location: display\dxgk_monitorsourcemodeset_interface_pfnaddmode.htm
ms.assetid: 88fe5a2d-d140-4ebc-846d-acea39b8bc73
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_ADDMODE, DXGKDDI_MONITORSOURCEMODESET_ADDMODE callback, VidPnFunctions_1b037d93-a615-41e1-bc22-bf9565050062.xml, d3dkmddi/pfnAddMode, display.dxgk_monitorsourcemodeset_interface_pfnaddmode, pfnAddMode, pfnAddMode callback function [Display Devices]
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
-	pfnAddMode
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_MONITORSOURCEMODESET_ADDMODE callback function


## -description


The <b>pfnAddMode</b> function adds a monitor source mode to a specified monitor source mode set object.


## -parameters




### -param hMonitorSourceModeSet [in]

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/a64197c0-a61f-4989-9b68-4e06b1a69fd4">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param pMonitorSourceModeInfo [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that describes the monitor source mode. The display miniport driver previously obtained this structure by calling <a href="https://msdn.microsoft.com/314b345c-a40b-418d-a2d8-c7b42e5fd27d">pfnCreateNewModeInfo</a>.


## -returns



The <b>pfnAddMode</b> function returns one of the following values.

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
The function failed because it could not allocate enough memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_MONITOR_SOURCE_MODE</b></dt>
</dl>
</td>
<td width="60%">
The information supplied in <i>pMonitorSourceModeInfo</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_MONITOR_SOURCEMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hMonitorSourceModeSet</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_FREQUENCY</b></dt>
</dl>
</td>
<td width="60%">
The frequency information supplied in <i>pMonitorSourceModeInfo</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_ACTIVE_REGION</b></dt>
</dl>
</td>
<td width="60%">
The active region supplied in <i>pMonitorSourceModeInfo</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_TOTAL_REGION</b></dt>
</dl>
</td>
<td width="60%">
The total region supplied in <i>pMonitorSourceModeInfo</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_MODE_ALREADY_IN_MODE_SET</b></dt>
</dl>
</td>
<td width="60%">
The mode set already contains a mode that is identical to the mode supplied in <i>pMonitorSourceModeInfo</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_MODE_ID_MUST_BE_UNIQUE</b></dt>
</dl>
</td>
<td width="60%">
The identifier supplied in pMonitorSourceModeInfo-&gt;Id is already being used for another mode in the mode set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_RESOURCES_NOT_RELATED</b></dt>
</dl>
</td>
<td width="60%">
The structure pointed to by <i>pMonitorSourceModeInfo</i> was not created for addition to the mode set specified by <i>hMonitorSourceModeSet</i>.

</td>
</tr>
</table>
 




## -remarks



If <i>pMonitorSourceModeInfo</i>-&gt;<b>Preference</b> is equal to D3DKMDT_MP_PREFERRED, the newly added mode becomes the preferred mode of the mode set.




## -see-also




<a href="https://msdn.microsoft.com/314b345c-a40b-418d-a2d8-c7b42e5fd27d">pfnCreateNewModeInfo</a>
 

 

