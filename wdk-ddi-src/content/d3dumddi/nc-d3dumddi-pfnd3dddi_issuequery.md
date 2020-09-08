---
UID: NC:d3dumddi.PFND3DDDI_ISSUEQUERY
title: PFND3DDDI_ISSUEQUERY (d3dumddi.h)
description: The IssueQuery function processes a query.
old-location: display\issuequery.htm
tech.root: display
ms.assetid: e31b2b6a-3721-472a-8044-6516a8419ad3
ms.date: 05/10/2018
keywords: ["PFND3DDDI_ISSUEQUERY callback function"]
ms.keywords: IssueQuery, IssueQuery callback function [Display Devices], PFND3DDDI_ISSUEQUERY, PFND3DDDI_ISSUEQUERY callback, UserModeDisplayDriver_Functions_59755967-2a97-4c5c-9210-c4e85cdcdd38.xml, d3dumddi/IssueQuery, display.issuequery
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
 - PFND3DDDI_ISSUEQUERY
 - d3dumddi/PFND3DDDI_ISSUEQUERY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - IssueQuery
product:
 - Windows
---

# PFND3DDDI_ISSUEQUERY callback function


## -description

The <i>IssueQuery</i> function processes a query.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_issuequery">D3DDDIARG_ISSUEQUERY</a> structure that describes how to process the query.

## -returns

<i>IssueQuery</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The query is successfully processed.|
|E_OUTOFMEMORY|IssueQuery could not allocate the required memory for it to complete.|

## -remarks

The user-mode display driver should set a fence value and store the fence value in the driver's private query structure. The user-mode display driver implements the query by using a fence. If the <i>IssueQuery</i> function is called on a query again before a previous query issue completes, the driver should overwrite the fence value and ignore the previous query issue.

If the call to <i>IssueQuery</i> requires the driver to return data, the driver should insert a graphics processing unit (GPU) instruction to write the required data to an allocation. In the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getquerydata">GetQueryData</a> function, the driver should typically lock the allocation and return the appropriate data.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createquery">CreateQuery</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_issuequery">D3DDDIARG_ISSUEQUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getquerydata">GetQueryData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>

