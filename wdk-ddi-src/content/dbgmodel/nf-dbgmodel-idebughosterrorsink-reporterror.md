---
UID: NF:dbgmodel.IDebugHostErrorSink.ReportError
title: IDebugHostErrorSink::ReportError
author: windows-driver-content
description: TBD
ms.assetid: c7a5bba3-dd86-4710-9da8-0e5f111ab45e
ms.author: windowsdriverdev
ms.date: 09/12/2018
ms.topic: method
ms.keywords: IDebugHostErrorSink::ReportError, ReportError, IDebugHostErrorSink.ReportError, IDebugHostErrorSink::ReportError, IDebugHostErrorSink.ReportError
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostErrorSink.ReportError
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostErrorSink::ReportError


## -description

The ReportError method is a callback on the error sink to notify it that an error has occurred and allow the sink to route the error to whatever UI or mechanism is appropriate. 

## -parameters

### -param errClass
An enumeration of type ErrorClass which indicates what class the error is (e.g.: warning or error)

### -param hrError
The HRESULT of the error which occurred.

### -param message
An optional message associated with the error.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostErrorSink interface](nn-dbgmodel-idebughosterrorsink.md)
