---
UID: NS:iddcx.IDARG_IN_GETSRMLISTVERSION
title: IDARG_IN_GETSRMLISTVERSION
ms.date: 10/02/2020
tech.root: display
ms.topic: language-reference
targetos: Windows
description: IDARG_IN_GETSRMLISTVERSION is an input structure for IddCxMonitorGetSrmListVersion.
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
 - IDARG_IN_GETSRMLISTVERSION
f1_keywords:
 - iddcx/IDARG_IN_GETSRMLISTVERSION
dev_langs:
 - c++
---

# IDARG_IN_GETSRMLISTVERSION structure

## -description

**IDARG_IN_GETSRMLISTVERSION** is an input structure for [**IddCxMonitorGetSrmListVersion**](nf-iddcx-iddcxmonitorgetsrmlistversion.md).

## -struct-fields

### -field SrmListVersionBufferInputCount

[in] Size in bytes of the buffer being passed by the driver to the OS through **pSrmListVersion**. A value of zero indicates that the driver is simply querying the size of the SRM list version buffer that should be provided by the driver. In this case, the OS will set the buffer size in the output structure.

Either **SrmListVersionBufferInputCount** needs to be zero and **pSrmListVersion** set to null, or **SrmListVersionBufferInputCount** needs to be non-zero and **pSrmListVerion** needs to be non-null.

### -field pSrmListVersion

Pointer to a buffer in which the OS should copy the SRM list version if the value is non-NULL. In this case, the format of the version is defined by the PlayReady Porting Kit 4.0.

If **pSrmListVersion** is NULL then the OS will not copy any data and will set the value **[IDARG_OUT_GETSRMLISTVERSION](ns-iddcx-idarg_out_getsrmlistversion.md).SrmListVersionBufferOutputCount** to indicate the size of buffer required to store the SRM list version.

## -remarks

## -see-also

[**IDARG_OUT_GETSRMLISTVERSION**](ns-iddcx-idarg_out_getsrmlistversion.md)

[**IddCxMonitorGetSrmListVersion**](nf-iddcx-iddcxmonitorgetsrmlistversion.md)
