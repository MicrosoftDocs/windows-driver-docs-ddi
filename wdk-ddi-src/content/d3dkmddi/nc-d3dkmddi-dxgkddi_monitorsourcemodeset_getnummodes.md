---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES
title: DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES
author: windows-driver-content
description: The pfnGetNumModes function returns the number modes in a specified monitor source mode set.
old-location: display\dxgk_monitorsourcemodeset_interface_pfngetnummodes.htm
old-project: display
ms.assetid: 58daf5be-45c5-493b-9d51-ef48bb123dce
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.dxgk_monitorsourcemodeset_interface_pfngetnummodes, pfnGetNumModes callback function [Display Devices], pfnGetNumModes, DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES, DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES, d3dkmddi/pfnGetNumModes, VidPnFunctions_ac29494d-c35e-46bb-bfc1-6aaf70edbc2d.xml
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
-	pfnGetNumModes
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES callback


## -description


The <b>pfnGetNumModes</b> function returns the number modes in a specified monitor source mode set.


## -prototype


````
DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES pfnGetNumModes;

NTSTATUS APIENTRY pfnGetNumModes(
  _In_  const D3DKMDT_HMONITORSOURCEMODESET hMonitorSourceModeSet,
  _Out_ const SIZE_T CONST                  *pNumMonitorSourceModes
)
{ ... }
````


## -parameters




### -param hMonitorSourceModeSet [in]

A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


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

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirenextmodeinfo.md">pfnAcquireNextModeInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

