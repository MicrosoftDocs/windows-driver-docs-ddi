---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO
title: DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO
author: windows-driver-content
description: The pfnCreateNewModeInfo function returns a pointer to a D3DKMDT_MONITOR_SOURCE_MODE structure that the display miniport driver populates before calling pfnAddMode.
old-location: display\dxgk_monitorsourcemodeset_interface_pfncreatenewmodeinfo.htm
ms.assetid: 314b345c-a40b-418d-a2d8-c7b42e5fd27d
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO, DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO callback, VidPnFunctions_4b8b1581-4518-471d-a79e-ed05899ad500.xml, d3dkmddi/pfnCreateNewModeInfo, display.dxgk_monitorsourcemodeset_interface_pfncreatenewmodeinfo, pfnCreateNewModeInfo, pfnCreateNewModeInfo callback function [Display Devices]
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
-	pfnCreateNewModeInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO callback function


## -description


The <b>pfnCreateNewModeInfo</b> function returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546133">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that the display miniport driver populates before calling <a href="https://msdn.microsoft.com/88fe5a2d-d140-4ebc-846d-acea39b8bc73">pfnAddMode</a>.


## -parameters




### -param hMonitorSourceModeSet [in]

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/a64197c0-a61f-4989-9b68-4e06b1a69fd4">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param ppNewMonitorSourceModeInfo [out]

[out] A pointer to a variable that receives a pointer to a newly created D3DKMDT_MONITOR_SOURCE_MODE structure allocated by the VidPN manager.


## -returns



The <b>pfnCreateNewModeInfo</b> function returns one of the following values.

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
 




## -remarks



After you call <b>pfnCreateNewModeInfo</b> to obtain a D3DKMDT_MONITOR SOURCE_MODE structure, you must do one, but not both, of the following:

<ul>
<li>
Populate the structure and pass it to <a href="https://msdn.microsoft.com/88fe5a2d-d140-4ebc-846d-acea39b8bc73">pfnAddMode</a>.

</li>
<li>
Release the structure by calling <a href="https://msdn.microsoft.com/2c82ec09-e858-4efc-a1c0-a3792e0b5ddf">pfnReleaseModeInfo</a>.

</li>
</ul>


