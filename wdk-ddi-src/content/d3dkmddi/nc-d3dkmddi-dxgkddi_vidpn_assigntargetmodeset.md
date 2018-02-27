---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_ASSIGNTARGETMODESET
title: DXGKDDI_VIDPN_ASSIGNTARGETMODESET
author: windows-driver-content
description: The pfnAssignTargetModeSet function assigns a target mode set to a particular target in a specified VidPN.
old-location: display\dxgk_vidpn_interface_pfnassigntargetmodeset.htm
old-project: display
ms.assetid: 846c6dd5-d4f8-4835-83a2-994725deaf36
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKDDI_VIDPN_ASSIGNTARGETMODESET, VidPnFunctions_7051492a-0560-4898-8532-60e66ebcb001.xml, d3dkmddi/pfnAssignTargetModeSet, display.dxgk_vidpn_interface_pfnassigntargetmodeset, pfnAssignTargetModeSet, pfnAssignTargetModeSet callback function [Display Devices]
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
-	pfnAssignTargetModeSet
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPN_ASSIGNTARGETMODESET callback


## -description


The <b>pfnAssignTargetModeSet</b> function assigns a target mode set to a particular target in a specified VidPN.


## -prototype


````
DXGKDDI_VIDPN_ASSIGNTARGETMODESET pfnAssignTargetModeSet;

NTSTATUS APIENTRY pfnAssignTargetModeSet(
  _In_       D3DKMDT_HVIDPN                 hVidPn,
  _In_ const D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId,
  _In_ const D3DKMDT_HVIDPNTARGETMODESET    hVidPnTargetModeSet
)
{ ... }
````


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a> or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>.


### -param VidPnTargetId [in]

[in] An integer that identifies one of the video present targets associated with the VidPN object.


### -param hVidPnTargetModeSet [in]

[in] A handle to the target mode set object that is to be assigned to the target identified by <i>VidPnTargetId</i>. The display miniport driver previously obtained this handle by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset.md">pfnCreateNewTargetModeSet</a>.


## -returns



The <b>pfnAssignTargetModeSet</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET</b></dt>
</dl>
</td>
<td width="60%">
The identifier supplied in <i>VidPnTargetId</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTargetModeSet</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_PINNED_MODE_MUST_REMAIN_IN_SET</b></dt>
</dl>
</td>
<td width="60%">
The target mode set you are attempting to assign does not contain the mode that was already pinned on the target.

</td>
</tr>
</table>
 




## -remarks



VidPN target identifiers are assigned by the display miniport driver. <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

If you obtain a handle by calling <b>pfnCreateNewTargetModeSet</b> and then pass that handle to <b>pfnAssignTargetModeSet</b>, you do not need to release the handle by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset.md">pfnReleaseTargetModeSet</a>.

If you obtain a handle by calling <b>pfnCreateNewTargetModeSet</b> and then you decide not to assign the new target mode set to a target, you must release the newly obtained handle by calling <b>pfnReleaseTargetModeSet</b>.  

<div class="alert"><b>Note</b>    The <b>pfnAssignTargetModeSet</b> function releases or does not release the target mode set object that is identified by the <i>hVidPnTargetModeSet</i> parameter depending on the reason that caused <b>pfnAssignTargetModeSet</b> to fail. <p class="note"><b>pfnAssignTargetModeSet</b> does not release the target mode set object if <b>pfnAssignTargetModeSet</b> fails with an invalid input parameter (that is, fails with the STATUS_GRAPHICS_INVALID_VIDPN, STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET, or STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET error code) because the parameters that were specified were not sufficient for the operating system to determine which mode set object to release. Such invalid parameter situations indicate a gross coding error in the driver. You can fix this error by specifying the correct VidPN handle, target identifier, or VidPN target mode set handle. 

<p class="note"><b>pfnAssignTargetModeSet</b> will release the target mode set object after successfully validating all of the input parameters if <b>pfnAssignTargetModeSet</b> fails because of one of the following reasons:

<ul>
<li>
The target mode set is empty.

</li>
<li>
The target mode set does not contain a mode that is pinned in the previous mode set, if any.

</li>
<li>
The target mode set was not created for the target that is identified by <i>VidPnTargetId</i>.

</li>
</ul>
</div>
<div> </div>
The D3DDDI_VIDEO_PRESENT_TARGET_ID data type is defined in <i>D3dukmdt.h</i>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNTARGETMODESET data types are defined in <i>D3dkmdt.h</i>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570559">VidPN Target Mode Set Interface</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset.md">pfnCreateNewTargetModeSet</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPN_ASSIGNTARGETMODESET callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

