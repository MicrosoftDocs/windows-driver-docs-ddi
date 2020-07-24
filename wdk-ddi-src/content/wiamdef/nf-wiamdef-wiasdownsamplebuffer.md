---
UID: NF:wiamdef.wiasDownSampleBuffer
title: wiasDownSampleBuffer function (wiamdef.h)
description: The wiasDownSampleBuffer function takes in a buffer of DWORD-aligned pixel data and downsamples it (produces image data of lower resolution) to the specified size and resolution.
old-location: image\wiasdownsamplebuffer.htm
tech.root: image
ms.assetid: 4581b852-f539-4cad-93fd-2638c885c2e7
ms.date: 05/03/2018
keywords: ["wiasDownSampleBuffer function"]
ms.keywords: image.wiasdownsamplebuffer, wiamdef/wiasDownSampleBuffer, wiasDownSampleBuffer, wiasDownSampleBuffer function [Imaging Devices], wiasFncs_a109a3d9-e801-4332-bc89-65432023eecb.xml
f1_keywords:
 - "wiamdef/wiasDownSampleBuffer"
 - "wiasDownSampleBuffer"
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
- wiasDownSampleBuffer
targetos: Windows
req.typenames: 
---

# wiasDownSampleBuffer function

## -description

The **wiasDownSampleBuffer** function takes in a buffer of DWORD-aligned pixel data and downsamples it (produces image data of lower resolution) to the specified size and resolution.

## -parameters

### -param lFlags

Specifies a set of flags that determine the behavior of this function. Currently, only the following flag is defined.

| Flag | Meaning |
| --- | --- |
| **WIAS_GET_DOWNSAMPLED_SIZE_ONLY** | Do not copy the downsampled data to the destination buffer. Instead, set the following members of the [WIAS_DOWN_SAMPLE_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wias_down_sample_info) structure: **ulDownSampledHeight**, **ulDownSampleWidth**, **ulAlignedHeight**, **ulAlignedWidth**. |

### -param pInfo [in, out]

Pointer to the [WIAS_DOWN_SAMPLE_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wias_down_sample_info) structure that contains all of the information needed for the downsampling operation.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](https://docs.microsoft.com/windows/win32/wia/-wia-error-codes).

## -remarks

The **wiasDownSampleBuffer** function can be used in either of the following two ways:

- The caller specifies the downsampled (that is, output) width and height by setting the **ulDownSampledWidth** and **ulDownSampledHeight** members of the **WIA_DOWN_SAMPLE_INFO** structure.

- The caller sets the **ulDownSampledWidth** and **ulDownSampledHeight** members of the **WIA_DOWN_SAMPLE_INFO** structure to zero, indicating that the function should choose the output width and height.

To see what output width and height values the function chooses, call this function with the *lFlags* parameter set to **WIAS_GET_DOWNSAMPLED_SIZE_ONLY**. On return, the **ulDownSampledWidth** and **ulDownSampledHeight** members are set to their new values. No downsampling is performed in this case.

The caller of this function is required to fill in the following members of the **WIA_DOWN_SAMPLE_INFO** structure:

- **ulOriginalWidth**
- **ulOriginal Height**
- **ulBitsPerPixel**
- **ulXRes**
- **ulYRes**
- **pSrcBuffer**

> [!NOTE]
> The **wiasDownSampleBuffer** function expects **ulBitsPerPixel** to be 1, 8, or 24, corresponding to 1-, 8-, and 24-bit-per-pixel data. The caller can also specify the size of the downsampled data by filling in the following **WIA_DOWN_SAMPLE_INFO** structure members: - **ulDownSampledWidth** **ulDownSampledHeight**

If the buffer that receives the downsampled data has already been allocated, the caller should fill in these **WIA_DOWN_SAMPLE_INFO** structure members:

- **ulDestBufSize**
- **ulSrcBufSize**
- **pDestBuffer**

If the caller sets **pDestBuffer** to **NULL**, the destination buffer is allocated by the WIA service. On return from this function, **pDestBuffer** points to the destination buffer. The caller is responsible for freeing this memory when the operation is finished, and does this by calling [**CoTaskMemFree**](https://docs.microsoft.com/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree) on the buffer.

Because this function is not able to produce partial output lines, the number of scan lines in the input buffer must be an integer multiple of the scaling factor. For example, suppose the input buffer contains an image sampled at 600 dpi, which you intend to downsample to an equivalent 50 dpi image. In this case, you are scaling down the original image by a factor of 12 (because 600 / 50 = 12). This means that the function must receive 12 input lines for each output line that it produces.

If the original image has a resolution of R*in* dpi, and is to be scaled down to an image with a resolution of R*out* dpi, the scale-down factor is R*in* / R*out*, and the number of lines in the input buffer should be a multiple of R*in* / R*out*. If the scan head reaches the last band of the original image, and there are too few scan lines in the input buffer to produce an output line, pad the input buffer so that it contains the required number of data lines. Failure to do so causes unpredictable results, and can even result in a driver crash.

## -see-also

[WIAS_DOWN_SAMPLE_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wias_down_sample_info)
