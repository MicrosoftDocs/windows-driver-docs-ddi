---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_RELEASETARGETMODESET
title: DXGKDDI_VIDPN_RELEASETARGETMODESET
author: windows-driver-content
description: The pfnReleaseTargetModeSet function releases a handle to a target mode set object.
old-location: display\dxgk_vidpn_interface_pfnreleasetargetmodeset.htm
old-project: display
ms.assetid: bd369651-57d4-406f-ba51-9632362de15d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_vidpn_interface_pfnreleasetargetmodeset, pfnReleaseTargetModeSet callback function [Display Devices], pfnReleaseTargetModeSet, DXGKDDI_VIDPN_RELEASETARGETMODESET, DXGKDDI_VIDPN_RELEASETARGETMODESET, d3dkmddi/pfnReleaseTargetModeSet, VidPnFunctions_c1609a38-53ff-49e0-a11a-26ceb5d64cdb.xml
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
-	pfnReleaseTargetModeSet
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPN_RELEASETARGETMODESET callback


## -description


The <b>pfnReleaseTargetModeSet</b> function releases a handle to a target mode set object.


## -prototype


````
DXGKDDI_VIDPN_RELEASETARGETMODESET pfnReleaseTargetModeSet;

NTSTATUS APIENTRY pfnReleaseTargetModeSet(
  _In_ const D3DKMDT_HVIDPN              hVidPn,
  _In_ const D3DKMDT_HVIDPNTARGETMODESET hVidPnTargetModeSet
)
{ ... }
````


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object that contains the target mode set object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a>, or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>.


### -param hVidPnTargetModeSet [in]

[in] The handle to be released.


## -returns



The <b>pfnReleaseTargetModeSet</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_RESOURCES_NOT_RELATED</b></dt>
</dl>
</td>
<td width="60%">
The VidPN identified by <i>hVidPn</i> does not contain the target mode set identified by <i>hVidPnTargetModeSet</i>.

</td>
</tr>
</table>
 




## -remarks



When you have finished using a handle that you obtained by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset.md">pfnAcquireTargetModeSet</a>, you must release the handle by calling <b>pfnReleaseTargetModeSet</b>.

If you obtain a handle by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset.md">pfnCreateNewTargetModeSet</a> and then pass that handle to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_assigntargetmodeset.md">pfnAssignTargetModeSet</a>, you do not need to release the handle.

If you obtain a handle by calling <b>pfnCreateNewTargetModeSet</b> and then you decide not to assign the new source mode set to a source, you must release the newly obtained handle by calling <b>pfnReleaseTargetModeSet</b>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNTARGETMODESET data types are defined in <i>D3dkmdt.h</i>. 




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset.md">pfnAcquireTargetModeSet</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset.md">pfnCreateNewTargetModeSet</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPN_RELEASETARGETMODESET callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

