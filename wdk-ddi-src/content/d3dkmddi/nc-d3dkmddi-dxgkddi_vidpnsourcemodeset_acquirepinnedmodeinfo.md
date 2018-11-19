---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO
title: DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO
author: windows-driver-content
description: The pfnAcquirePinnedModeInfo function returns a descriptor of the pinned mode in a specified VidPN source mode set.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnacquirepinnedmodeinfo.htm
ms.assetid: e757852b-ee68-4b07-83c8-9dfd089d1ab7
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO, DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO callback, VidPnFunctions_552ed18a-24d2-4a92-85fa-3af6aa4733dc.xml, d3dkmddi/pfnAcquirePinnedModeInfo, display.dxgk_vidpnsourcemodeset_interface_pfnacquirepinnedmodeinfo, pfnAcquirePinnedModeInfo, pfnAcquirePinnedModeInfo callback function [Display Devices]
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
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO callback function


## -description


The <b>pfnAcquirePinnedModeInfo</b> function returns a descriptor of the pinned mode in a specified VidPN source mode set.


## -parameters




### -param hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/cf19f468-86c1-4cc9-8945-e23f73a85c91">pfnAcquireSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param ppPinnedVidPnSourceModeInfo [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a> structure. The structure contains a variety of information about the pinned mode, including its ID, type, and rendering format. If the source mode set identified by <i>hVidPnSourceModeSet</i> has no pinned mode, then this variable receives a <b>NULL</b> pointer.


## -returns



The <b>pfnAcquirePinnedModeInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded by doing one of the following:<br/>1. Setting ppPinnedVidPnSourceModeInfo to the address of D3DKMDT_VIDPN_SOURCE_MODE structure that describes the pinned mode.<br/>2. Setting ppPinnedVidPnSourceModeInfo to NULL to indicate that the source mode set has no pinned mode.|
|STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET|The handle supplied in hVidPnSourceModeSet was invalid.|




## -remarks



When you have finished using the D3DKMDT_VIDPN_SOURCE_MODE structure, you must release the structure by calling <a href="https://msdn.microsoft.com/614283cc-90bf-44f2-bab2-1aeec5e7de01">pfnReleaseModeInfo</a>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/14bbdc35-e633-49a5-bdf0-6b60d330ca8e">pfnPinMode</a>



<a href="https://msdn.microsoft.com/614283cc-90bf-44f2-bab2-1aeec5e7de01">pfnReleaseModeInfo</a>
 

 

