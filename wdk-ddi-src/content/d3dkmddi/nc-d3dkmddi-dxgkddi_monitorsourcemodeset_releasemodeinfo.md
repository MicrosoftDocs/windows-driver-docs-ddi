---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO
title: DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO
author: windows-driver-content
description: The pfnReleaseModeInfo function releases a D3DKMDT_MONITOR_SOURCE_MODE structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_monitorsourcemodeset_interface_pfnreleasemodeinfo.htm
old-project: display
ms.assetid: 2c82ec09-e858-4efc-a1c0-a3792e0b5ddf
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_monitorsourcemodeset_interface_pfnreleasemodeinfo, pfnReleaseModeInfo callback function [Display Devices], pfnReleaseModeInfo, DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO, DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO, d3dkmddi/pfnReleaseModeInfo, VidPnFunctions_215a7f94-e7f6-46a9-9f12-ba7d306c6c18.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	pfnReleaseModeInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO callback


## -description


The <b>pfnReleaseModeInfo</b> function releases a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that the VidPN manager previously provided to the display miniport driver.


## -prototype


````
DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO pfnReleaseModeInfo;

NTSTATUS APIENTRY pfnReleaseModeInfo(
  _In_ const D3DKMDT_HMONITORSOURCEMODESET     hMonitorSourceModeSet,
  _In_ const D3DKMDT_MONITOR_SOURCE_MODE CONST *pMonitorSourceModeInfo
)
{ ... }
````


## -parameters




### -param hMonitorSourceModeSet [in]

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


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



When you have finished using a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that you obtained by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a> or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirenextmodeinfo.md">pfnAcquireNextModeInfo</a>, you must release the structure by calling <b>pfnReleaseModeInfo</b>.

The D3DKMDT_HMONITORSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md">D3DKMDT_MONITOR_SOURCE_MODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

