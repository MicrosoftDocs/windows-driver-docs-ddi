---
UID: NS:acxrequest._ACX_REQUEST_PARAMETERS
tech.root: audio
title: ACX_REQUEST_PARAMETERS
ms.date: 03/04/2022
targetos: Windows
description: The ACX_REQUEST_PARAMETERS structure describes the items that can be used in an ACX request.
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
req.typenames: ACX_REQUEST_PARAMETERS, *PACX_REQUEST_PARAMETERS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxrequest.h
api_name:
 - _ACX_REQUEST_PARAMETERS
 - PACX_REQUEST_PARAMETERS
 - ACX_REQUEST_PARAMETERS
f1_keywords:
 - _ACX_REQUEST_PARAMETERS
 - acxrequest/_ACX_REQUEST_PARAMETERS
 - PACX_REQUEST_PARAMETERS
 - acxrequest/PACX_REQUEST_PARAMETERS
 - ACX_REQUEST_PARAMETERS
 - acxrequest/ACX_REQUEST_PARAMETERS
dev_langs:
 - c++
---

## -description

The **ACX_REQUEST_PARAMETERS** structure describes the items that can be used in an ACX request.

The following parameters are based on the service that is being invoked, such as a property, method or event. Drivers can determine which set to use based on the ACX_ITEM_TYPE.

The three uses of this structure facilitate communications back to existing kernel streaming (KS) types. For more information about KS see [KS Properties, Events, and Methods](/windows-hardware/drivers/stream/ks-properties--events--and-methods).

For specific information of each of the types, see the following topics.

- [KS Properties](/windows-hardware/drivers/stream/ks-properties)
- [KS Events](/windows-hardware/drivers/stream/ks-events)
- [KS Methods](/windows-hardware/drivers/stream/ks-methods)

In addition the following topics may be useful.

[Audio Drivers Property Sets](/windows-hardware/drivers/audio/audio-drivers-property-sets)
[KSIDENTIFIER structure (ks.h)](/windows-hardware/drivers/ddi/ks/ns-ks-ksidentifier)

## -struct-fields

### -field Size

The size of the structure in bytes.

### -field MajorFunction

The WDF IRP major function that is used for this request, for example IRP_MJ_DEVICE_CONTROL or IRP_MJ_PNP. For more information about WDF IRP, see [IRP Major Function Codes](/windows-hardware/drivers/kernel/irp-major-function-codes).

### -field MinorFunction

The WDF IRP minor function that is used for this request, for example IRP_MN_QUERY_CAPABILITIES. For more information about the Minor Function refer to the associated withe major IRP, for example [Plug and Play Minor IRPs](/windows-hardware/drivers/kernel/plug-and-play-minor-irps), [Power Management Minor IRPs](/windows-hardware/drivers/kernel/power-management-minor-irps) and [WMI Minor IRPs](/windows-hardware/drivers/kernel/wmi-minor-irps).

### -field Type

The **ACX_ITEM_TYPE**(ne-acxrequest-acx_item_type.md) enumeration describes the type of items that will be sent in the request.

### -field Parameters

### -field Parameters.Property

### -field Parameters.Property.Set

### -field Parameters.Property.Id

### -field Parameters.Property.Verb

### -field Parameters.Property.ItemType

### -field Parameters.Property.ItemId

### -field Parameters.Property.Control

### -field Parameters.Property.ControlCb

The count in bytes (size) of the Control

### -field Parameters.Property.Value

The Property Value that will be TBD

### -field Parameters.Property.ValueCb

The count in bytes (size) of the Value.

### -field Parameters.Method

TBD - Based on Method struct?

### -field Parameters.Method.Set

### -field Parameters.Method.Id

### -field Parameters.Method.Verb

### -field Parameters.Method.ItemType

### -field Parameters.Method.ItemId

### -field Parameters.Method.Args

### -field Parameters.Method.ArgsCb

### -field Parameters.Method.Result

### -field Parameters.Method.ResultCb

### -field Parameters.Event

TBD - Based on Method struct

### -field Parameters.Event.Set

### -field Parameters.Event.Id

### -field Parameters.Event.Verb

### -field Parameters.Event.ItemType

### -field Parameters.Event.ItemId

### -field Parameters.Event.Data

### -field Parameters.Event.DataCb

### -field Parameters.Event.EventData


### -field Parameters.Create

TBD - 

### -field Parameters.Create.Control

TBD - 

### -field Parameters.Create.ControlCb

TBD - The count in bytes (size) of the Create Control TBD

## -remarks

### Example

Example usage is shown below.

```cpp

```

## -see-also

- [acxrequest.h header](index.md)

TBD - Please review this topic