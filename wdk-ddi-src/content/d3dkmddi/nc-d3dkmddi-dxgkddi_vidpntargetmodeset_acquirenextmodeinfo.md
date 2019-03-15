---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_ACQUIRENEXTMODEINFO
title: DXGKDDI_VIDPNTARGETMODESET_ACQUIRENEXTMODEINFO (d3dkmddi.h)
description: The pfnAcquireNextModeInfo function returns a descriptor of the next mode in a specified VidPN target mode set, given the current mode.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnacquirenextmodeinfo.htm
ms.assetid: 894d0d15-d12a-4138-9a92-8f930c12dd52
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_ACQUIRENEXTMODEINFO, DXGKDDI_VIDPNTARGETMODESET_ACQUIRENEXTMODEINFO callback, VidPnFunctions_27f5e19c-6a31-4e02-b9a2-8feaa5798fc3.xml, d3dkmddi/pfnAcquireNextModeInfo, display.dxgk_vidpntargetmodeset_interface_pfnacquirenextmodeinfo, pfnAcquireNextModeInfo, pfnAcquireNextModeInfo callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- pfnAcquireNextModeInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNTARGETMODESET_ACQUIRENEXTMODEINFO callback function


## -description


The <b>pfnAcquireNextModeInfo</b> function returns a descriptor of the next mode in a specified VidPN target mode set, given the current mode.


## -parameters




### -param hVidPnTargetModeSet [in]

[in] A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param pVidPnTargetModeInfo [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a> structure that describes the current mode. The display miniport driver previously obtained this pointer by calling <a href="https://msdn.microsoft.com/64a1a8f4-afbc-4337-b809-9346c1171e0b">pfnAcquireFirstModeInfo</a> or <b>pfnAcquireNextModeInfo</b>.


### -param ppNextVidPnTargetModeInfo [out]

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_TARGET_MODE structure that describes the next mode.


## -returns



The <b>pfnAcquireNextModeInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|


## -remarks



When you have finished using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a> structure, you must release the structure by calling <a href="https://msdn.microsoft.com/0b1d0331-f0fa-40fc-a1d6-15fe3568f3cc">pfnReleaseModeInfo</a>.

You can enumerate all the modes that belong to a particular target mode set object by calling <a href="https://msdn.microsoft.com/64a1a8f4-afbc-4337-b809-9346c1171e0b">pfnAcquireFirstModeInfo</a> and then making a sequence of calls to <b>pfnAcquireNextModeInfo</b>.

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="https://msdn.microsoft.com/64a1a8f4-afbc-4337-b809-9346c1171e0b">pfnAcquireFirstModeInfo</a>



<a href="https://msdn.microsoft.com/0b1d0331-f0fa-40fc-a1d6-15fe3568f3cc">pfnReleaseModeInfo</a>
 

 

