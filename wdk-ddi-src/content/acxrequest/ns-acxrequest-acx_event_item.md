---
UID: NS:acxrequest._ACX_EVENT_ITEM
tech.root: audio
title: ACX_EVENT_ITEM
ms.date: 07/26/2022
targetos: Windows
description: The ACX_EVENT_ITEM structure describes an event item that is the target of an ACX request.
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
req.typenames: ACX_EVENT_ITEM, *PACX_EVENT_ITEM
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxrequest.h
api_name:
 - _ACX_EVENT_ITEM
 - PACX_EVENT_ITEM
 - ACX_EVENT_ITEM
f1_keywords:
 - _ACX_EVENT_ITEM
 - acxrequest/_ACX_EVENT_ITEM
 - PACX_EVENT_ITEM
 - acxrequest/PACX_EVENT_ITEM
 - ACX_EVENT_ITEM
 - acxrequest/ACX_EVENT_ITEM
dev_langs:
 - c++
---

## -description

The **ACX_EVENT_ITEM** structure describes an event item that is the target of an ACX request.

## -struct-fields

### -field Set

Specifies a GUID that identifies a KS (kernel streaming) event item set.

### -field Id

Specifies the member of the event set.

### -field Flags

The Flags field can be used to set the following Flags defined in the AcxRequest header.

```cpp

#define ACX_EVENT_ITEM_FLAG_NONE                0x00000000
#define ACX_EVENT_ITEM_FLAG_ENABLE              0x00000001 // KSEVENT_TYPE_ENABLE
#define ACX_EVENT_ITEM_FLAG_BASICSUPPORT        0x00000200 // KSEVENT_TYPE_BASICSUPPORT

```

### -field EvtAcxObjectProcessRequest

The [EVT_ACX_OBJECT_PROCESS_REQUEST callback](nc-acxrequest-evt_acx_object_process_event_request.md) event handler associated with this item.

### -field Reserved

This field is reserved.

## -remarks

### Example

Example usage is shown below.

```cpp

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)
