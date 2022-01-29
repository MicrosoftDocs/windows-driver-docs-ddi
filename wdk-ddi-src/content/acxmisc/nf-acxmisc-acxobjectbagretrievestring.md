---
UID: NF:acxmisc.AcxObjectBagRetrieveString
tech.root: audio
title: AcxObjectBagRetrieveString
ms.date: 01/28/2022
targetos: Windows
description: The AcxObjectBagRetrieveString function retrieves a string value from an existing, intialized AcxObjectBag that contains values. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmisc.h
req.idl: 
req.include-header: 
req.irql: 
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
 - AcxObjectBagRetrieveString
f1_keywords:
 - AcxObjectBagRetrieveString
 - acxmisc/AcxObjectBagRetrieveString
dev_langs:
 - c++
---

## -description

The AcxObjectBagRetrieveString function retrieves a string value from an existing, intialized AcxObjectBag that contains values. 
 
## -parameters

### -param ObjectBag

An intialized ObjectBag ACX object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ValueName

The name of the value that will be used to access the value.

### -param Value

The  WDFSTRING object value to be retrieved from the ObjectBag.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This example shows the use of AcxObjectBagRetrieveString.

```cpp
    status = RtlUnicodeStringInit(&usName, inParams->ValueName);
    if (!NT_SUCCESS(status))
    {
        DrvLogError(g_RecorderLog, FLAG_DDI, 
                    "WDFDEVICE %p, RtlUnicodeStringInit(%S) failed, %!STATUS!", 
                    m_Device, inParams->ValueName, status);
        goto exit;
    }

    //
    // Set the specified property.
    //
    switch(inParams->ValueType)
    {
    case REG_SZ:
        //
        // Create an empty WDF string to get the value.
        //
        status = WdfStringCreate(nullptr, nullptr, &wsValue);
        if (!NT_SUCCESS(status))
        {
            DrvLogError(g_RecorderLog, FLAG_DDI, 
                        "WDFDEVICE %p, WdfStringCreate failed, %!STATUS!", 
                        m_Device, status);
            goto exit;
        }

        //
        // Get the string value from bag.
        //
        status = AcxObjectBagRetrieveString(objBag, &usName, wsValue);
```

## -see-also

[acxmisc.h header](index.md)

