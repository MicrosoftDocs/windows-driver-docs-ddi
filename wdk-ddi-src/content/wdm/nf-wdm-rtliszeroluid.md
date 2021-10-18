---
UID: NF:wdm.RtlIsZeroLuid
tech.root: 
title: RtlIsZeroLuid
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: RtlIsZeroLuid"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - RtlIsZeroLuid
f1_keywords:
 - RtlIsZeroLuid
 - wdm/RtlIsZeroLuid
dev_langs:
 - c++
---

## -description

The **RtlIsZeroLuid** macro determines if the specified LUID is the zero LUID.

## -parameters

### -param L1

[in]
Specifies the [**LUID**](/windows/win32/api/ntdef/ns-ntdef-luid) to check.

## -remarks

**RtlIsZeroLuid** returns **TRUE** if _L1_ is zero, and returns **FALSE** otherwise.
