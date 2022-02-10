---
UID: NS:acxrequest._ACX_REQUEST_PARAMETERS
tech.root: audio
title: ACX_REQUEST_PARAMETERS
ms.date: 02/08/2022
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

## -struct-fields

### -field Size

The size of the structure in bytes.

### -field MajorFunction

The MajorFunction

TBD - Pointer to the IUnknown interface of a miniport object that supports the method set and method specified by TBD

### -field MinorFunction

The MinorFunction

### -field Type

The Type field TBD

### -field Parameters

TBD TBD TBD TBD 

TBD - Fields may be based on other structures to link to.

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

### -field Parameters.Property.ValueCb

The count in bytes (size) of the Value.

### -field Parameters.Method

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

### -field Parameters.Event.Set

### -field Parameters.Event.Id

### -field Parameters.Event.Verb

### -field Parameters.Event.ItemType

### -field Parameters.Event.ItemId

### -field Parameters.Event.Data

### -field Parameters.Event.DataCb

### -field Parameters.Event.EventData

### -field Parameters.Create

### -field Parameters.Create.Control

### -field Parameters.Create.ControlCb

## -remarks

### Example

Example usage is shown below.

```cpp

```

## -see-also

[acxrequest.h header](index.md)

