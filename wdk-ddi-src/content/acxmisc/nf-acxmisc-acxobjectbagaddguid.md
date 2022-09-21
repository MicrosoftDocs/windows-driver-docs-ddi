---
UID: NF:acxmisc.AcxObjectBagAddGuid
tech.root: audio
title: AcxObjectBagAddGuid
ms.date: 06/17/2022
targetos: Windows
description: The AcxObjectBagAddGuid function adds Guid data to an existing, intialized AcxObjectBag. 
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
 - AcxObjectBagAddGuid
f1_keywords:
 - AcxObjectBagAddGuid
 - acxmisc/AcxObjectBagAddGuid
dev_langs:
 - c++
---

## -description

The AcxObjectBagAddGuid function adds Guid data to an existing, intialized AcxObjectBag. 

## -parameters

### -param ObjectBag

An intialized ObjectBag ACX object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ValueName

The name of the value that will be used to access the value.

### -param Value

The Value to be added to the ObjectBag.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

The code below shows the use of AcxObjectBagAddGuid.

```cpp
    // Object bag
    //
    // This obj-bag config setting is shared by all composite/circuit templates.
    ACX_OBJECTBAG_CONFIG objBagCfg;
    ACX_OBJECTBAG_CONFIG_INIT(&objBagCfg);

    WDF_OBJECT_ATTRIBUTES attributes;
    WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
    attributes.ParentObject = AcxGetManager(NULL);

    ACXOBJECTBAG objBag = NULL;
    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagCreate(&attributes, &objBagCfg, &objBag));

    // Enable deletion of the object bag when the function completes and goes out of scope
    auto objBag_scope = scope_exit([&objBag]() {
        if (objBag != NULL)
        {
            WdfObjectDelete(objBag);
        }
    });

    //
    // Add a test unsigned int 4 bytes to the object bag
    //
    RETURN_NTSTATUS_IF_FAILED(ObjBagAddTestUI4(objBag, 0));

    //
    // Add unique circuit ID to the object bag
    // This unique Id will be picked up by DSP circuit
    //
    DECLARE_CONST_ACXOBJECTBAG_SYSTEM_PROPERTY_NAME(UniqueID);
    GUID uniqueID = { 0 };
    RETURN_NTSTATUS_IF_FAILED(RtlGUIDFromString(&circuit_IDs[compositeType], &uniqueID));

    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagAddGuid(objBag, &UniqueID, uniqueID));
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmisc.h header](index.md)
