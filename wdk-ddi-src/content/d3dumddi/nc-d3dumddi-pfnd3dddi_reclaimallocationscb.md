---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMALLOCATIONSCB
title: PFND3DDDI_RECLAIMALLOCATIONSCB (d3dumddi.h)
description: Called by the user-mode display driver to reclaim video memory allocations that were previously offered for reuse.
old-location: display\pfnreclaimallocationscb.htm
tech.root: display
ms.assetid: BAC27F24-B348-48D5-9E9B-20897B4D8E2D
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_RECLAIMALLOCATIONSCB, d3dumddi/pfnReclaimAllocationsCb, display.pfnreclaimallocationscb, pfnReclaimAllocationsCb, pfnReclaimAllocationsCb callback, pfnReclaimAllocationsCb callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3dumddi/pfnReclaimAllocationsCb"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- pfnReclaimAllocationsCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_RECLAIMALLOCATIONSCB callback function


## -description


Called by the user-mode display driver   to reclaim video memory allocations that were previously offered  for reuse.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_reclaimallocations">D3DDDICB_RECLAIMALLOCATIONS</a> structure that defines the allocations to reclaim.


## -returns

Returns one of the following values.

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The allocations were successfully reclaimed. | 
| **E_INVALIDARG** | An invalid parameter was supplied. | 
| **D3DDDIERR_DEVICEREMOVED** | The video memory manager or display miniport driver could not complete the operation because either a Plug and Play (PnP) Stop event or a Timeout Detection and Recovery (TDR) event occurred.<br/>**Note:** If this error code is returned, the driver's calling function (typically the [pfnReclaimResources](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions)  routine) must return this error code to the Direct3D runtime. | 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_reclaimallocations">D3DDDICB_RECLAIMALLOCATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">pfnReclaimResources</a>
 

 

