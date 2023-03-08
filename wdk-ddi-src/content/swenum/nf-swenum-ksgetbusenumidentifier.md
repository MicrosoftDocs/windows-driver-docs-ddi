---
UID: NF:swenum.KsGetBusEnumIdentifier
title: KsGetBusEnumIdentifier function (swenum.h)
description: The KsGetBusEnumIdentifier function retrieves the software bus enumerator identifier for the bus device associated with the given IRP.
tech.root: stream
ms.date: 03/03/2023
keywords: ["KsGetBusEnumIdentifier function"]
ms.keywords: KsGetBusEnumIdentifier, KsGetBusEnumIdentifier function [Streaming Media Devices], ksfunc_c001aace-8c97-48cb-ae8b-9e7075d51960.xml, stream.ksgetbusenumidentifier, swenum/KsGetBusEnumIdentifier
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGetBusEnumIdentifier
 - swenum/KsGetBusEnumIdentifier
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetBusEnumIdentifier
---

## -description

*This function is intended for internal use only.*

The **KsGetBusEnumIdentifier** function retrieves the software bus enumerator identifier for the bus device associated with the given IRP.

## -parameters

### -param Irp [in, out]

Pointer to the IRP that specifies the address and size of the user output buffer to receive the requested bus enumerator identifier.

## -returns

Returns STATUS_SUCCESS if the bus enumerator identifier was retrieved successfully. Otherwise, it returns one of the following values:

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | The specified device is not valid |
| **STATUS_BUFFER_TOO_SMALL** | The specified buffer was not large enough |
| **STATUS_BUFFER_OVERFLOW** | No buffer was specified (the required buffer size is returned in the Irp). |
