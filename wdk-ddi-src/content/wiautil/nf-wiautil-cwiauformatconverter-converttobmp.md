---
UID: NF:wiautil.CWiauFormatConverter.ConvertToBmp
title: CWiauFormatConverter::ConvertToBmp (wiautil.h)
description: The CWiauFormatConverter::ConvertToBmp method converts an image to BMP format.
tech.root: image
ms.date: 04/20/2022
keywords: ["CWiauFormatConverter::ConvertToBmp"]
ms.keywords: CWiauFormatConverter interface [Imaging Devices],ConvertToBmp method, CWiauFormatConverter.ConvertToBmp, CWiauFormatConverter::ConvertToBmp, ConvertToBmp, ConvertToBmp method [Imaging Devices], ConvertToBmp method [Imaging Devices],CWiauFormatConverter interface, image.cwiauformatconverter_converttobmp, wiauFncs_2c929e01-3e1f-4a07-9f2f-f50775b39017.xml, wiautil/CWiauFormatConverter::ConvertToBmp
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - CWiauFormatConverter::ConvertToBmp
 - wiautil/CWiauFormatConverter::ConvertToBmp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wiautil.h
api_name:
 - CWiauFormatConverter::ConvertToBmp
---

## -description

The **CWiauFormatConverter::ConvertToBmp** method converts an image to BMP format.

## -parameters

### -param pSource

Points to the memory location containing the first byte of the source image.

### -param iSourceSize

Specifies the size, in bytes, of the source image.

### -param ppDest

Pointer to a memory location that receives the address of the resulting image.

### -param piDestSize

Pointer to a memory location that receives the size, in bytes, of the resulting image.

### -param pBmpImageInfo

Pointer to a [BMP_IMAGE_INFO](./ns-wiautil-_bmp_image_info.md) structure that receives information about the resulting image.

### -param iSkipAmt

Optional

Specifies the amount of the BMP header to skip. The default value of this parameter denotes that none of the BMP header is skipped.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error.

## -remarks

The caller of this method can pass a result buffer in *ppDest* and the size in *piDestSize*.

Alternatively, the caller can set *ppDest* to **NULL** and *piDestSize* to zero in the call to indicate that this method should allocate the memory.

The caller is responsible for freeing the memory using the **delete []** operator.

## -see-also

[BMP_IMAGE_INFO](./ns-wiautil-_bmp_image_info.md)

[CWiauFormatConverter](/previous-versions/windows/hardware/drivers/ff540363(v=vs.85))

[CWiauFormatConverter::IsFormatSupported](./nf-wiautil-cwiauformatconverter-isformatsupported.md)

[SKIP_AMOUNT](./ne-wiautil-skip_amount.md)