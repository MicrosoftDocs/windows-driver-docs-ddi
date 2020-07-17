---
UID: NC:d3dumddi.PFND3DDDI_GETQUERYDATA
title: PFND3DDDI_GETQUERYDATA (d3dumddi.h)
description: The GetQueryData function retrieves information about a query.
old-location: display\getquerydata.htm
tech.root: display
ms.assetid: 64daec14-8e16-4df3-bb0c-27760223b86c
ms.date: 05/10/2018
keywords: ["PFND3DDDI_GETQUERYDATA callback function"]
ms.keywords: GetQueryData, GetQueryData callback function [Display Devices], PFND3DDDI_GETQUERYDATA, PFND3DDDI_GETQUERYDATA callback, UserModeDisplayDriver_Functions_05870f6b-5971-4201-9910-c8c8c548878a.xml, d3dumddi/GetQueryData, display.getquerydata
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: 
f1_keywords:
 - "d3dumddi/GetQueryData"
 - "GetQueryData"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - GetQueryData
product:
 - Windows
---

# PFND3DDDI_GETQUERYDATA callback function

## -description

The <i>GetQueryData</i> function retrieves information about a query.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getquerydata">D3DDDIARG_GETQUERYDATA</a> structure that contains the information about the query that is retrieved from the driver.

## -returns

<i>GetQueryData</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The query operation completed and the query result is available.|
|S_FALSE|GetQueryData returned successfully. However, the query operation did not complete, so the query result is not available.|
|E_OUTOFMEMORY|GetQueryData could not allocate the required memory for it to complete.|

## -remarks

The Microsoft Direct3D runtime can call <i>GetQueryData</i> at any time after calling the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_issuequery">IssueQuery</a> function. The user-mode display driver should check the current fence value against the value that is stored in the driver's private query structure to determine if the query issue is complete.

If the query is completed, the driver should return S_OK; otherwise, the driver should return S_FALSE. 

If a driver supports <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supporting-multiple-processors">runtime-handled multiple-processor optimizations</a> and exposes a DDI version of 0x0000000B or greater, the runtime will call <i>GetQueryData</i> in a reentrant manner. The driver returns the DDI-version value in the <b>DriverVersion</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_openadapter">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_openadapter">OpenAdapter</a> function. When the runtime calls <i>GetQueryData</i> in a reentrant manner, one thread can execute inside <i>GetQueryData</i> while another thread that references the same display device executes inside of another user-mode display driver function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getquerydata">D3DDDIARG_GETQUERYDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_issuequery">IssueQuery</a>

