---
UID: NF:wdm.KdPrintEx
title: KdPrintEx macro (wdm.h)
description: The KdPrintEx macro sends a string to the kernel debugger if the conditions you specify are met.A call to KdPrintEx requires double parentheses.
tech.root: devtest
ms.date: 12/13/2022
keywords: ["KdPrintEx macro"]
ms.keywords: DebugFns_375418aa-5241-4b2c-9369-c930c3ca1ca6.xml, KdPrintEx, KdPrintEx function [Driver Development Tools], devtest.kdprintex, wdm/KdPrintEx
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later.
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
req.lib: NtosKrnl.lib (See DbgPrintEx.)
req.dll: NtosKrnl.exe
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KdPrintEx
 - wdm/KdPrintEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KdPrintEx
---

## -description

The **KdPrintEx** macro sends a string to the kernel debugger if the conditions you specify are met.

A call to **KdPrintEx** requires double parentheses.

## -parameters

### -param _x_

Specifies arguments for the format string, as in **printf**.

## -remarks

**KdPrintEx** is identical to the **DbgPrintEx** routine in code that is compiled for a debug configuration. This routine has no effect in code that is compiled for a release build. Only kernel-mode drivers can call the **KdPrintEx** routine.

**KdPrintEx** either passes the specified string to the kernel debugger or does nothing at all, depending on the values of _ComponentId_, _Level_, and the corresponding component filter masks. For details, see [Reading and Filtering Debugging Messages](/windows-hardware/drivers/devtest/reading-and-filtering-debugging-messages).

Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to **KdPrintEx**. If you do use a string that you did not create, you must verify that this is a valid format string, and that the format codes match the argument list in type and quantity. The best coding practice is for all _Format_ strings to be static and defined at compile time.

There is no upper limit to the size of the _Format_ string or the number of arguments. However, any single call to **KdPrintEx** will only transmit 512 bytes of information. There is also a limit to the size of the DbgPrint buffer. See [The DbgPrint Buffer and the Debugger](/windows-hardware/drivers/devtest/reading-and-filtering-debugging-messages) for details.

This routine is defined in ntddk.h and ndis.h; component filter IDs are defined in dpfilter.h, ndis.h, and wdm.h. Include ntddk.h or ndis.h.

Here are the arguments:

- ComponentId [in]

  Specifies the component calling this routine. This must be one of the component name filter IDs defined in the dpfilter.h header file. To avoid mixing your driver's output with the output of Windows components, you should use only the following values for _ComponentId_:

  - DPFLTR_IHVVIDEO_ID

  - DPFLTR_IHVAUDIO_ID

  - DPFLTR_IHVNETWORK_ID

  - DPFLTR_IHVSTREAMING_ID

  - DPFLTR_IHVBUS_ID

  - DPFLTR_IHVDRIVER_ID

- Format [in]

  Specifies a pointer to the format string to print. The _Format_ string supports most of the **printf**-style [format specification fields](/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions). However, the Unicode format codes (**%C**, **%S**, **%lc**, **%ls**, **%wc**, **%ws**, and **%wZ**) can only be used with IRQL = PASSIVE_LEVEL. The **KdPrintEx** routine does not support any of the floating point types (**%f**, **%e**, **%E**, **%g**, **%G**, **%a**, or **%A**).

- Level [in]

  Specifies the severity of this message. This can be any 32-bit integer. Values between 0 and 31 (inclusive) are treated differently than values between 32 and 0xFFFFFFFF. For details, see [Reading and Filtering Debugging Messages](/windows-hardware/drivers/devtest/reading-and-filtering-debugging-messages).

## -see-also

[DbgPrint](./nf-wdm-dbgprint.md)

[DbgPrintEx](./nf-wdm-dbgprintex.md)

[KdPrint](./nf-wdm-kdprint.md)