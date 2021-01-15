---
UID: NS:iddcx.IDARG_OUT_GETSRMLISTVERSION
title: IDARG_OUT_GETSRMLISTVERSION
ms.date: 10/02/2020
tech.root: display
ms.topic: language-reference
targetos: Windows
description: IDARG_OUT_GETSRMLISTVERSION is the output structure for IddCxMonitorGetSrmListVersion.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10
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
 - IDARG_OUT_GETSRMLISTVERSION
f1_keywords:
 - IDARG_OUT_GETSRMLISTVERSION
 - iddcx/IDARG_OUT_GETSRMLISTVERSION
dev_langs:
 - c++
---

# IDARG_OUT_GETSRMLISTVERSION structure


## -description

**IDARG_OUT_GETSRMLISTVERSION** is the output structure for [**IddCxMonitorGetSrmListVersion**](nf-iddcx-iddcxmonitorgetsrmlistversion.md).

## -struct-fields

### -field SrmListVersionBufferOutputCount

[out] If **[IDARG_IN_GETSRMLISTVERSION](ns-iddcx-idarg_in_getsrmlistversion.md).pSrmListVersion** is NULL, the OS will set **SrmListVersionBufferOutputCount** to the size, in bytes, of the buffer needed to read the SRM list version description. If **IDARG_IN_GETSRMLISTVERSION.pSrmListVersion** is non-NULL, then **SrmListVersionBufferOutputCount** is the number of bytes returned in **IDARG_IN_GETSRMLISTVERSION.pSrmListVersion** buffer. If there was no SRM list set, the OS will set **SrmListVersionBufferOutputCount** to zero.

## -remarks

## -see-also

[**IDARG_IN_GETSRMLISTVERSION**](ns-iddcx-idarg_in_getsrmlistversion.md)

[**IddCxMonitorGetSrmListVersion**](nf-iddcx-iddcxmonitorgetsrmlistversion.md)

