---
UID: NC:d3d10umddi.PFND3D11DDI_COPYSTRUCTURECOUNT
title: PFND3D11DDI_COPYSTRUCTURECOUNT (d3d10umddi.h)
description: The CopyStructureCount function copies the number of items in the filled portion (that is, the filled-size value) of an append buffer unordered access view (UAV) to an offset into a destination buffer.
old-location: display\copystructurecount.htm
ms.assetid: 39f20ff3-859f-4933-8be0-e2bb7c05e7e1
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_COPYSTRUCTURECOUNT callback function"]
ms.keywords: CopyStructureCount, CopyStructureCount callback function [Display Devices], PFND3D11DDI_COPYSTRUCTURECOUNT, PFND3D11DDI_COPYSTRUCTURECOUNT callback, UserModeDisplayDriverDx11_Functions_b6bad9fd-b0b2-40fa-aa4a-664554984dcd.xml, d3d10umddi/CopyStructureCount, display.copystructurecount
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CopyStructureCount is supported beginning with the Windows 7 operating system.
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11DDI_COPYSTRUCTURECOUNT
 - d3d10umddi/PFND3D11DDI_COPYSTRUCTURECOUNT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CopyStructureCount
---

# PFND3D11DDI_COPYSTRUCTURECOUNT callback function


## -description

The <b>CopyStructureCount</b> function copies the number of items in the filled portion (that is, the filled-size value) of an append buffer unordered access view (UAV) to an offset into a destination buffer.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDstBuffer* [in]

A handle to a destination buffer to copy the filled-size value of an UAV to. To create this destination buffer, the runtime must have previously called the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a> function with the <b>ResourceDimension</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> structure set to the D3D10DDIRESOURCE_BUFFER value.

### -param Arg3

*DstAlignedByteOffset* [in]

The 4-byte aligned offset, in bytes, into the destination buffer that the <i>hDstBuffer</i> parameter specifies. <b>CopyStructureCount</b> copies the filled-size value of the append buffer view that the <i>hSrcView</i> parameter specifies to this offset in <b>hDstBuffer</b>. <b>DstAlignedByteOffset</b> must be a multiple of four.

### -param Arg4

*hSrcView* [in]

A handle to the source append UAV, which must be an append buffer view. <b>CopyStructureCount</b> copies the filled-size value of this view to the destination buffer that the <b>hDstBuffer</b> parameter specifies. To create this append buffer view, the runtime must have previously called the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a> function with the D3D11_DDI_BUFFER_UAV_FLAG_APPEND flag set.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if the device removal interferes with the operation of <b>CopyStructureCount</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

<b>CopyStructureCount</b> takes the filled-size value of the append buffer UAV (a UAV that supports push and pop-up operations on structures like on a stack) and copies this value to an offset into the destination buffer. The graphics hardware uses a 4-byte filled-size value to keep track of how much data is filled in the append buffer UAV.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>