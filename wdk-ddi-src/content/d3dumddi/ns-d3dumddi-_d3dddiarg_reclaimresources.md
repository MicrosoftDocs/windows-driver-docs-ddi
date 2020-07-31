---
UID: NS:d3dumddi._D3DDDIARG_RECLAIMRESOURCES
title: _D3DDDIARG_RECLAIMRESOURCES (d3dumddi.h)
description: Describes video memory resources that are to be reclaimed and that the user-mode display driver previously offered for reuse. Used with the ReclaimResources function.
old-location: display\d3dddiarg_reclaimresources.htm
tech.root: display
ms.assetid: 58e8738c-b10a-4c93-b179-03efcb65412d
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_RECLAIMRESOURCES structure"]
ms.keywords: D3DDDIARG_RECLAIMRESOURCES, D3DDDIARG_RECLAIMRESOURCES structure [Display Devices], _D3DDDIARG_RECLAIMRESOURCES, d3dumddi/D3DDDIARG_RECLAIMRESOURCES, display.d3dddiarg_reclaimresources
f1_keywords:
 - "d3dumddi/D3DDDIARG_RECLAIMRESOURCES"
 - "D3DDDIARG_RECLAIMRESOURCES"
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dumddi.h
api_name:
- D3DDDIARG_RECLAIMRESOURCES
targetos: Windows
req.typenames: D3DDDIARG_RECLAIMRESOURCES
---

# _D3DDDIARG_RECLAIMRESOURCES structure


## -description


Describes video memory resources that are to be reclaimed and that the user-mode display driver  previously offered  for reuse. Used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimresources">ReclaimResources</a> function.


## -struct-fields




### -field pResources

[in] A pointer to an array of handles to the resources that are to be reclaimed.


### -field pDiscarded

[out] An optional array of Boolean values that specify whether each resource or allocation was discarded.

Each Boolean value in this array corresponds to a resource at the same index location in the structure pointed to by <b>pResources</b>.

The driver sets each Boolean value to <b>TRUE</b> if the corresponding resource was discarded, or to <b>FALSE</b> if not.

If <b>pDiscarded</b> is <b>NULL</b>, the driver can ignore it.


### -field Resources

[in] The number of elements in the arrays pointed to by <b>pResources</b> and <b>pDiscarded</b>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimresources">ReclaimResources</a>
 

 

