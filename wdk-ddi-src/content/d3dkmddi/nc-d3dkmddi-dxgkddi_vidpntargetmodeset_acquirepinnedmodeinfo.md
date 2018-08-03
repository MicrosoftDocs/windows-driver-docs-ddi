---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO
title: DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO
author: windows-driver-content
description: The pfnAcquirePinnedModeInfo function returns a descriptor of the pinned mode in a specified VidPN target mode set.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnacquirepinnedmodeinfo.htm
tech.root: display
ms.assetid: 0a321ee2-f246-498d-b658-a01e275644be
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO, DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO callback, VidPnFunctions_81cb0000-6d1d-448f-8e4a-ca5df30d97ea.xml, d3dkmddi/pfnAcquirePinnedModeInfo, display.dxgk_vidpntargetmodeset_interface_pfnacquirepinnedmodeinfo, pfnAcquirePinnedModeInfo, pfnAcquirePinnedModeInfo callback function [Display Devices]
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
-	pfnAcquirePinnedModeInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO callback function


## -description


The <b>pfnAcquirePinnedModeInfo</b> function returns a descriptor of the pinned mode in a specified VidPN target mode set.


## -parameters




### -param hVidPnTargetModeSet [in]

[in] A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param ppPinnedVidPnTargetModeInfo [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a> structure. The structure contains a variety of information about the pinned mode, including its ID and video signal characteristics. If the target mode set identified by <i>hVidPnTargetModeSet</i> has no pinned mode, then this variable receives a <b>NULL</b> pointer.


## -returns



The <b>pfnAcquirePinnedModeInfo</b> function returns one of the following values:

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
The function succeeded by doing one of the following:

Setting <i>ppPinnedVidPnTargetModeInfo</i> to the address of D3DKMDT_VIDPN_TARGET_MODE structure that describes the pinned mode.

Setting <i>ppPinnedVidPnTargetModeInfo</i> to <b>NULL</b> to indicate that the target mode set has no pinned mode. 

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



When you have finished using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a> structure, you must release the structure by calling <a href="https://msdn.microsoft.com/0b1d0331-f0fa-40fc-a1d6-15fe3568f3cc">pfnReleaseModeInfo</a>.

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="https://msdn.microsoft.com/91ea3105-2fdf-4533-a2d4-d27f1e660056">pfnPinMode</a>



<a href="https://msdn.microsoft.com/0b1d0331-f0fa-40fc-a1d6-15fe3568f3cc">pfnReleaseModeInfo</a>
 

 

