---
UID: NS:acxrequest._ACX_REQUEST_PARAMETERS
tech.root: audio
title: ACX_REQUEST_PARAMETERS
ms.date: 02/22/2022
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

TBD - Once the related property/method fields are filled in can mirror over to here.

## -struct-fields

### -field Size

The size of the structure in bytes.

### -field MajorFunction

The WDF IRP major function that is used for this request, for example IRP_MJ_DEVICE_CONTROL or IRP_MJ_PNP. For more information about WDF IRP, see [IRP Major Function Codes](/windows-hardware/drivers/kernel/irp-major-function-codes).

### -field MinorFunction

The WDF IRP minor function that is used for this request, for example IRP_MN_QUERY_CAPABILITIES. For more information about the Minor Function refer to the associated withe major IRP, for example [Plug and Play Minor IRPs](/windows-hardware/drivers/kernel/plug-and-play-minor-irps), [Power Management Minor IRPs](/windows-hardware/drivers/kernel/power-management-minor-irps) and [WMI Minor IRPs](/windows-hardware/drivers/kernel/wmi-minor-irps).

### -field Type

The Type field TBD

### -field Parameters

TBD - Based on Property struct

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

[acxrequest.h header](index.md)

