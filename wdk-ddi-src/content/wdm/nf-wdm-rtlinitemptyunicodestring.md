---
UID: NF:wdm.RtlInitEmptyUnicodeString
tech.root: 
title: RtlInitEmptyUnicodeString
ms.date: 07/16/2021
targetos: Windows
description: 
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
req.target-min-winverclnt: Windows XP
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
 - RtlInitEmptyUnicodeString
f1_keywords:
 - RtlInitEmptyUnicodeString
 - wdm/RtlInitEmptyUnicodeString
dev_langs:
 - c++
---

## -description

The **RtlInitEmptyUnicodeString** macro initializes an empty counted Unicode string.

## -parameters

### -param UnicodeString

[out]
Pointer to the [**UNICODE_STRING**](/windows-hardware/drivers/ddi/wudfwdm/ns-wudfwdm-_unicode_string) structure to be initialized.

### -param Buffer

[in]
Pointer to a caller-allocated buffer to be used to contain a WCHAR string.

### -param BufferSize

[in]
Length, in bytes, of the buffer that _Buffer_ points to.

## -remarks

The members of the structure that the _DestinationString_ parameters points to are initialized as follows.

*   **Length**. Zero.

*   **MaximumLength**. _BufferSize_.

*   **Buffer**. _SourceString_.

To initialize a non-empty counted Unicode string, call [**RtlInitUnicodeString**](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring).

