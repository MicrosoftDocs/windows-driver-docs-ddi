---
UID: NS:acxrequest._ACX_PROPERTY_ITEM
tech.root: audio
title: ACX_PROPERTY_ITEM
ms.date: 03/04/2022
targetos: Windows
description: The ACX_PROPERTY_ITEM structure describes the ACX request property item.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxrequest.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_PROPERTY_ITEM, *PACX_PROPERTY_ITEM
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxrequest.h
api_name:
 - _ACX_PROPERTY_ITEM
 - PACX_PROPERTY_ITEM
 - ACX_PROPERTY_ITEM
f1_keywords:
 - _ACX_PROPERTY_ITEM
 - acxrequest/_ACX_PROPERTY_ITEM
 - PACX_PROPERTY_ITEM
 - acxrequest/PACX_PROPERTY_ITEM
 - ACX_PROPERTY_ITEM
 - acxrequest/ACX_PROPERTY_ITEM
dev_langs:
 - c++
---

## -description

The **ACX_PROPERTY_ITEM** structure describes the ACX request property item. A Property represents a capability or control-state setting that belongs to a kernel streaming object, such as a filter or pin. For more information, see [KS Properties](/windows-hardware/drivers/stream/ks-properties).

## -struct-fields

### -field Set

TBD - Specifies a GUID that identifies a kernel streaming property item set. For example, the KSPIN_INTERFACE structure describes a specific interface within an interface set. For more information, see [KSPROPERTY structure](/windows-hardware/drivers/stream/ksproperty-structure).

### -field Id

Specifies the member of the property set. For KSPIN_MEDIUM, identifies a unique connection on the bus. For KSPIN_INTERFACE, specifies the ID number of this particular interface within the interface set. 

### -field Flags

The Flags field is used to set the following Flags defined in the AcxRequest header.

```cpp
#define ACX_PROPERTY_ITEM_FLAG_NONE             0x00000000
#define ACX_PROPERTY_ITEM_FLAG_GET              0x00000001 // KSPROPERTY_TYPE_GET
#define ACX_PROPERTY_ITEM_FLAG_SET              0x00000002 // KSPROPERTY_TYPE_SET
#define ACX_PROPERTY_ITEM_FLAG_BASICSUPPORT     0x00000200 // KSPROPERTY_TYPE_BASICSUPPORT
```

ACX_PROPERTY_ITEM_FLAG_GET - Retrieves the value of the specified property item.

ACX_PROPERTY_ITEM_FLAG_SET - Sets the value of the specified property item.

ACX_PROPERTY_ITEM_FLAG_BASICSUPPORT - Queries the request types that the driver handles for this property item. Returns KSPROPERTY_TYPE_GET or KSPROPERTY_TYPE_SET or both. All property sets must support this flag.


### -field EvtAcxObjectProcessRequest

The [EVT_ACX_OBJECT_PROCESS_REQUEST callback](nc-acxrequest-evt_acx_object_process_event_request.md) associated with this item.

### -field Reserved

This field is reserved.

### -field ControlCb

The count in bytes (size) of the Control.

### -field ValueCb

The count in bytes (size) of the Value.

### -field ValueType

The ValueType field is TBD.

## -remarks

### Example

Example usage is shown below.

```cpp

#define ACX_PROPERTY_ITEM_FLAG_NONE             0x00000000
#define ACX_PROPERTY_ITEM_FLAG_GET              0x00000001 // KSPROPERTY_TYPE_GET
#define ACX_PROPERTY_ITEM_FLAG_SET              0x00000002 // KSPROPERTY_TYPE_SET
#define ACX_PROPERTY_ITEM_FLAG_BASICSUPPORT     0x00000200 // KSPROPERTY_TYPE_BASICSUPPORT

// Stream properties.
// DRM
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

```

## -see-also

[acxrequest.h header](index.md)

