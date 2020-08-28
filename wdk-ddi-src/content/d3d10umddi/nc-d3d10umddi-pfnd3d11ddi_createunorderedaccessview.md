---
UID: NC:d3d10umddi.PFND3D11DDI_CREATEUNORDEREDACCESSVIEW
title: PFND3D11DDI_CREATEUNORDEREDACCESSVIEW (d3d10umddi.h)
description: The CreateUnorderedAccessView function creates an unordered access view.
old-location: display\createunorderedaccessview.htm
ms.assetid: c5a258e7-6645-46bb-ab2c-a1c8f5e593b7
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_CREATEUNORDEREDACCESSVIEW callback function"]
ms.keywords: CreateUnorderedAccessView, CreateUnorderedAccessView callback function [Display Devices], PFND3D11DDI_CREATEUNORDEREDACCESSVIEW, PFND3D11DDI_CREATEUNORDEREDACCESSVIEW callback, UserModeDisplayDriverDx11_Functions_4b9c2d38-c780-47be-a5fa-dec2c860732b.xml, d3d10umddi/CreateUnorderedAccessView, display.createunorderedaccessview
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateUnorderedAccessView is supported beginning with the Windows 7 operating system.
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
 - PFND3D11DDI_CREATEUNORDEREDACCESSVIEW
 - d3d10umddi/PFND3D11DDI_CREATEUNORDEREDACCESSVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CreateUnorderedAccessView
product:
 - Windows
---

# PFND3D11DDI_CREATEUNORDEREDACCESSVIEW callback function


## -description

The <b>CreateUnorderedAccessView</b> function creates an unordered access view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateUnorderedAccessView* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a> structure that describes the parameters that the user-mode display driver uses to create an unordered access view.

### -param Arg3

*hUnorderedAccessView* [in]

A handle to the driver's private data for the hull shader.

### -param Arg4

*hRTUnorderedAccessView* [in]

A handle to the unordered access view that the driver should use when it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview">DestroyUnorderedAccessView</a> function to destroy the handle that the <i>hUnorderedAccessView</i> parameter specifies.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize">CalcPrivateUnorderedAccessViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview">DestroyUnorderedAccessView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

