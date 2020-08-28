---
UID: NC:d3d10umddi.PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP
title: PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP (d3d10umddi.h)
description: Updates a destination subresource region that stores constant buffers from a source system-memory region. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\defaultconstantbufferupdatesubresourceup_d3d11_1_.htm
ms.assetid: 67FCC9A4-B3C5-46FC-83ED-CFFB8186328F
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP callback function"]
ms.keywords: DefaultConstantBufferUpdateSubresourceUP(D3D11_1), DefaultConstantBufferUpdateSubresourceUP(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP, PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP callback, d3d10umddi/DefaultConstantBufferUpdateSubresourceUP(D3D11_1), display.defaultconstantbufferupdatesubresourceup_d3d11_1_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP
 - d3d10umddi/PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - DefaultConstantBufferUpdateSubresourceUP(D3D11_1)
---

# PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP callback function


## -description

updates a destination subresource region that stores constant buffers from a source system-memory region. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDstResource*

A handle to the destination resource to copy to.

### -param Arg3

*DstSubresource*

An index that indicates the destination subresource to copy to.

### -param Arg4

*pDstBox* [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_box">D3D10_DDI_BOX</a> structure that specifies the region of the destination subresource to copy data to. If <i>pDstBox</i> is <b>NULL</b>, the driver should copy to the entire destination subresouce.

### -param Arg5

*pSysMemUP* [in]

A pointer to the beginning address of the source data that <b>DefaultConstantBufferUpdateSubresourceUP(D3D11_1)</b> uses to update the destination subresouce.

### -param Arg6

*RowPitch*

The offset, in bytes, to move to the next row of source data.

### -param Arg7

*DepthPitch*

The offset, in bytes, to move to the next depth slice of source data.

### -param CopyFlags

A value that specifies characteristics of copy operation as a bitwise <b>OR</b> of the values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1_ddi_copy_flags">D3D11_1_DDI_COPY_FLAGS</a> enumeration type.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code.






The driver should not encounter any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>. Therefore, if the driver passes any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return <b>D3DDDIERR_DEVICEREMOVED</b>; however, if device removal interfered with the operation of <b>DefaultConstantBufferUpdateSubresourceUP(D3D11_1)</b> (which typically should not happen), the driver can return <b>D3DDDIERR_DEVICEREMOVED</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_devicefuncs">D3D11_1DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1_ddi_copy_flags">D3D11_1_DDI_COPY_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

