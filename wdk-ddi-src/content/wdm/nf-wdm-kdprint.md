---
UID: NF:wdm.KdPrint
title: KdPrint macro (wdm.h)
description: The KdPrint macro sends a message to the kernel debugger.
old-location: devtest\kdprint.htm
tech.root: devtest
ms.assetid: 4a2ab12b-ee89-462d-821a-0a2db20cc36c
ms.date: 02/23/2018
keywords: ["KdPrint macro"]
ms.keywords: DebugFns_630aea64-3f51-4c73-8575-00a507846ab9.xml, KdPrint, KdPrint function [Driver Development Tools], devtest.kdprint, wdm/KdPrint
f1_keywords:
 - "wdm/KdPrint"
 - "KdPrint"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
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
req.lib: NtosKrnl.lib (See DbgPrint.)
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KdPrint
targetos: Windows
req.typenames: 
---

# KdPrint macro

## -description

The **KdPrint** macro sends a message to the kernel debugger.

**KdPrint** sends a message only if the conditions you specify apply. More info in the section below.

A call to **KdPrint** requires double parentheses.

## -parameters

### -param _x_ 
[in]
Specifies a pointer to the format string to print. The *Format* string supports most of the **printf**-style [format specification fields](https://docs.microsoft.com/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions?redirectedfrom=MSDN&view=vs-2019). However, the Unicode format codes (**%C**, **%S**, **%lc**, **%ls**, **%wc**, **%ws**, and **%wZ**) can only be used with IRQL = PASSIVE_LEVEL. The **KdPrint** routine does not support any of the floating point types (**%f**, **%e**, **%E**, **%g**, **%G**, **%a**, or **%A**).

## -remarks

**KdPrint** is identical to the **DbgPrint** routine in code that is compiled for a debug configuration.  This routine has no effect if compiled for a release configuration. Only kernel-mode drivers can call the **KdPrint** routine.

**KdPrint** sends a message only if certain conditions apply. Specifically, it behaves like [KdPrintEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kdprintex) with the DEFAULT component and a message importance level of DPFLTR_INFO_LEVEL. In other words, the following two function calls are identical:

`KdPrint (( Format, arguments ))`

`KdPrintEx (( DPFLTR_DEFAULT_ID, DPFLTR_INFO_LEVEL, Format, arguments ))`

For more information about message filtering, components, and message importance level, see [Reading and Filtering Debugging Messages](https://docs.microsoft.com/windows-hardware/drivers/devtest/reading-and-filtering-debugging-messages).

>[!NOTE]
>Regardless of which version of Windows you are using, it is recommended that you use **KdPrintEx** instead of **KdPrint**, since **KdPrintEx** allows you to control the conditions under which the message is sent.

Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to **KdPrint**. If you do use a string that you did not create, you must verify that this is a valid format string, and that the format codes match the argument list in type and quantity. The best coding practice is for all *Format* strings to be static and defined at compile time.

There is no upper limit to the size of the *Format* string or the number of arguments. However, any single call to **KdPrint** will only transmit 512 bytes of information. There is also a limit to the size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgprint">DbgPrint</a> buffer. See <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/reading-and-filtering-debugging-messages">The DbgPrint Buffer and the Debugger</a> for details.

## -see-also

[DbgPrint](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgprint)

[DbgPrintEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgprintex)

[KdPrintEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kdprintex)
