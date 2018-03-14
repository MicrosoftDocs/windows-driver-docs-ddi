---
UID: NC:d3d10umddi.PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP
title: PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP
author: windows-driver-content
description: Updates a destination subresource region that stores constant buffers from a source system-memory region. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\defaultconstantbufferupdatesubresourceup_d3d11_1_.htm
old-project: display
ms.assetid: 67FCC9A4-B3C5-46FC-83ED-CFFB8186328F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DefaultConstantBufferUpdateSubresourceUP(D3D11_1), DefaultConstantBufferUpdateSubresourceUP(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP, d3d10umddi/DefaultConstantBufferUpdateSubresourceUP(D3D11_1), display.defaultconstantbufferupdatesubresourceup_d3d11_1_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	DefaultConstantBufferUpdateSubresourceUP(D3D11_1)
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP callback


## -description


updates a destination subresource region that stores constant buffers from a source system-memory region. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -prototype


````
PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP DefaultConstantBufferUpdateSubresourceUP(D3D11_1);

VOID APIENTRY* DefaultConstantBufferUpdateSubresourceUP(D3D11_1)(
                 D3D10DDI_HDEVICE   hDevice,
                 D3D10DDI_HRESOURCE hDstResource,
                 UINT               DstSubresource,
  _In_opt_ const D3D10_DDI_BOX      *pDstBox,
  _In_     const VOID               *pSysMemUP,
                 UINT               RowPitch,
                 UINT               DepthPitch,
                 UINT               CopyFlags
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D10DDI_HRESOURCE


### -param UINT


### -param *


### -param CopyFlags

A value that specifies characteristics of copy operation as a bitwise <b>OR</b> of the values in the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1_ddi_copy_flags.md">D3D11_1_DDI_COPY_FLAGS</a> enumeration type.


#### - DepthPitch

 The offset, in bytes, to move to the next depth slice of source data.


#### - DstSubresource

 An index that indicates the destination subresource to copy to.


#### - RowPitch

 The offset, in bytes, to move to the next row of source data.


#### - hDevice

 A handle to the display device (graphics context).


#### - hDstResource

 A handle to the destination resource to copy to.


#### - pDstBox [in, optional]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_box.md">D3D10_DDI_BOX</a> structure that specifies the region of the destination subresource to copy data to. If <i>pDstBox</i> is <b>NULL</b>, the driver should copy to the entire destination subresouce. 


#### - pSysMemUP [in]

 A pointer to the beginning address of the source data that <b>DefaultConstantBufferUpdateSubresourceUP(D3D11_1)</b> uses to update the destination subresouce. 


## -returns



None.

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>. Therefore, if the driver passes any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return <b>D3DDDIERR_DEVICEREMOVED</b>; however, if device removal interfered with the operation of <b>DefaultConstantBufferUpdateSubresourceUP(D3D11_1)</b> (which typically should not happen), the driver can return <b>D3DDDIERR_DEVICEREMOVED</b>.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_devicefuncs.md">D3D11_1DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1_ddi_copy_flags.md">D3D11_1_DDI_COPY_FLAGS</a>



 

 


