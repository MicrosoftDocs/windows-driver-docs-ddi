---
UID: NS:dispmprt._DXGK_MITIGATEDRANGEINFO
title: _DXGK_MITIGATEDRANGEINFO
description: The list of pages in the virtual function’s BARs that need to be mitigated.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGK_MITIGATEDRANGEINFO structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_MITIGATEDRANGEINFO, DXGK_MITIGATEDRANGEINFO, *PDXGK_MITIGATEDRANGEINFO,
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_MITIGATEDRANGEINFO, *PDXGK_MITIGATEDRANGEINFO
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGK_MITIGATEDRANGEINFO
 - dispmprt/_DXGK_MITIGATEDRANGEINFO
 - PDXGK_MITIGATEDRANGEINFO
 - dispmprt/PDXGK_MITIGATEDRANGEINFO
 - DXGK_MITIGATEDRANGEINFO
 - dispmprt/DXGK_MITIGATEDRANGEINFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_MITIGATEDRANGEINFO
 - PDXGK_MITIGATEDRANGEINFO
 - DXGK_MITIGATEDRANGEINFO
product:
 - Windows
dev_langs:
 - c++
---

# _DXGK_MITIGATEDRANGEINFO structure


## -description

The list of pages in the virtual function’s BARs that need to be mitigated.

## -struct-fields

### -field BasePageNumber

Offset of the range from the beginning of the BAR.

### -field PageCount

Number of pages in the range. A mitigated range size should not exceed 2 GB. When the driver needs to mitigate a range, which is bigger than 2GB, it needs to report multiple consecutive ranges. There is no limit on the number of mitigate ranges the driver can report.

### -field InterceptReads

Set this to TRUE to mitigate reads to the range.

### -field InterceptWrites

 
Set this to TRUE to mitigates writes to the range.

## -remarks

## -see-also

