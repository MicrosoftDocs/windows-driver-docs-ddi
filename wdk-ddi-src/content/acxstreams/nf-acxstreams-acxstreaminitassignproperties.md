---
UID: NF:acxstreams.AcxStreamInitAssignProperties
tech.root: audio
title: AcxStreamInitAssignProperties
ms.date: 02/02/2022
targetos: Windows
description: The AcxStreamInitAssignProperties function assigns an array of properties to a stream, device and circuit using an ACXSTREAM_INIT object.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
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
 - HeaderDef 
api_location:
 - acxstreams.h
api_name:
 - AcxStreamInitAssignProperties
f1_keywords:
 - AcxStreamInitAssignProperties
 - acxstreams/AcxStreamInitAssignProperties
dev_langs:
 - c++
---

## -description

The AcxStreamInitAssignProperties function assigns an array of properties to a stream, device and circuit using an *ACXSTREAM_INIT* object.

## -parameters

### -param StreamInit

Defined by a ACXSTREAM_INIT object, that is used to define the stream initialization. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Properties

An array of [ACX_PROPERTY_ITEM structure](..\acxrequest\ns-acxrequest-acx_property_item.md) that describe the requested property set, properties and flags.

### -param PropertiesCount

A one based count of the number of Properties in the Properties array.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).


## -remarks

### Example

Example usage is shown below.

```cpp

static ACX_PROPERTY_ITEM StreamProperties[] =
{
    {
        &KSPROPSETID_DrmAudioStream,
        KSPROPERTY_DRMAUDIOSTREAM_CONTENTID,
        ACX_PROPERTY_ITEM_FLAG_SET,
        HDACodec_EvtStreamSetContentId,
        NULL,  // Reserved
        sizeof(KSP_DRMAUDIOSTREAM_CONTENTID) - sizeof(KSPROPERTY), // ControlCb
        sizeof(KSDRMAUDIOSTREAM_CONTENTID), // ValueCb
    }, 
};

static ULONG StreamPropertiesCount = SIZEOF_ARRAY(StreamProperties);

    status = AcxStreamInitAssignProperties(StreamInit,
                                           StreamProperties,
                                           StreamPropertiesCount);
```

## -see-also

- [acxstreams.h header](index.md)

TBD - Please review this topic