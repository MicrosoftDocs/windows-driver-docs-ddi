---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_ASSIGNSOURCEMODESET
title: DXGKDDI_VIDPN_ASSIGNSOURCEMODESET
author: windows-driver-content
description: The pfnAssignSourceModeSet function assigns a source mode set to a particular source in a specified VidPN.
old-location: display\dxgk_vidpn_interface_pfnassignsourcemodeset.htm
old-project: display
ms.assetid: e1a2ca9e-9035-4656-bcb8-4ad956a8501d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_vidpn_interface_pfnassignsourcemodeset, pfnAssignSourceModeSet callback function [Display Devices], pfnAssignSourceModeSet, DXGKDDI_VIDPN_ASSIGNSOURCEMODESET, DXGKDDI_VIDPN_ASSIGNSOURCEMODESET, d3dkmddi/pfnAssignSourceModeSet, VidPnFunctions_558924ab-3dd4-43e9-84ed-4e28feae91c5.xml
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
-	pfnAssignSourceModeSet
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPN_ASSIGNSOURCEMODESET callback


## -description


The <b>pfnAssignSourceModeSet</b> function assigns a source mode set to a particular source in a specified VidPN.


## -prototype


````
DXGKDDI_VIDPN_ASSIGNSOURCEMODESET pfnAssignSourceModeSet;

NTSTATUS APIENTRY pfnAssignSourceModeSet(
  _In_       D3DKMDT_HVIDPN                 hVidPn,
  _In_ const D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId,
  _In_ const D3DKMDT_HVIDPNSOURCEMODESET    hVidPnSourceModeSet
)
{ ... }
````


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a> or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>.


### -param VidPnSourceId [in]

[in] An integer that identifies one of the video present sources associated with the VidPN object.


### -param hVidPnSourceModeSet [in]

[in] A handle to the source mode set object that is to be assigned to the source identified by <i>VidPnSourceId</i>. The display miniport driver previously obtained this handle by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset.md">pfnCreateNewSourceModeSet</a>.


## -returns


The <b>pfnAssignSourceModeSet</b> function returns one of the following values:
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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPn</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The identifier supplied in <i>VidPnSourceId</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnSourceModeSet</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_PINNED_MODE_MUST_REMAIN_IN_SET</b></dt>
</dl>
</td>
<td width="60%">
The source mode set you are attempting to assign does not contain the mode that was already pinned on the source.

</td>
</tr>
</table> 



## -remarks


VidPN source identifiers are assigned by the operating system. <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

If you obtain a handle by calling <b>pfnCreateNewSourceModeSet</b> and then pass that handle to <b>pfnAssignSourceModeSet</b>, you do not need to release  the handle by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_releasesourcemodeset.md">pfnReleaseSourceModeSet</a>.

If you obtain a handle by calling <b>pfnCreateNewSourceModeSet</b> and then you decide not to assign the new source mode set to a source, you must release the newly obtained handle by calling <b>pfnReleaseSourceModeSet</b>.  
<div class="alert"><b>Note</b>    The <b>pfnAssignSourceModeSet</b> function releases or does not release the source mode set object that is identified by the <i>hVidPnSourceModeSet</i> parameter depending on the reason that caused <b>pfnAssignSourceModeSet</b> to fail. <p class="note"><b>pfnAssignSourceModeSet</b> does not release the source mode set object if <b>pfnAssignSourceModeSet</b> fails with an invalid input parameter (that is, fails with the STATUS_GRAPHICS_INVALID_VIDPN, STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE, or STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET error code) because the parameters that were specified were not sufficient for the operating system to determine which mode set object to release. Such invalid parameter situations indicate a gross coding error in the driver. You can fix this error by specifying the correct VidPN handle, source identifier, or VidPN source mode set handle. 

<p class="note"><b>pfnAssignSourceModeSet</b> will release the source mode set object after successfully validating all of the input parameters if <b>pfnAssignSourceModeSet</b> fails because of one of the following reasons:

<ul>
<li>
The source mode set is empty.

</li>
<li>
The source mode set does not contain a mode that is pinned in the previous mode set, if any.

</li>
<li>
The source mode set was not created for the source that is identified by <i>VidPnSourceId</i>.

</li>
</ul>
</div><div> </div>The D3DDDI_VIDEO_PRESENT_SOURCE_ID data type is defined in <i>D3dukmdt.h</i>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNSOURCEMODESET data types are defined in <i>D3dkmdt.h</i>. 



## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset.md">pfnCreateNewSourceModeSet</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570558">VidPN Source Mode Set Interface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPN_ASSIGNSOURCEMODESET callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

