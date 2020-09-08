---
UID: NC:d3d10umddi.PFND3D10DDI_QUERYBEGIN
title: PFND3D10DDI_QUERYBEGIN (d3d10umddi.h)
description: The QueryBegin function marks the beginning of a sequence of graphics commands for a query and transitions the query to the "building" state.
old-location: display\querybegin.htm
ms.assetid: 2f0a7462-83a6-47df-b5f6-b3706b875349
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_QUERYBEGIN callback function"]
ms.keywords: PFND3D10DDI_QUERYBEGIN, PFND3D10DDI_QUERYBEGIN callback, QueryBegin, QueryBegin callback function [Display Devices], UserModeDisplayDriverDx10_Functions_d456daf9-09b9-4174-8eba-7591ec45cd20.xml, d3d10umddi/QueryBegin, display.querybegin
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_QUERYBEGIN
 - d3d10umddi/PFND3D10DDI_QUERYBEGIN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - QueryBegin
---

# PFND3D10DDI_QUERYBEGIN callback function


## -description

The *QueryBegin* function marks the beginning of a sequence of graphics commands for a query and transitions the query to the "building" state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hQuery* [in]

A handle to the query object to begin.

## -remarks

The driver can use the [pfnSetErrorCb](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb) callback function to set an error code.

The driver is not required to support the *QueryBegin* function for a D3D10DDI_QUERY_EVENT or D3D10DDI_QUERY_TIMESTAMP query operation. Such a query operation has an implied beginning.

The Microsoft Direct3D runtime cannot call *QueryBegin* on a predicate that is currently bound to the pipeline through a call to the [SetPredication](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setpredication) function.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the [pfnSetErrorCb](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb) function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of *QueryBegin* (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

[D3D10DDI_DEVICEFUNCS](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs)

[QueryEnd](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_queryend)

[SetPredication](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setpredication)

[pfnSetErrorCb](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb)

