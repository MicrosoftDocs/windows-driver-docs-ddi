---
UID: NS:acxrequest._ACX_METHOD_ITEM
tech.root: audio
title: ACX_METHOD_ITEM
ms.date: 07/26/2022
targetos: Windows
description: The ACX_METHOD_ITEM structure describes a method item that is the target of an ACX request.
prerelease: false
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
req.typenames: ACX_METHOD_ITEM, *PACX_METHOD_ITEM
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxrequest.h
api_name:
 - _ACX_METHOD_ITEM
 - PACX_METHOD_ITEM
 - ACX_METHOD_ITEM
f1_keywords:
 - _ACX_METHOD_ITEM
 - acxrequest/_ACX_METHOD_ITEM
 - PACX_METHOD_ITEM
 - acxrequest/PACX_METHOD_ITEM
 - ACX_METHOD_ITEM
 - acxrequest/ACX_METHOD_ITEM
dev_langs:
 - c++
---

## -description

The **ACX_METHOD_ITEM** structure describes a method item that is the target of an ACX request.

## -struct-fields

### -field Set

Specifies a GUID that identifies a KS (kernel streaming) method item set.

### -field Id

Specifies the member of the member set.

### -field Flags

The Flags field can be used to set the following Flags defined in the AcxRequest header.

```cpp

#define ACX_METHOD_ITEM_FLAG_NONE               0x00000000
#define ACX_METHOD_ITEM_FLAG_SEND               0x00000001 // KSMETHOD_TYPE_SEND
#define ACX_METHOD_ITEM_FLAG_BASICSUPPORT       0x00000200 // KSMETHOD_TYPE_BASICSUPPORT

```

### -field EvtAcxObjectProcessRequest

The [EVT_ACX_OBJECT_PROCESS_REQUEST callback](nc-acxrequest-evt_acx_object_process_event_request.md) method handler associated with this item.

### -field Reserved

This field is reserved.

### -field ArgsCb

The minimum count in bytes (size) of the Args buffer. Set to zero if no minimum value.

### -field ResultCb

The minimum count in bytes (size) of the Result buffer. Set to zero if no minimum value.

### -field ResultType

The minimum count in bytes (size) of the Result buffer. Set to zero if there is no minimum value.

## -remarks

### Example

Example usage is shown below.

```cpp

static ACX_METHOD_ITEM CircuitMethods[] =
{
    {
        &KSMETHODSETID_AcxTestMethod,
        KSMETHOD_ACXCIRCUIT_TEST_IN2OUT,
        ACX_METHOD_ITEM_FLAG_SEND,
        Codec_EvtTestIn2OutMethodCallback,
        NULL,               // Reserved
        sizeof(ULONG),      // ArgsCb
        sizeof(ULONG),      // ResultCb
    },
};

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)
