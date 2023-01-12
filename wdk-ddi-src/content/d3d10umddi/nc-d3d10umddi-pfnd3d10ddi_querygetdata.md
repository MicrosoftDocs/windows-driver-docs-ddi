---
UID: NC:d3d10umddi.PFND3D10DDI_QUERYGETDATA
title: PFND3D10DDI_QUERYGETDATA (d3d10umddi.h)
description: The QueryGetData function polls for the state of a query operation.
old-location: display\querygetdata.htm
ms.date: 08/22/2022
keywords: ["PFND3D10DDI_QUERYGETDATA callback function"]
ms.keywords: PFND3D10DDI_QUERYGETDATA, PFND3D10DDI_QUERYGETDATA callback, QueryGetData, QueryGetData callback function [Display Devices], UserModeDisplayDriverDx10_Functions_c1a88bca-7df5-4640-9134-fc893e5c8a0d.xml, d3d10umddi/QueryGetData, display.querygetdata
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
 - PFND3D10DDI_QUERYGETDATA
 - d3d10umddi/PFND3D10DDI_QUERYGETDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_QUERYGETDATA
product:
 - Windows
---

# PFND3D10DDI_QUERYGETDATA callback function

## -description

The **QueryGetData** function polls for the state of a query operation.

## -parameters

### -param unnamedParam1

*hDevice* [in]: A handle to the display device (graphics context).

### -param unnamedParam2

*hQuery* [in]: A handle to the query object to poll.

### -param unnamedParam3

*pData* [out]: A pointer to a region of memory that receives the data from a query operation. The user-mode display driver can set **pData** to NULL and set the **DataSize** parameter to zero. If **pData** is NULL, **QueryGetData** can indicate the state of the query operation (for example, whether the query operation is finished).

### -param DataSize

[out] The size, in bytes, of the query data that the **pData** parameter points to. The user-mode display driver can set **DataSize** to zero and set **pData** to NULL. If **DataSize** is zero, **QueryGetData** can indicate the state of the query operation (for example, through return codes).

### -param unnamedParam5

*Flags* [in]: D3D10_DDI_GET_DATA_FLAG flags.

## -remarks

The driver can use the [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) callback function to set an error code.

After the Microsoft Direct3D runtime calls the user-mode display driver's [**QueryEnd**](nc-d3d10umddi-pfnd3d10ddi_queryend.md) function to transition a query operation to the "issued" state, the runtime can call **QueryGetData** to determine if the query operation is still in the "issued" state (DXGI_DDI_ERR_WASSTILLDRAWING) or has transitioned to the "signaled" state (S_OK). If the query operation is in the "signaled" state, **QueryGetData** can return the query data in the **pData** parameter; otherwise, **pData** is unchanged. The driver can call [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) to indicate the state of the query operation.

The runtime cannot call **QueryGetData** with a predicate that was created with D3D10_QUERY_MISCFLAG_PREDICATEHINT through a call to the [**SetPredication**](nc-d3d10umddi-pfnd3d10ddi_setpredication.md) function.

If a query operation handles work that still resides in partial command buffers, by default, the driver should terminate and submit the partial command buffers. However, the driver should not terminate and submit the buffers if the runtime specified the D3D10_DDI_GET_DATA_DO_NOT_FLUSH flag in the **Flags** parameter. If the runtime passed the D3D10_DDI_GET_DATA_DO_NOT_FLUSH flag in the **Flags** parameter and if the query operation handles work that still resides in partial command buffers, the driver can call [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) to set only the DXGI_DDI_ERR_WASSTILLDRAWING error code.

When the runtime calls **QueryGetData** to check for query completion, the driver can pass DXGI_DDI_ERR_WASSTILLDRAWING in a call to [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) to indicate that the query is not finished yet. The driver can also pass D3DDDIERR_DEVICEREMOVED in a call to **pfnSetErrorCb**. The Direct3D runtime will determine that any other errors are critical.

## -see-also

[**CheckCounter**](nc-d3d10umddi-pfnd3d10ddi_checkcounter.md)

[**D3D10DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10ddi_devicefuncs.md)

[**QueryEnd**](nc-d3d10umddi-pfnd3d10ddi_queryend.md)

[**SetPredication**](nc-d3d10umddi-pfnd3d10ddi_setpredication.md)

[**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md)
