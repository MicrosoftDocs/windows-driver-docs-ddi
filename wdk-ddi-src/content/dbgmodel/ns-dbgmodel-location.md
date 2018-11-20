---
UID: NS:dbgmodel.Location
title: Location
author: windows-driver-content
description: Defines the location for an object.  This particular variant of Location is the C-COM access struct.
ms.assetid: 9ab3c521-e5c9-48ad-977e-d95954f5064b
ms.date: 10/02/2018
ms.topic: struct
ms.keywords: Location, , 
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dbgmodel.h
api_name: 
-	Location
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# Location structure

## -description

Defines the location for an object.  This particular variant of Location is the C-COM access struct.

Note that a location only has meaning in conjunction with a host context.  It is a location within a context.  When performing an operation on the location (reading bytes, writing bytes, etc...), a valid host context must be supplied.

## -struct-fields

### -field HostDefined
 
The HostDefined field has two states that are "Non-Opaque" at the API layer.

0: Indicates that the offset is a pointer into virtual address space of the target.

Non-Zero: The defined value is proprietary to the host.  Clients can propagate and change offset.  They cannot legally change the value. 
This can be determined by the IsVirtualAddress() method if this structure is built from C++ code.

### -field Offset

The location’s offset into the address space defined by the host context and the HostDefined field of this structure.  If the HostDefined field is zero, this is the virtual address of the location.  If the HostDefined field is non-zero, this is the offset into some other address space.  It may, for example, indicate where a particular field of a registered structure is located within the containing register.


## -remarks


## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
