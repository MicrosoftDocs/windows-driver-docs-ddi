---
UID: NF:ntddk.PshedSynchronizeExecution
title: PshedSynchronizeExecution function (ntddk.h)
description: The PshedSynchronizeExecution function synchronizes the execution of a given function with the hardware error processing for an error source.
tech.root: whea
ms.date: 01/10/2023
keywords: ["PshedSynchronizeExecution function"]
ms.keywords: PshedSynchronizeExecution, PshedSynchronizeExecution function [WHEA Drivers and Applications], ntddk/PshedSynchronizeExecution, whea.pshedsynchronizeexecution, whearef_7a6363f4-466d-498a-97c4-b5f7937005dd.xml
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.lib: Pshed.lib
req.dll: Pshed.dll
req.irql: IRQL <= DIRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - PshedSynchronizeExecution
 - ntddk/PshedSynchronizeExecution
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Pshed.dll
api_name:
 - PshedSynchronizeExecution
---

## -description

The **PshedSynchronizeExecution** function synchronizes the execution of a given function with the hardware error processing for an error source.

## -parameters

### -param ErrorSource [in]

A pointer to a [**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure that describes an error source.

### -param SynchronizeRoutine [in]

A pointer to a caller-supplied function whose execution is synchronized with the hardware error processing for the error source described by the *ErrorSource* parameter. A *SynchronizeRoutine* function is declared as follows:

```cpp
BOOLEAN
SynchronizeRoutine(
    _In_ PVOID  SynchronizeContext
    );
```

#### SynchronizeContext

The context value that is passed in the *SynchronizeContext* parameter to the **PshedSynchronizeExecution** function.

### -param SynchronizeContext [in]

A pointer to a caller-supplied context area that is passed to the function pointed to by the *SynchronizeRoutine* parameter.

## -returns

**PshedSynchronizeExecution** returns the value that is returned by the function pointed to by the *SynchronizeRoutine* parameter.

## -remarks

A PSHED plug-in calls the **PshedSynchronizeExecution** function to synchronize the execution of a given function with the hardware error processing for an error source. This is required whenever a PSHED plug-in shares resources between code that executes outside of the normal hardware error processing flow and code that executes as part of the normal hardware error processing flow. For more information about the processing of hardware errors, see [Error Processing](/windows-hardware/drivers/whea/error-processing).

When this function is called, the following occurs:

1. The IRQL is raised to the IRQL at which the low-level hardware error handler (LLHEH) for the error source executes.

1. Access to the context area specified by the *SynchronizeContext* parameter is synchronized with the LLHEH by acquiring the associated spin lock.

1. The function specified in the *SynchronizeRoutine* parameter is called.

Callers of the **PshedSynchronizeExecution** function must be running at IRQL <= DIRQL, that is, less than or equal to the IRQL at which the LLHEH for the error source executes.

## -see-also

[**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor)
