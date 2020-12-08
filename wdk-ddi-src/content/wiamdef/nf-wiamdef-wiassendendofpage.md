---
UID: NF:wiamdef.wiasSendEndOfPage
title: wiasSendEndOfPage function (wiamdef.h)
description: The wiasSendEndOfPage function calls the client callback routine during a data transfer, sending the current total page count.
old-location: image\wiassendendofpage.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiasSendEndOfPage function"]
ms.keywords: image.wiassendendofpage, wiamdef/wiasSendEndOfPage, wiasFncs_c8a81130-c832-40d8-8a62-619d04d8d3dc.xml, wiasSendEndOfPage, wiasSendEndOfPage function [Imaging Devices]
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
targetos: Windows
req.typenames: 
f1_keywords:
 - wiasSendEndOfPage
 - wiamdef/wiasSendEndOfPage
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasSendEndOfPage
---

# wiasSendEndOfPage function


## -description

The <b>wiasSendEndOfPage </b>function calls the client callback routine during a data transfer, sending the current total page count.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param lPageCount

Specifies the total page count.

### -param pmdtc 

[in, out]
Pointer to a <a href="/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context">MINIDRV_TRANSFER_CONTEXT</a> structure.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

<a href="/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context">MINIDRV_TRANSFER_CONTEXT</a>
