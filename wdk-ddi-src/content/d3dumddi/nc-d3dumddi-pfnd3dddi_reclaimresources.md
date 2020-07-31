---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMRESOURCES
title: PFND3DDDI_RECLAIMRESOURCES (d3dumddi.h)
description: Called by the Microsoft Direct3D runtime to reclaim video memory resources that it previously offered for reuse.
old-location: display\reclaimresources.htm
tech.root: display
ms.assetid: F0533DBB-CB18-4556-9871-2DF4CA719172
ms.date: 05/10/2018
keywords: ["PFND3DDDI_RECLAIMRESOURCES callback function"]
ms.keywords: PFND3DDDI_RECLAIMRESOURCES, PFND3DDDI_RECLAIMRESOURCES callback, ReclaimResources, ReclaimResources callback function [Display Devices], d3dumddi/ReclaimResources, display.reclaimresources
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/ReclaimResources"
 - "ReclaimResources"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - ReclaimResources
product:
 - Windows
---

# PFND3DDDI_RECLAIMRESOURCES callback function

## -description

Called by the Microsoft Direct3D runtime to reclaim video memory resources that it  previously offered  for reuse.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_reclaimresources">D3DDDIARG_RECLAIMRESOURCES</a> structure that defines the video memory resources to reclaim.

## -returns

Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The video memory resources were successfully reclaimed.<br/>This error code is returned if the driver does not need to call the [pfnReclaimAllocationsCb](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocationscb)  function. | 
| **E_INVALIDARG** | An invalid parameter was supplied.<br/>This error code is returned if the driver calls the [pfnReclaimAllocationsCb](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocationscb) function and that function returns E_INVALIDARG. | 
| **D3DDDIERR_DEVICEREMOVED** | The video memory manager or display miniport driver could not complete the operation because either a Plug and Play (PnP) Stop event or a Timeout Detection and Recovery (TDR) event occurred.<br/>This error code is returned if the driver calls the [pfnReclaimAllocationsCb](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocationscb) function and that function returns D3DDDIERR_DEVICEREMOVED.<br/>**Note:** If this error code is returned, the driver's calling function (typically the [ReclaimResourcesDXGI](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions)  routine) must return this error code to the Direct3D runtime. |

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_reclaimresources">D3DDDIARG_RECLAIMRESOURCES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_offerresources">OfferResources</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">ReclaimResourcesDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocationscb">pfnReclaimAllocationsCb</a>

