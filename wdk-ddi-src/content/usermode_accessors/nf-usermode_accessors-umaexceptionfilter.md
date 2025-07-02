---
UID: NF:usermode_accessors.UmaExceptionFilter
tech.root: kernel
title: UmaExceptionFilter
ms.date: 07/02/2025
targetos: Windows
description: The UmaExceptionFilter function provides mode-dependent exception filtering for structured exception handling.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: usermode_accessors.h
req.idl: 
req.include-header: 
req.irql: Less than or equal to APC_LEVEL
req.kmdf-ver: 
req.lib: umaccess.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: See Remarks
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usermode_accessors.h
api_name:
 - UmaExceptionFilter
f1_keywords:
 - UmaExceptionFilter
 - usermode_accessors/UmaExceptionFilter
dev_langs:
 - c++
helpviewer_keywords:
 - UmaExceptionFilter
---

## -description

The **UmaExceptionFilter** function provides mode-dependent exception filtering for structured exception handling.

## -parameters

### -param Mode

[in] The processor mode that determines the exception handling behavior. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | The exception should continue searching for a handler. Returns **EXCEPTION_CONTINUE_SEARCH**. |
| **UserMode** | The exception should be handled by the current handler. Returns **EXCEPTION_EXECUTE_HANDLER**. |

## -returns

The function returns one of the following exception filter values:

| Return code | Description |
|-------------|-------------|
| **EXCEPTION_EXECUTE_HANDLER** | Returned when **Mode** is **UserMode**. Indicates that the exception handler should execute and the exception is considered handled. |
| **EXCEPTION_CONTINUE_SEARCH** | Returned when **Mode** is **KernelMode**. Indicates that the exception should propagate up the call stack to find another handler. |

## -remarks

This function provides a standardized way to handle structured exceptions differently depending on whether the code is dealing with user-mode or kernel-mode memory access. It's designed to be used in `__except()` clauses within usermode accessor functions.

The behavior depends on the processor mode specified:

- When **Mode** is **UserMode**, the function returns **EXCEPTION_EXECUTE_HANDLER**, indicating that exceptions should be handled gracefully. This is appropriate for user-mode memory access where exceptions are expected and should not crash the system.
- When **Mode** is **KernelMode**, the function returns **EXCEPTION_CONTINUE_SEARCH**, indicating that exceptions should propagate to higher-level handlers. This is appropriate for kernel-mode memory access where exceptions typically indicate serious bugs that should not be silently ignored.

This design pattern ensures that user-mode memory access failures are handled safely while kernel-mode memory access failures are treated as serious errors requiring appropriate debugging and error handling.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.
