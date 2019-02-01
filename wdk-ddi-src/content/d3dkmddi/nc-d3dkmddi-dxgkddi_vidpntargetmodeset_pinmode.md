---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_PINMODE
title: DXGKDDI_VIDPNTARGETMODESET_PINMODE (d3dkmddi.h)
description: The pfnPinMode function pins a specified mode in a VidPN target mode set.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnpinmode.htm
ms.assetid: 91ea3105-2fdf-4533-a2d4-d27f1e660056
ms.date: 05/10/2018
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

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET_MODE|The mode identified by VidPnTargetModeId does not belong to the source mode set represented by hVidPnTargetModeSet.|

## -remarks



VidPN target mode identifiers are assigned by the operating system. The <a href="https://msdn.microsoft.com/ebb37681-fa03-49f5-968b-87c9ff4ebae9">pfnCreateNewModeInfo</a> function generates a mode identifier, assigns the identifier to the <b>Id</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a> structure, and returns the structure to the display miniport driver.

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>. 



