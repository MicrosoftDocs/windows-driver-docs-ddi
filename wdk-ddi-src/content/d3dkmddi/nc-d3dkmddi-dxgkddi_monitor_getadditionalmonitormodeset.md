---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET
title: DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET
author: windows-driver-content
description: The pfnGetAdditionalMonitorModeSet function, available in the DXGK_MONITOR_INTERFACE_V2 interface beginning with Windows 7, returns a handle to an additional monitor source mode set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_v2_pfngetadditionalmonitormodeset.htm
old-project: display
ms.assetid: 37878f3a-f61e-423c-ab03-94318089f7af
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_monitor_interface_v2_pfngetadditionalmonitormodeset, pfnGetAdditionalMonitorModeSet callback function [Display Devices], pfnGetAdditionalMonitorModeSet, DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET, DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET, d3dkmddi/pfnGetAdditionalMonitorModeSet, VidPnFunctions_c86b07fb-c73c-4990-86a0-15c93ba7e2dd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
-	pfnGetAdditionalMonitorModeSet
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET callback


## -description


The <i>pfnGetAdditionalMonitorModeSet</i> function, available in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface_v2.md">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7, returns a handle to an additional monitor source mode set object that is associated with a specified monitor.


## -prototype


````
DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET pfnGetAdditionalMonitorModeSet;

NTSTATUS APIENTRY pfnGetAdditionalMonitorModeSet(
  _In_  const D3DKMDT_ADAPTER                hAdapter,
  _In_  const D3DDDI_VIDEO_PRESENT_TARGET_ID VideoPresentTargetId,
  _Out_       UINT                           *pNumberModes,
  _Out_       DXGK_TARGETMODE_DETAIL_TIMING  **ppAdditionalModesSet
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


### -param VideoPresentTargetId [in]

[in] An integer that identifies one of the video present targets on the display adapter. The returned <i>ppAdditionalModesSet</i> additional modes set object describes the additional monitor source mode sets that are available on the monitor that is connected to this video present target.


### -param pNumberModes [out]

[out] A pointer to a variable that contains the number of additional timing modes of the video present target specified by <i>VideoPresentTargetId</i>.


### -param ppAdditionalModesSet [out]

[out] A pointer to a variable that receives a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_targetmode_detail_timing.md">DXGK_TARGETMODE_DETAIL_TIMING</a> structure. The structure describes a video present target's additional timing modes that are compatible with the display device.


## -returns



The <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md">pfnAcquireMonitorSourceModeSet</a> function returns one of the following values.

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
<dt><b>STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hAdapter</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET</b></dt>
</dl>
</td>
<td width="60%">
The identifier supplied in <i>VideoPresentTargetId</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_MONITOR_NOT_CONNECTED</b></dt>
</dl>
</td>
<td width="60%">
There is no monitor connected to the video present target identified by <i>VideoPresentTargetId</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The video present target identified by <i>VideoPresentTargetId</i> could not be found.

</td>
</tr>
</table>
 




## -remarks



VidPN target identifiers are assigned by the display miniport driver. The <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> function, implemented by the display miniport driver, returns an array of <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

This function is available beginning with Windows 7.




## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_targetmode_detail_timing.md">DXGK_TARGETMODE_DETAIL_TIMING</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface_v2.md">DXGK_MONITOR_INTERFACE_V2</a>



<a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_releaseadditionalmonitormodeset.md">DXGK_MONITOR_INTERFACE_V2::pfnReleaseAdditionalMonitorModeSet</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_targetmode_detail_timing.md">DXGK_TARGETMODE_DETAIL_TIMING</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_releaseadditionalmonitormodeset.md">DXGK_MONITOR_INTERFACE_V2::pfnReleaseAdditionalMonitorModeSet</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

