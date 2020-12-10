---
UID: NN:dbgmodel.IDebugHostErrorSink
title: IDebugHostErrorSink (dbgmodel.h)
description: An interface to which errors will be sinked.
ms.date: 07/13/2018
keywords: ["IDebugHostErrorSink interface"]
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostErrorSink
 - dbgmodel/IDebugHostErrorSink
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostErrorSink
---

# IDebugHostErrorSink interface


## -description

An interface to which errors will be sinked.

An interface implemented by callers to receive errors from certain portions of the host and data model.

## -inheritance

IDebugHostErrorSink interits from IUnknown.

## -remarks

The IDebugHostErrorSink is a means by which a client can receive notifications of errors which occur during certain operations and route those errors where needed.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
