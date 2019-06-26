---
UID: NC:d3d10umddi.PFND3D10DDI_OPENADAPTER
title: PFND3D10DDI_OPENADAPTER (d3d10umddi.h)
description: The OpenAdapter10 function creates a graphics adapter object that is referenced in subsequent calls.
old-location: display\openadapter10.htm
ms.assetid: 50c10021-2bad-4e3c-99cc-24cf31fbc95d
ms.date: 05/10/2018
ms.keywords: OpenAdapter10, OpenAdapter10 callback function [Display Devices], PFND3D10DDI_OPENADAPTER, PFND3D10DDI_OPENADAPTER callback, UserModeDisplayDriverDx10_Functions_686164e4-0e8b-40ab-8095-cdc3efb34866.xml, d3d10umddi/OpenAdapter10, display.openadapter10
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Universal
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- OpenAdapter10
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_OPENADAPTER callback function


## -description


The <i>OpenAdapter10</i> function creates a graphics adapter object that is referenced in subsequent calls. 


## -parameters




### -param *

*pOpenData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_openadapter">D3D10DDIARG_OPENADAPTER</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.


## -returns



<i>OpenAdapter10</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The graphics adapter object was successfully created. | 
| **E_OUTOFMEMORY** | OpenAdapter10 could not allocate memory that was required for it to complete. | 


## -remarks



The graphics adapter object that is created by the <i>OpenAdapter10</i> function represents the underlying graphics hardware. Before the Direct3D runtime can create a display device by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>, the user-mode display driver should call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a> function to query for the graphics hardware capabilities from the display miniport driver. 

The Direct3D runtime can open multiple graphics adapter objects from a single graphics adapter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_openadapter">D3D10DDIARG_OPENADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a>
 

 

