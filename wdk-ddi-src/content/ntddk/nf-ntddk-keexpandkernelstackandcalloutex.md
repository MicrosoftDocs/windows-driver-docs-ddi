---
UID: NF:ntddk.KeExpandKernelStackAndCalloutEx
title: KeExpandKernelStackAndCalloutEx
ms.date: 11/8/2019
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe 
req.header: ntddk.h
req.idl: 
req.include-header: 
req.irql: See Remarks section.
req.kmdf-ver: 
req.lib: NtosKrnl.lib 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - ntddk.h
api_name:
 - KeExpandKernelStackAndCalloutEx
f1_keywords:
 - ntddk/KeExpandKernelStackAndCalloutEx
 - ""
dev_langs:
 - c++
---

## -description

The **KeExpandKernelStackAndCalloutEx** routine calls a routine and guarantees that a specified amount of stack space is available for this call.

## -parameters

### -param Callout

A function pointer to an [*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) routine. **KeExpandKernelStackAndCalloutEx** expands the stack, if necessary, before it calls this routine.


### -param Size

Specifies the number of bytes of stack space to provide for the call to the [*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) routine. This value must be large enough to accommodate the stack usage of the [*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) routine and of any call that this routine might make. The Size value must not exceed MAXIMUM_EXPANSION_SIZE.


### -param Wait

Specifies whether the routine should wait to allocate the required stack space if this space is not immediately available. Set Wait to **TRUE** if the routine can wait for an expanded stack to be allocated. Otherwise, set Wait to **FALSE**. This parameter must be **FALSE** if **KeExpandKernelStackAndCalloutEx** is called at IRQL = DISPATCH_LEVEL.


### -param Context

Reserved. Always set this parameter to NULL.


### -param Parameter

Specifies the parameter value to pass to the [*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) routine.


## -returns

**KeExpandKernelStackAndCalloutEx** returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.

|Return code|Description|
|-|-|
|STATUS_INVALID_PARAMETER_3|The Size parameter is greater than MAXIMUM_EXPANSION_SIZE.|
|STATUS_INVALID_PARAMETER_4|The Wait parameter is TRUE but the routine was called at IRQL = DISPATCH_LEVEL.|
|STATUS_NO_MEMORY|Not enough memory is available to expand the stack.|
|STATUS_STACK_OVERFLOW|The stack, if expanded, would exceed the operating system's internal limits on stack space.|
 

## -remarks

This routine first determines whether a minimum of *Size* bytes is available on the current stack for the call to the [*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) routine. If not, **KeExpandKernelStackAndCalloutEx** tries to expand the current stack by *Size* bytes. If the current stack cannot be expanded by this amount, **KeExpandKernelStackAndCalloutEx** temporarily allocates a new kernel stack segment. If a stack of the required size is available, **KeExpandKernelStackAndCalloutEx** uses this stack to call the [*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) routine.

If **KeExpandKernelStackAndCalloutEx** is unable to obtain the required stack space, it returns without calling the [*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) routine. **KeExpandKernelStackAndCalloutEx** returns STATUS_SUCCESS only if it is able to call the [*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) routine. Otherwise, it returns an error code.

**KeExpandKernelStackAndCalloutEx** is not declared in a header file. To use this routine in your driver, include the following function declaration in your driver code:

```cpp
#if (NTDDI_VERSION >= NTDDI_VISTA)
__checkReturn
__drv_minIRQL(PASSIVE_LEVEL)
__drv_maxIRQL(DISPATCH_LEVEL)
__drv_reportError("DISPATCH_LEVEL is only supported on Windows 7 or later versions of Windows.")
NTKERNELAPI
NTSTATUS
KeExpandKernelStackAndCalloutEx (
    __in PEXPAND_STACK_CALLOUT Callout,
    __in_opt PVOID Parameter,
    __in SIZE_T Size,
    __in BOOLEAN Wait,
    __in_opt PVOID Context
    );
#endif
```

The [**KeExpandKernelStackAndCallout**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keexpandkernelstackandcallout) routine is similar to **KeExpandKernelStackAndCalloutEx** but does not have *Wait* and *Context* parameters. In addition, [**KeExpandKernelStackAndCallout**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keexpandkernelstackandcallout) must always be called at IRQL <= APC_LEVEL, whereas **KeExpandKernelStackAndCalloutEx** can be called at DISPATCH_LEVEL (but only if *Wait* is **FALSE**).

The calling thread must not call the [**PsTerminateSystemThread**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-psterminatesystemthread) routine until the thread's [*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) routine returns. [**PsTerminateSystemThread**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-psterminatesystemthread) checks to determine if the [*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) routine is still active and, if it is, causes a bug check.

In Windows Vista and Windows Server 2008, **KeExpandKernelStackAndCalloutEx** must be called at IRQL <= APC_LEVEL. In Windows 7, Windows Server 2008 R2, and later versions of Windows, this routine can be called at IRQL <= DISPATCH_LEVEL. However, the *Wait* parameter must be **FALSE** if the routine is called at DISPATCH_LEVEL. If *Wait* is **TRUE**, the call must occur at IRQL <= APC_LEVEL.


## -see-also

[*ExpandedStackCall*](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout) 
[**KeExpandKernelStackAndCallout**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keexpandkernelstackandcallout) 
[**PsTerminateSystemThread**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-psterminatesystemthread) 
