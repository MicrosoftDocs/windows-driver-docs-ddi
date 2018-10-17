---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_PINMODE
title: DXGKDDI_VIDPNTARGETMODESET_PINMODE
author: windows-driver-content
description: The pfnPinMode function pins a specified mode in a VidPN target mode set.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnpinmode.htm
ms.assetid: 91ea3105-2fdf-4533-a2d4-d27f1e660056
ms.date: 5/10/2018
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_PINMODE, DXGKDDI_VIDPNTARGETMODESET_PINMODE callback, VidPnFunctions_2b6f869f-bd7d-4699-8934-04cbe56bf0af.xml, d3dkmddi/pfnPinMode, display.dxgk_vidpntargetmodeset_interface_pfnpinmode, pfnPinMode, pfnPinMode callback function [Display Devices]
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
-	pfnPinMode
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNTARGETMODESET_PINMODE callback function


## -description


The <b>pfnPinMode</b> function pins a specified mode in a VidPN target mode set.


## -parameters




### -param hVidPnTargetModeSet [in]

[in] A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param VidPnTargetModeId [in]

[in] An integer that identifies the mode to be pinned.


## -returns



The <b>pfnPinMode</b> function returns one of the following values:

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET_MODE</b></dt>
</dl>
</td>
<td width="60%">
The mode identified by <i>VidPnTargetModeId</i> does not belong to the source mode set represented by <i>hVidPnTargetModeSet</i>.

</td>
</tr>
</table>
 




## -remarks



VidPN target mode identifiers are assigned by the operating system. The <a href="https://msdn.microsoft.com/ebb37681-fa03-49f5-968b-87c9ff4ebae9">pfnCreateNewModeInfo</a> function generates a mode identifier, assigns the identifier to the <b>Id</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a> structure, and returns the structure to the display miniport driver.

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>. 



