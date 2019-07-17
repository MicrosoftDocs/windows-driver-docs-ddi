---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_CREATENEWSOURCEMODESET
title: DXGKDDI_VIDPN_CREATENEWSOURCEMODESET (d3dkmddi.h)
description: The pfnCreateNewSourceModeSet function creates a new source mode set object within a specified VidPN object.
old-location: display\dxgk_vidpn_interface_pfncreatenewsourcemodeset.htm
ms.assetid: d46ffa49-6e75-4cd4-9d14-aa2c9fa671be
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPN_CREATENEWSOURCEMODESET, DXGKDDI_VIDPN_CREATENEWSOURCEMODESET callback, VidPnFunctions_13c4227c-f1d3-4191-a085-5ed298fe11e7.xml, d3dkmddi/pfnCreateNewSourceModeSet, display.dxgk_vidpn_interface_pfncreatenewsourcemodeset, pfnCreateNewSourceModeSet, pfnCreateNewSourceModeSet callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3dkmddi/pfnCreateNewSourceModeSet"
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
- pfnCreateNewSourceModeSet
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPN_CREATENEWSOURCEMODESET callback function


## -description


The <b>pfnCreateNewSourceModeSet</b> function creates a new source mode set object within a specified VidPN object.


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn">DxgkDdiIsSupportedVidPn</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>.


### -param VidPnSourceId [in]

[in] An integer that identifies one of the video present sources associated with the VidPN object.


### -param phNewVidPnSourceModeSet [out]

[out] A pointer to a variable that receives a handle to the newly created source mode set object.


### -param ppVidPnSourceModeSetInterface [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface">DXGK_VIDPNSOURCEMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the source mode set object.


## -returns



The <b>pfnCreateNewSourceModeSet</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN|The handle supplied in hVidPn was invalid.|
|STATUS_NO_MEMORY|The VidPN manager was unable to allocate the memory required to create the new source mode set object.|


## -remarks



To assign a new source mode set to a particular source in a VidPN, perform the following steps:

<ol>
<li>
Call <b>pfnCreateNewSourceModeSet</b> to get a handle to a new source mode set object. That source mode set object belongs to a particular VidPN object that you specify.

</li>
<li>
Use the functions of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface">DXGK_VIDPNSOURCEMODESET_INTERFACE</a> interface to add modes to the source mode set object.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_assignsourcemodeset">pfnAssignSourceModeSet</a> to assign the new source mode set to a particular source.

</li>
</ol>
If you obtain a handle by calling <b>pfnCreateNewSourceModeSet</b> and then pass that handle to <b>pfnAssignSourceModeSet</b>, you do not need to release the handle by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasesourcemodeset">pfnReleaseSourceModeSet</a>.

If you obtain a handle by calling <b>pfnCreateNewSourceModeSet</b> and then you decide not to assign the new source mode set to a source, you must release the newly obtained handle by calling <b>pfnReleaseSourceModeSet</b>.

The lifetime of the DXGK_VIDPNSOURCEMODESET_INTERFACE structure returned in <i>ppVidPnSourceModeSetInterface</i> is owned by the operating system. Using this ownership scheme, the operating system can switch to newer implementations at run time without breaking clients of the interface.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNSOURCEMODESET data types are defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">VidPN Source Mode Set Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_assignsourcemodeset">pfnAssignSourceModeSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasesourcemodeset">pfnReleaseSourceModeSet</a>
 

 

