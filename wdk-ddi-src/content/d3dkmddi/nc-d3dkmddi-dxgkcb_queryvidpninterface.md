---
UID: NC:d3dkmddi.DXGKCB_QUERYVIDPNINTERFACE
title: DXGKCB_QUERYVIDPNINTERFACE (d3dkmddi.h)
description: The DxgkCbQueryVidPnInterface function returns a pointer to a DXGK_VIDPN_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter a VidPN object.
old-location: display\dxgkcbqueryvidpninterface.htm
ms.assetid: 649ce7fc-6852-43f3-b944-b2b64fcba874
ms.date: 05/10/2018
ms.keywords: DXGKCB_QUERYVIDPNINTERFACE, DXGKCB_QUERYVIDPNINTERFACE callback, DpFunctions_0bbf993b-c05b-402b-af4a-cf1a3ec4d4b8.xml, DxgkCbQueryVidPnInterface, DxgkCbQueryVidPnInterface callback function [Display Devices], d3dkmddi/DxgkCbQueryVidPnInterface, display.dxgkcbqueryvidpninterface
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DxgkCbQueryVidPnInterface
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_QUERYVIDPNINTERFACE callback function


## -description


The <b>DxgkCbQueryVidPnInterface</b> function returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter a VidPN object.


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided the display miniport driver with this handle by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn">DxgkDdiIsSupportedVidPn</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>.


### -param VidPnInterfaceVersion [in]

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ne-d3dkmddi-_dxgk_vidpn_interface_version">DXGK_VIDPN_INTERFACE_VERSION</a> enumerator that specifies the version of the VidPN interface being requested. Callers must set this parameter to <b>DXGK_VIDPN_INTERFACE_VERSION_V1</b>.


### -param ppVidPnInterface [out]

[out] A pointer to a variable that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> structure.


## -returns



<b>DxgkCbQueryVidPnInterface </b>returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_INVALID_PARAMETER|The value passed to ppVidPnInterface is not valid.|
|STATUS_GRAPHICS_INVALID_VIDPN|The handle passed to hVidPn is not valid.|
|STATUS_NOT_SUPPORTED|The interface version specified by VidPnInterfaceVersion is not supported.|
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Monitor Source Mode Set Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">VidPN Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">VidPN Source Mode Set Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">VidPN Target Mode Set Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">VidPN Topology Interface</a>
 

 

