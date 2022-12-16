---
UID: NE:acxrequest._ACX_METHOD_VERB
tech.root: audio
title: ACX_METHOD_VERB
ms.date: 07/26/2022
targetos: Windows
description: The ACX_METHOD_VERB structure describes the type of verb operations suppored on ACX methods.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxrequest.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxrequest.h
api_name:
 - _ACX_METHOD_VERB
 - PACX_METHOD_VERB
 - ACX_METHOD_VERB
f1_keywords:
 - _ACX_METHOD_VERB
 - acxrequest/_ACX_METHOD_VERB
 - PACX_METHOD_VERB
 - acxrequest/PACX_METHOD_VERB
 - ACX_METHOD_VERB
 - acxrequest/ACX_METHOD_VERB
dev_langs:
 - c++
---

## -description

The **ACX_METHOD_VERB** enumeration describes the type of verb operations suppored on ACX methods.

## -enum-fields

### -field AcxMethodVerbNone

No verb support.

### -field AcxMethodVerbSend

Verb send support.

### -field AcxMethodVerbBasicSupport

Basic Verb support.

### -field AcxMethodVerbSetSupport

Set Verb support.

### -field AcxMethodVerbMax

For internal validation, do not use.

## -remarks

### Example

Example usage is shown below.

Sample pending.

```cpp

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)
