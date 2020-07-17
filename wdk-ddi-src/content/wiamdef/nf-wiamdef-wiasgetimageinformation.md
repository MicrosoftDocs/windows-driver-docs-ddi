---
UID: NF:wiamdef.wiasGetImageInformation
title: wiasGetImageInformation function (wiamdef.h)
description: The wiasGetImageInformation function retrieves transfer context information from an item.
old-location: image\wiasgetimageinformation.htm
tech.root: image
ms.assetid: 457c4b98-313d-4b31-aa6c-fb62fea6fc7d
ms.date: 05/03/2018
keywords: ["wiasGetImageInformation function"]
ms.keywords: image.wiasgetimageinformation, wiamdef/wiasGetImageInformation, wiasFncs_6603ae74-b0b9-48f4-9fa9-83cdf3edc1d6.xml, wiasGetImageInformation, wiasGetImageInformation function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasGetImageInformation"
 - "wiasGetImageInformation"
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt:
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
- wiasGetImageInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasGetImageInformation function

## -description

The **wiasGetImageInformation** function retrieves transfer context information from an item.

## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.

### -param lFlags

Specifies operational flags. Currently, only the following flag is defined:

| Flag | Meaning |
| --- | --- |
| WIAS_INIT_CONTEXT | Initialize the MINIDRV_TRANSFER_CONTEXT structure. |

### -param pmdtc [in, out]

Pointer to a [MINIDRV_TRANSFER_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context) structure. Upon return, this structure contains the requested image item information.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](https://docs.microsoft.com/windows/win32/wia/-wia-error-codes).

## -remarks

This function uses a [MINIDRV_TRANSFER_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context) structure to calculate item image and item header sizes. In addition, it can optionally fill in an image header if the image format requires a data header. The header will be copied to the buffer if the **pTransferBuffer** member of the MINIDRV_TRANSFER_CONTEXT structure is not **NULL**. When using image formats (such as JPEG) that do not have a header, the header size in the **lHeaderSize** member of the MINIDRV_TRANSFER_CONTEXT structure is reported as zero.

For image formats where the actual final size of the image is not known until after data acquisition, as with multipage TIFF and compressed formats, the **lItemSize** member of the [MINIDRV_TRANSFER_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context) structure is reported as zero. The **lImageSize** member is reported as the size, in bytes, of the uncompressed image in a single page.

If WIAS_INIT_CONTEXT is specified in the *lFlags* parameter, the MINIDRV_TRANSFER_CONTEXT structure pointed to by the *pmdtc* parameter is filled in with information derived from the item's image properties. This flag should be used when a minidriver has allocated a new context.

## -see-also

[MINIDRV_TRANSFER_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context)
