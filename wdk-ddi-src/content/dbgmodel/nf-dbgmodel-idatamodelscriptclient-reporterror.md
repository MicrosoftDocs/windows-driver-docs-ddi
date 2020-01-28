---
UID: NF:dbgmodel.IDataModelScriptClient.ReportError
title: IDataModelScriptClient::ReportError (dbgmodel.h)
description: If an error occurs during execution or invocation of the script, the script provider calls the ReportError method to notify the user interface of the error. 
ms.assetid: c8cedcee-002c-4373-a518-31aad3cee313
ms.date: 08/20/2018
f1_keywords:
 - "dbgmodel/IDataModelScriptClient.ReportError"
ms.keywords: IDataModelScriptClient::ReportError, ReportError, IDataModelScriptClient.ReportError, IDataModelScriptClient::ReportError, IDataModelScriptClient.ReportError
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDataModelScriptClient.ReportError
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptClient::ReportError


## -description

If an error occurs during execution or invocation of the script, the script provider calls the ReportError method to notify the user interface of the error. 

The script provider may call the ReportError method an arbitrary number of times during an Execute or InvokeMain operation. It is up to the client to determine how to present the error information to the user. 


## -parameters

### -param errClass
The class of error which is being reported as a member of the ErrorClass enumeration. Further information about this enumeration can be found in the documentation for [IDebugHostErrorSink](nn-dbgmodel-idebughosterrorsink.md).

### -param hrFail
The HRESULT of the error which occurred. If the domain of the error was not an HRESULT, it should be converted to such by the most appropriate means.

### -param message
The error message which occurred.

### -param line
The one based line number of the script where the error occurred.

### -param position
The one based position (column number) within the line where the error occurred.


## -returns
This method returns HRESULT.
## -remarks

## -see-also

[IDataModelScriptClient interface](nn-dbgmodel-idatamodelscriptclient.md)
