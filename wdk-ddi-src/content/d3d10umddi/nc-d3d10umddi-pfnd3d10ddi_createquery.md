---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEQUERY
title: PFND3D10DDI_CREATEQUERY (d3d10umddi.h)
description: The CreateQuery(D3D10) function creates a query.
old-location: display\createquery_d3d10_.htm
ms.assetid: abe6a82f-1613-4c74-9e81-01939db74bfd
ms.date: 05/10/2018
ms.keywords: CreateQuery, CreateQuery callback function [Display Devices], PFND3D10DDI_CREATEQUERY, PFND3D10DDI_CREATEQUERY callback, UserModeDisplayDriverDx10_Functions_faa26999-d692-40b4-81ef-99c730879b49.xml, d3d10umddi/CreateQuery, display.createquery_d3d10_
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CreateQuery
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_CREATEQUERY callback function


## -description


The <b>CreateQuery(D3D10)</b> function creates a query.


## -parameters


### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pCreateQuery* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541685">D3D10DDIARG_CREATEQUERY</a> structure that describes the parameters that the user-mode display driver uses to create a query. 

### -param Arg2

*hQuery* [in]

A handle to the driver's private data for the query. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/59a59aa8-085e-4bf8-8a6f-e08f2aecd894">CalcPrivateQuerySize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its query object.

### -param Arg3

*hRTQuery* [in]

A handle to the query that the driver should use anytime it calls back into the Direct3D runtime. 



## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver might run out of memory or be unable to create queries because of their exclusive nature. Therefore, the driver can pass E_OUTOFMEMORY, DXGI_DDI_ERR_NONEXCLUSIVE, or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/74bb85df-6d64-49e8-b431-2f4a9954eff2">DestroyQuery(D3D10)</a> function to destroy the handle that the <i>hQuery</i> parameter specifies.




## -see-also




<a href="https://msdn.microsoft.com/59a59aa8-085e-4bf8-8a6f-e08f2aecd894">CalcPrivateQuerySize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541685">D3D10DDIARG_CREATEQUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/74bb85df-6d64-49e8-b431-2f4a9954eff2">DestroyQuery(D3D10)</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

