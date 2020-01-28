---
UID: NF:wiamdef.wiasUpdateScanRect
title: wiasUpdateScanRect function (wiamdef.h)
description: The wiasUpdateScanRect function updates the scanning area sizes of the scanning device.
old-location: image\wiasupdatescanrect.htm
tech.root: image
ms.assetid: f8184ae1-878f-46fc-bddc-66c065bc9e75
ms.date: 05/03/2018
ms.keywords: image.wiasupdatescanrect, wiamdef/wiasUpdateScanRect, wiasFncs_ef2b5686-5026-469b-8133-d2c37fddb732.xml, wiasUpdateScanRect, wiasUpdateScanRect function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasUpdateScanRect"
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasUpdateScanRect
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasUpdateScanRect function


## -description


The <b>wiasUpdateScanRect</b> function updates the scanning area sizes of the scanning device.


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param pContext [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_context">WIA_PROPERTY_CONTEXT</a> structure containing the property context, created by a prior call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiascreatepropcontext">wiasCreatePropContext</a>.


### -param lWidth

Specifies the horizontal width of the scanning area of the scanning device, in units of thousandths of an inch. Normally, this is the horizontal bed size.


### -param lHeight

Specifies the vertical height of the scanning area of the scanning device, in units of thousandths of an inch. Normally, this is the vertical bed size.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -remarks



This helper method is called to update the properties making up the scan rectangle. The appropriate changes are made to the properties that are dependent on those that make up the scan rectangle. For example, a change in horizontal resolution affects the horizontal extent. This function assumes that the valid values for the vertical and horizontal extents, and vertical and horizontal positions have not yet been updated. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_context">WIA_PROPERTY_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiascreatepropcontext">wiasCreatePropContext</a>
 

 

