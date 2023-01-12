---
UID: NF:acxmisc.AcxObjectBagAddUnicodeString
tech.root: audio
title: AcxObjectBagAddUnicodeString
ms.date: 12/16/2022
targetos: Windows
description: The AcxObjectBagAddUnicodeString function adds a unicode string to and existing, initialized AcxObjectBag.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmisc.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - LibDef
api_location:
 - acxmisc.h
api_name:
 - AcxObjectBagAddUnicodeString
f1_keywords:
 - AcxObjectBagAddUnicodeString
 - acxmisc/AcxObjectBagAddUnicodeString
dev_langs:
 - c++
---

## -description

The AcxObjectBagAddUnicodeString function adds a unicode string to and existing, initialized AcxObjectBag.

## -parameters

### -param ObjectBag

An initialized ObjectBag ACX object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ValueName

The name of the value that will be used to access the value.

### -param Value

The UNICODE_STRING Value to be added to the ObjectBag.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This example shows the use of AcxObjectBagAddUnicodeString.

```cpp
    _In_ ACXOBJECTBAG               ObjBag,
    _In_ UNICODE_STRING             FriendlyNameStr,
    _In_ UNICODE_STRING             NameStr
)
{
    PAGED_CODE();

    NTSTATUS status = STATUS_SUCCESS;

    DECLARE_CONST_ACXOBJECTBAG_SYSTEM_PROPERTY_NAME(FriendlyName);
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagAddUnicodeString(ObjBag, &FriendlyName, &FriendlyNameStr));
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmisc.h header](index.md)
