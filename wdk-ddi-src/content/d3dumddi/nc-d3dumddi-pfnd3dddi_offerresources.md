---
UID: NC:d3dumddi.PFND3DDDI_OFFERRESOURCES
title: PFND3DDDI_OFFERRESOURCES (d3dumddi.h)
description: Called by the Microsoft Direct3D runtime to request that the user-mode display driver offer video memory resources for reuse.
old-location: display\offerresources.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_OFFERRESOURCES callback function"]
ms.keywords: OfferResources, OfferResources callback function [Display Devices], PFND3DDDI_OFFERRESOURCES, PFND3DDDI_OFFERRESOURCES callback, d3dumddi/OfferResources, display.offerresources
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
 - PFND3DDDI_OFFERRESOURCES
 - d3dumddi/PFND3DDDI_OFFERRESOURCES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_OFFERRESOURCES
product:
 - Windows
---

# PFND3DDDI_OFFERRESOURCES callback function


## -description

Called by the Microsoft Direct3D runtime to request that the user-mode display driver  offer video memory resources for reuse.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_offerresources">D3DDDIARG_OFFERRESOURCES</a> structure that defines the video memory resources that the driver offers.

## -returns

Returns one of the following values.

|Return code|Description|
|--- |--- |
|S_OK|The video memory resources were successfully offered.|
|D3DDDIERR_DEVICEREMOVED|The driver detected that the display adapter was removed, so the driver did not complete the operation.<br/>If the driver is not aware of the adapter removal, the driver is not required to return this error code.|

## -remarks

If the user-mode driver does not have outstanding work queued that references an allocation that it has been asked to offer, then it can offer the allocation immediately or postpone the offer until the next call is made to the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfworkitem-flush">Flush</a> or <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_present">Present</a> functions. However, the driver must always process all batched offer calls that have been submitted through <i>Flush</i> or <i>Present</i>.

If the driver uses the <a href="/windows-hardware/drivers/display/requesting-to-rename-an-allocation">renaming service</a> of the video memory manager, then the driver should offer the last allocation instance.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_offerresources">D3DDDIARG_OFFERRESOURCES</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfworkitem-flush">Flush</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_present">Present</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimresources">ReclaimResources</a>

