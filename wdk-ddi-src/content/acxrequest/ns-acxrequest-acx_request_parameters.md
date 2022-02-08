---
UID: NS:acxrequest._ACX_REQUEST_PARAMETERS
tech.root: audio
title: ACX_REQUEST_PARAMETERS
ms.date: 01/10/2022
targetos: Windows
description: 
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

The **ACX_REQUEST_PARAMETERS** structure describes the event items that can be used in an ACX request.

## -struct-fields

### -field Size

### -field MajorFunction

### -field MinorFunction

### -field Type

### -field Parameters

### -field Parameters.Property

### -field Parameters.Property.Set

### -field Parameters.Property.Id

### -field Parameters.Property.Verb

### -field Parameters.Property.ItemType

### -field Parameters.Property.ItemId

### -field Parameters.Property.Control

### -field Parameters.Property.ControlCb

### -field Parameters.Property.Value

### -field Parameters.Property.ValueCb

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

