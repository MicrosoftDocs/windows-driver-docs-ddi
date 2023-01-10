---
UID: NF:wdm.DbgPrint
title: DbgPrint function (wdm.h)
description: The DbgPrint routine sends a message to the kernel debugger.
tech.root: devtest
ms.date: 01/10/2023
keywords: ["DbgPrint function"]
ms.keywords: DbgPrint, DbgPrint routine [Driver Development Tools], DebugFns_5e11bbcc-adc2-46c0-b371-0e54c50bb2dc.xml, ULONG, devtest.dbgprint, wdm/DbgPrint
req.header: wdm.h
req.include-header: Wdm.h
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
req.lib: NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: IRQL <= DIRQL (see Comments section)
targetos: Windows
req.typenames: 
f1_keywords:
 - DbgPrint
 - wdm/DbgPrint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtDll.dll
 - NtosKrnl.exe
api_name:
 - DbgPrint
---

## -description

The **DbgPrint** routine sends a message to the kernel debugger when the conditions that you specify apply (see the **Remarks** section below).

## -parameters

### -param Format [in]

Specifies a pointer to the format string to print. The *Format* string supports most of the **printf**-style [format specification fields](/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions). However, the Unicode format codes (**%C**, **%S**, **%lc**, **%ls**, **%wc**, **%ws**, and **%wZ**) can only be used with IRQL = PASSIVE_LEVEL. The **DbgPrint** routine does not support any of the floating point types (**%f**, **%e**, **%E**, **%g**, **%G**, **%a**, or **%A**).

### -param

Specifies arguments for the format string, as in **printf**.

## -returns

If successful, **DbgPrint** returns the NTSTATUS code STATUS_SUCCESS; otherwise it returns the appropriate error code.

## -remarks

**DbgPrint** and **DbgPrintEx** can be called at IRQL&lt;=DIRQL. However, Unicode format codes (**%C**, **%S**, **%lc**, **%ls**, **%wc**, **%ws**, and **%wZ**) can be used only at IRQL=PASSIVE_LEVEL. Also, because the debugger uses interprocess interrupts (IPIs) to communicate with other processors, calling **DbgPrint** at IRQL&gt;DIRQL can cause deadlocks.

Only kernel-mode drivers can call the **DbgPrint** routine.

**DbgPrint** sends a message only if certain conditions apply. Specifically, it behaves like the [DbgPrintEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgprintex) routine with the DEFAULT component and a message importance level of DPFLTR_INFO_LEVEL. In other words, the following two function calls are identical:

```cpp
DbgPrint ( Format, arguments )

DbgPrintEx ( DPFLTR_DEFAULT_ID, DPFLTR_INFO_LEVEL, Format, arguments )
```

For more information about message filtering, components, and message importance level, see [Reading and Filtering Debugging Messages](/windows-hardware/drivers/devtest/reading-and-filtering-debugging-messages).

It is recommended that you use **DbgPrintEx** instead of **DbgPrint**, since this allows you to control the conditions under which the message is sent.

Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to **DbgPrint**. If you do use a string that you did not create, you must verify that this is a valid format string, and that the format codes match the argument list in type and quantity. The best coding practice is for all *Format* strings to be static and defined at compile time.

There is no upper limit to the size of the *Format* string or the number of arguments. However, any single call to **DbgPrint** will only transmit 512 bytes of information. There is also a limit to the size of the DbgPrint buffer. See [DbgPrint Buffer and the Debugger](/windows-hardware/drivers/devtest/reading-and-filtering-debugging-messages) for details.

## -see-also

[DbgPrintEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgprintex)

[KdPrint](/windows-hardware/drivers/ddi/wdm/nf-wdm-kdprint)

[KdPrintEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-kdprintex)
