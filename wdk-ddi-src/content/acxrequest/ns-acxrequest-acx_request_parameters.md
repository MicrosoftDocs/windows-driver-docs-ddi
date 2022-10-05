---
UID: NS:acxrequest._ACX_REQUEST_PARAMETERS
tech.root: audio
title: ACX_REQUEST_PARAMETERS
ms.date: 07/27/2022
targetos: Windows
description: The ACX_REQUEST_PARAMETERS structure receives parameters that are associated with an I/O ACX request.
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

The **ACX_REQUEST_PARAMETERS** structure receives parameters that are associated with an I/O ACX request.

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

The WDF IRP major function that is used for this request, for example IRP_MJ_DEVICE_CONTROL. For more information about WDF IRP, see [IRP Major Function Codes](/windows-hardware/drivers/kernel/irp-major-function-codes).

### -field MinorFunction

The WDF IRP minor function that is used for this request. For more information about the Minor Function refer to the associated withe major IRP, for example [Plug and Play Minor IRPs](/windows-hardware/drivers/kernel/plug-and-play-minor-irps), [Power Management Minor IRPs](/windows-hardware/drivers/kernel/power-management-minor-irps) and [WMI Minor IRPs](/windows-hardware/drivers/kernel/wmi-minor-irps).

### -field Type

The [ACX_REQUEST_TYPE](ne-acxrequest-acx_request_type.md) enumeration describes the type of items that will be sent in the request. Depending on the type specified, a subset of the parameters listed below will be used.

### -field Parameters

### -field Parameters.Property

Parameters for [KS Properties](/windows-hardware/drivers/stream/ks-properties) are being used for the ACX request. For more information, see [KSPROPERTY structure](/windows-hardware/drivers/stream/ksproperty-structure).

### -field Parameters.Property.Set

Specifies a GUID that identifies a kernel streaming property set. 

### -field Parameters.Property.Id

Specifies the member of the property set.

### -field Parameters.Property.Verb

An [ACX_PROPERTY_VERB](ne-acxrequest-acx_property_verb.md) enumeration that describes the property verb.

### -field Parameters.Property.ItemType

An [ACX_ITEM_TYPE](ne-acxrequest-acx_item_type.md) enumeration that describes the ACX item type being the target of this request.

### -field Parameters.Property.ItemId

The Item ID.

### -field Parameters.Property.Control

A pointer to system service parameters that are used as additional input parameters for the ACX request.

### -field Parameters.Property.ControlCb

The count in bytes (size) of the Property.Control buffer.

### -field Parameters.Property.Value

A pointer to the property value.

### -field Parameters.Property.ValueCb

The count in bytes (size) of the Property.Value buffer.

### -field Parameters.Method

Parameters used for a [KS Methods](/windows-hardware/drivers/stream/ks-methods) request. 

### -field Parameters.Method.Set

Specifies a GUID that identifies a kernel streaming method set.

### -field Parameters.Method.Id

Specifies the member of the method set.

### -field Parameters.Method.Verb

An [ACX_METHOD_VERB](ne-acxrequest-acx_method_verb.md) enumeration that describes the item being sent.

### -field Parameters.Method.ItemType

An [ACX_ITEM_TYPE](ne-acxrequest-acx_item_type.md) enumeration that describes the ACX item type being the target of this request.

### -field Parameters.Method.ItemId

The Item ID of the item being sent.

### -field Parameters.Method.Args

A pointer to optional arguments for the method.

### -field Parameters.Method.ArgsCb

The count in bytes (size) of the optional arguments for the method.

### -field Parameters.Method.Result

A pointer to the result of the method.

### -field Parameters.Method.ResultCb

The count in bytes (size) of the Method.Result buffer.

### -field Parameters.Event

Parameters used for [KS Events](/windows-hardware/drivers/stream/ks-events) that are being used for the ACX request. For more information, see [KSEVENT structure](/windows-hardware/drivers/stream/ksevent-structure).

### -field Parameters.Event.Set

Specifies a GUID that identifies a kernel streaming event set.

### -field Parameters.Event.Id

Specifies the member of the event set.

### -field Parameters.Event.Verb

An [ACX_EVENT_VERB](ne-acxrequest-acx_event_verb.md) enumeration that describes the item being sent.

### -field Parameters.Event.ItemType

An [ACX_ITEM_TYPE](ne-acxrequest-acx_item_type.md) enumeration that describes the ACX item type being the target of this request.

### -field Parameters.Event.ItemId

The event Item ID.

### -field Parameters.Event.Data

A pointer to the event data.

### -field Parameters.Event.DataCb

The count in bytes (size) of the Event.Data buffer.

### -field Parameters.Event.EventData

An ACXEVENTDATA Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -field Parameters.Create

The structure that contains the create parameters that are being used for the ACX request.

### -field Parameters.Create.Control

A pointer to system service parameters that are used as additional input parameters for the ACX request.

### -field Parameters.Create.ControlCb

The count in bytes (size) of the Create.Control buffer.

## -remarks

Driver must use ACX_REQUEST_PARAMETERS only when working with I/O ACX Requests. Driver must use WDF request DDIs to handle other type of requests.

### Example

Example usage is shown below.

```cpp
    ACX_REQUEST_PARAMETERS              params;
    
    PAGED_CODE();

    //
    // Get request parameters.
    //
    ACX_REQUEST_PARAMETERS_INIT(&params);
    AcxRequestGetParameters(Request, &params);

    ASSERT(params.Type == AcxRequestTypeMethod);
    ASSERT(params.Parameters.Method.Verb == AcxMethodVerbSend);
    ASSERT(params.Parameters.Method.ArgsCb >= argsCb);
        
    args = (PAPX_CIRCUIT_FACTORY_ADD_CIRCUIT)params.Parameters.Method.Args;
    argsCb = params.Parameters.Method.ArgsCb; // use real value.
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)
