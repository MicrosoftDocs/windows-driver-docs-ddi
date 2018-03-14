---
UID: NC:d3d10umddi.PFND3D10DDI_OPENADAPTER
title: PFND3D10DDI_OPENADAPTER
author: windows-driver-content
description: The OpenAdapter10 function creates a graphics adapter object that is referenced in subsequent calls.
old-location: display\openadapter10.htm
old-project: display
ms.assetid: 50c10021-2bad-4e3c-99cc-24cf31fbc95d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OpenAdapter10, OpenAdapter10 callback function [Display Devices], PFND3D10DDI_OPENADAPTER, UserModeDisplayDriverDx10_Functions_686164e4-0e8b-40ab-8095-cdc3efb34866.xml, d3d10umddi/OpenAdapter10, display.openadapter10
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	OpenAdapter10
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_OPENADAPTER callback


## -description


The <i>OpenAdapter10</i> function creates a graphics adapter object that is referenced in subsequent calls. 


## -prototype


````
PFND3D10DDI_OPENADAPTER OpenAdapter10;

HRESULT APIENTRY OpenAdapter10(
  _Inout_ D3D10DDIARG_OPENADAPTER *pOpenData
)
{ ... }
````


## -parameters




### -param *








#### - pOpenData [in, out]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_openadapter.md">D3D10DDIARG_OPENADAPTER</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.


## -returns



<i>OpenAdapter10</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter object was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>OpenAdapter10</i> could not allocate memory that was required for it to complete.

</td>
</tr>
</table>
 




## -remarks



The graphics adapter object that is created by the <i>OpenAdapter10</i> function represents the underlying graphics hardware. Before the Direct3D runtime can create a display device by calling <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>, the user-mode display driver should call the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a> function to query for the graphics hardware capabilities from the display miniport driver. 

The Direct3D runtime can open multiple graphics adapter objects from a single graphics adapter.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_openadapter.md">D3D10DDIARG_OPENADAPTER</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



 

 


