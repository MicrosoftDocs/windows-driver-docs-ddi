---
UID: NC:acxrequest.EVT_ACX_OBJECT_PROCESS_REQUEST
tech.root: audio
title: EVT_ACX_OBJECT_PROCESS_REQUEST
ms.date: 02/08/2022
targetos: Windows
description: The EVT_ACX_OBJECT_PROCESS_REQUEST callback is used by the driver to allow it to add additional functionality in the process request handling. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxrequest.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxrequest.h
api_name:
 - EVT_ACX_OBJECT_PROCESS_REQUEST
f1_keywords:
 - EVT_ACX_OBJECT_PROCESS_REQUEST
 - acxrequest/EVT_ACX_OBJECT_PROCESS_REQUEST
dev_langs:
 - c++
---

## -description

The **EVT_ACX_OBJECT_PROCESS_REQUEST** callback is used by the driver to allow it to add additional functionality in the process request handling. 

## -parameters

### -param Object

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that will be associated with the request.

### -param Request

A standard WDFREQUEST object. 

For more information about working with WDF request objects, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects) and [wdfrequest.h header](/windows-hardware/drivers/ddi/wdfrequest/).

## -remarks

### Example

Example usage is shown below.

```cpp

```

## -see-also

[acxrequest.h header](index.md)

