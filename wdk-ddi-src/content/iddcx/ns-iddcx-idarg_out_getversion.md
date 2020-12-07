---
UID: NS:iddcx.IDARG_OUT_GETVERSION
title: IDARG_OUT_GETVERSION
ms.date: 10/20/2020
ms.topic: language-reference
tech.root: display
targetos: Windows
description: The IDARG_OUT_GETVERSION structure is used to store the IddCx (Indirect Display Driver Class eXtension) version.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_OUT_GETVERSION
f1_keywords:
 - IDARG_OUT_GETVERSION
 - iddcx/IDARG_OUT_GETVERSION
dev_langs:
 - c++
---

## -description

> [!NOTE]
> Some information on this page relates to a pre-released product which may be substantially modified before it is commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

The **IDARG_OUT_GETVERSION** structure identifies the IddCx (Indirect Display Driver Class eXtension) version.

## -struct-fields

### -field IddCxVersion

ULONG value that identifies the IddCx version that the driver is running on. **IddCxVersion** can be one of the following values:

| Value                             | Windows 10 Version |
|-----------------------------------|------------------- |
| IDDCX_VERSION_MANGANESE (0x1600)  | 21H1               |
| IDDCX_VERSION_VIBRAINIUM (0x1500) | 2004               |
| IDDCX_VERSION_19H1 (0x1400)       | 1903               |
| IDDCX_VERSION_RS5 (0x1380)        | 1809               |
| IDDCX_VERSION_RS4 (0x1300)        | 1803               |
| IDDCX_VERSION_RS3 (0x1200)        | 1709               |

## -remarks

An ID driver calls [**IddCxGetVersion**](nf-iddcx-iddcxgetversion.md) to determine the IddCx version that the driver is running on.

## -see-also

[**IddCxGetVersion**](nf-iddcx-iddcxgetversion.md)

[**PFN_IDDCXGETVERSION**](nc-iddcx-pfn_iddcxgetversion.md)
