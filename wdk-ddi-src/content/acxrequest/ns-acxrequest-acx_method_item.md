---
UID: NS:acxrequest._ACX_METHOD_ITEM
tech.root: audio
title: ACX_METHOD_ITEM
ms.date: 03/03/2022
targetos: Windows
description: The ACX_METHOD_ITEM structure describes the method items that can be used in an ACX request.
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

The **ACX_METHOD_ITEM** structure describes the method items that can be used in an ACX request.

## -struct-fields

### -field Set

TBD - A set of methods defined as a KSMethodSet ID.

### -field Id

TBD - The KSMethod ID.

### -field Flags

The Flags field can be used to set the following Flags defined in the AcxRequest header.

```cpp
#define ACX_METHOD_ITEM_FLAG_NONE               0x00000000
#define ACX_METHOD_ITEM_FLAG_SEND               0x00000001 // KSMETHOD_TYPE_SEND
#define ACX_METHOD_ITEM_FLAG_BASICSUPPORT       0x00000200 // KSMETHOD_TYPE_BASICSUPPORT
```

### -field EvtAcxObjectProcessRequest

The [EVT_ACX_OBJECT_PROCESS_REQUEST callback](nc-acxrequest-evt_acx_object_process_event_request.md) associated with this item.

### -field Reserved

This field is reserved.

### -field ArgsCb

The count in bytes (size) of the Args.

### -field ResultCb

The count in bytes (size) of the Result.

### -field ResultType

TBD - The ResultType

## -remarks

### Example

Example usage is shown below.

TBD - Need to check on KSMETHODSETID_ApxCircuitFactory and if it is KS header?  Or maybe use a different code sample?

```cpp
DEFINE_GUIDSTRUCT("14226c89-d411-493d-b473-11d61d476f98", KSMETHODSETID_ApxCircuitFactory);
#define KSMETHODSETID_ApxCircuitFactory DEFINE_GUIDNAMED(KSMETHODSETID_ApxCircuitFactory)


static ACX_METHOD_ITEM s_FactoryCircuitMethods[] =
{
    {
        &KSMETHODSETID_ApxCircuitFactory,
        KSMETHOD_APXCIRCUITFACTORY_ADD_CIRCUIT,
        ACX_METHOD_ITEM_FLAG_SEND,
        &C_EvtAddCircuitCallback,
        NULL,                                       // Reserved
        sizeof(APX_CIRCUIT_FACTORY_ADD_CIRCUIT),    // ControlCb
        0,                                          // ValueCb
    },
```

## -see-also

- [acxrequest.h header](index.md)

TBD - Please review this topic