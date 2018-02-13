---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_ADDMODE
title: DXGKDDI_VIDPNTARGETMODESET_ADDMODE
author: windows-driver-content
description: The pfnAddMode function adds a VidPN target mode to a specified VidPN target mode set object.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnaddmode.htm
old-project: display
ms.assetid: 96c14056-aa93-4164-8adf-31fa1b3d33d3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_vidpntargetmodeset_interface_pfnaddmode, dxgk_vidpntargetmodeset_interface_pfnAddMode callback function [Display Devices], dxgk_vidpntargetmodeset_interface_pfnAddMode, DXGKDDI_VIDPNTARGETMODESET_ADDMODE, DXGKDDI_VIDPNTARGETMODESET_ADDMODE, d3dkmddi/dxgk_vidpntargetmodeset_interface_pfnAddMode, VidPnFunctions_96cfc36e-77db-49c8-b19c-e56624e72fb4.xml
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
-	dxgk_vidpntargetmodeset_interface_pfnAddMode
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTARGETMODESET_ADDMODE callback


## -description


The <b>pfnAddMode</b> function adds a VidPN target mode to a specified VidPN target mode set object.


## -prototype


````
DXGKDDI_VIDPNTARGETMODESET_ADDMODE dxgk_vidpntargetmodeset_interface_pfnAddMode;

NTSTATUS APIENTRY dxgk_vidpntargetmodeset_interface_pfnAddMode(
  _In_ D3DKMDT_HVIDPNTARGETMODESET     hVidPnTargetModeSet,
  _In_ D3DKMDT_VIDPN_TARGET_MODE CONST *pVidPnTargetModeInfo
)
{ ... }
````


## -parameters




### -param hVidPnTargetModeSet [in]

[in] A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset.md">pfnAcquireTargetModeSet</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param pVidPnTargetModeInfo [in]

[in] A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a> structure that describes the target mode. The display miniport driver previously obtained this structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a>.


## -returns



The <b>pfnAddMode</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTargetModeSet</i> was invalid.

</td>
</tr>
</table>
 




## -remarks



To add a mode to a target mode set, the display miniport driver performs the following steps.

<ol>
<li>
Call <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a> to obtain a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a> structure. The <b>pnfCreateNewModeInfo</b> function allocates the structure and fills in the <b>Id</b> member with a newly generated target mode identifier.

</li>
<li>
The <b>Info</b> member of the D3DKMDT_VIDPN_TARGET_MODE structure is a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_video_signal_info.md">D3DKMDT_VIDEO_SIGNAL_MODE</a> structure. Populate that structure with information about the mode.

</li>
<li>
Call <b>pfnAddMode</b> to add the mode to a target mode set.

</li>
</ol>
The VidPN manager allocates a D3DKMDT_VIDPN_TARGET_MODE structure when you call <b>pfnCreateNewModeInfo</b>. If you add the mode described by that structure to a target mode set, you do not need to explicitly release the structure; <b>pfnAddMode</b> releases it.

If you obtain a D3DKMDT_VIDPN_TARGET_MODE structure by calling <b>pfnCreateNewModeInfo</b> and then decide not to add that mode to a target mode set, you must explicity release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>.

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTARGETMODESET_ADDMODE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

