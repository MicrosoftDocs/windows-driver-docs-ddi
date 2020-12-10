---
UID: NS:iddcx.IDARG_IN_SETSRMLIST
title: IDARG_IN_SETSRMLIST
ms.date: 10/02/2020
tech.root: display
ms.topic: language-reference
targetos: Windows
description: IDARG_IN_SETSRMLIST is the input structure for IddCxMonitorSetSrmList.
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
 - IDARG_IN_SETSRMLIST
f1_keywords:
 - iddcx/IDARG_IN_SETSRMLIST
dev_langs:
 - c++
---

# IDARG_IN_SETSRMLIST structure

## -description

**IDARG_IN_SETSRMLIST** is the input structure for [**IddCxMonitorSetSrmList**](nf-iddcx-iddcxmonitorsetsrmlist.md).

## -struct-fields

### -field SrmListSizeInBytes

[in] The size, in bytes, of the buffer pointed to by **pSrmList**.

### -field pSrmList

[in] Pointer to a buffer that holds the SRM list to pass to the appropriate WDDM driver. This buffer should contain the SRM in the format required by the Digital Content Protection LLC for HDCP.

## -remarks

## -see-also

[**IddCxMonitorSetSrmList**](nf-iddcx-iddcxmonitorsetsrmlist.md)
