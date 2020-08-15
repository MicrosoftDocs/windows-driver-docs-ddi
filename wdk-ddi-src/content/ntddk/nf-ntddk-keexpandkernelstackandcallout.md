---
UID: NF:ntddk.KeExpandKernelStackAndCallout
title: KeExpandKernelStackAndCallout function (ntddk.h)
description: The KeExpandKernelStackAndCallout routine calls a routine with a guaranteed amount of stack space.
old-location: kernel\keexpandkernelstackandcallout.htm
tech.root: kernel
ms.assetid: afa27127-b427-4831-b5f5-3e293738c275
ms.date: 04/30/2018
keywords: ["KeExpandKernelStackAndCallout function"]
ms.keywords: KeExpandKernelStackAndCallout, KeExpandKernelStackAndCallout routine [Kernel-Mode Driver Architecture], k105_37fc85c2-2317-41a2-9daa-766c3ccf343f.xml, kernel.keexpandkernelstackandcallout, ntddk/KeExpandKernelStackAndCallout
f1_keywords:
 - "ntddk/KeExpandKernelStackAndCallout"
 - "KeExpandKernelStackAndCallout"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Server 2003 on x64-based processors, and starting with Windows Vista on all processors.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeExpandKernelStackAndCallout
targetos: Windows
req.typenames: 
---

# KeExpandKernelStackAndCallout function


## -description


The <b>KeExpandKernelStackAndCallout</b> routine calls a routine with a guaranteed amount of stack space.

## -syntax

```cpp
NTSTATUS
KeExpandKernelStackAndCallout (
    _In_ PEXPAND_STACK_CALLOUT Callout,
    _In_opt_ PVOID Parameter,
    _In_ SIZE_T Size
    );
```

## -parameters




### -param Callout 
[in]
Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout">ExpandedStackCall</a> routine.

### -param Parameter 
[in, optional]
Specifies the parameter to pass to the <i>ExpandedStackCall</i> routine.

### -param Size 
[in]
Specifies the number of bytes on the stack to provide to the <i>ExpandedStackCall</i> routine. This value must be large enough to accommodate the stack usage of the <i>ExpandedStackCall</i> routine and any call that this routine might make. This value must not exceed MAXIMUM_EXPANSION_SIZE.

## -returns


Returns success if the stack allocation is successful and the callout has been called. Otherwise, returns a failure status.



## -remarks



<b>KeExpandKernelStackAndCallout</b> expands the kernel stack by <i>Size</i> bytes for use by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout">ExpandedStackCall</a> routine. If there is not enough space available on the stack, <b>KeExpandKernelStackAndCallout</b> allocates a new kernel stack segment. The routine then calls the <i>ExpandedStackCall</i> routine.

In Windows 7, Windows Server 2008 R2, and later versions of Windows, consider using the [**KeExpandKernelStackAndCalloutEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keexpandkernelstackandcalloutex)  routine instead of <b>KeExpandKernelStackAndCallout</b>. <b>KeExpandKernelStackAndCalloutEx</b> is similar to <b>KeExpandKernelStackAndCallout</b> but has additional parameters and can be called at IRQL <= DISPATCH_LEVEL.

The calling thread must not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-psterminatesystemthread">PsTerminateSystemThread</a> routine until the thread's <i>ExpandedStackCall</i> routine returns. <b>PsTerminateSystemThread</b> checks to determine if the <i>ExpandedStackCall</i> routine is still active and, if it is, causes a bug check.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-expand_stack_callout">ExpandedStackCall</a>



[**KeExpandKernelStackAndCalloutEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keexpandkernelstackandcalloutex) 



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-psterminatesystemthread">PsTerminateSystemThread</a>
 

 

