---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_PINMODE
title: DXGKDDI_VIDPNSOURCEMODESET_PINMODE (d3dkmddi.h)
description: The pfnPinMode function pins a specified mode in a VidPN source mode set.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnpinmode.htm
ms.assetid: 14bbdc35-e633-49a5-bdf0-6b60d330ca8e
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNSOURCEMODESET_PINMODE, DXGKDDI_VIDPNSOURCEMODESET_PINMODE callback, VidPnFunctions_7fb0636b-da59-4451-8cf2-57b944629499.xml, d3dkmddi/pfnPinMode, display.dxgk_vidpnsourcemodeset_interface_pfnpinmode, pfnPinMode, pfnPinMode callback function [Display Devices]
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

# DXGKDDI_VIDPNSOURCEMODESET_PINMODE callback function


## -description


The <b>pfnPinMode</b> function pins a specified mode in a VidPN source mode set.


## -parameters




### -param hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/cf19f468-86c1-4cc9-8945-e23f73a85c91">pfnAcquireSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param VidPnSourceModeId [in]

[in] An integer that identifies the mode to be pinned.


## -returns



The <b>pfnPinMode</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET|The handle supplied in hVidPnSourceModeSet was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE_MODE|The mode identified by VidPnSourceModeId does not belong to the source mode set represented by hVidPnSourceModeSet.|


## -remarks



VidPN source mode identifiers are assigned by the operating system. The <a href="https://msdn.microsoft.com/b18aab68-7457-45eb-8641-0b6180cfa70e">pfnCreateNewModeInfo</a> function generates a mode identifier, assigns the identifier to the <b>Id</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a> structure, and returns the structure to the display miniport driver.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/e757852b-ee68-4b07-83c8-9dfd089d1ab7">pfnAcquirePinnedModeInfo</a>
 

 

