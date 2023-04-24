---
UID: NF:wdm.KdRefreshDebuggerNotPresent
title: KdRefreshDebuggerNotPresent function (wdm.h)
description: The KdRefreshDebuggerNotPresent macro refreshes the value of the KD_DEBUGGER_NOT_PRESENT global kernel variable.
tech.root: devtest
ms.date: 01/10/2023
keywords: ["KdRefreshDebuggerNotPresent function"]
ms.keywords: DebugFns_77b08eed-2f06-4ede-b02f-f1a7a5ab9ba5.xml, KdRefreshDebuggerNotPresent, KdRefreshDebuggerNotPresent function [Driver Development Tools], devtest.kdrefreshdebuggernotpresent, ntddk/KdRefreshDebuggerNotPresent
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KdRefreshDebuggerNotPresent
 - wdm/KdRefreshDebuggerNotPresent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KdRefreshDebuggerNotPresent
---

## -description

The **KdRefreshDebuggerNotPresent** macro refreshes the value of the [KD_DEBUGGER_NOT_PRESENT](/previous-versions/ff548125(v=vs.85)) global kernel variable.

## -returns

**KdRefreshDebuggerNotPresent** returns the value of KD_DEBUGGER_NOT_PRESENT.

## -remarks

When **KdRefreshDebuggerNotPresent** is called, it forces the value of KD_DEBUGGER_NOT_PRESENT to be updated to reflect whether a kernel debugger is currently attached. This updated value is also used as the return value of this routine.

If a kernel debugger was recently attached or removed, the value of KD_DEBUGGER_NOT_PRESENT may not reflect the new state. If you suspect this has happened, you should call **KdRefreshDebuggerNotPresent** to refresh the value of this variable. After this call, you may use either the value of KD_DEBUGGER_NOT_PRESENT or the return value of **KdRefreshDebuggerNotPresent** to determine if the kernel debugger is present.

KD_DEBUGGER_NOT_PRESENT can be modified by Windows or any other kernel-mode binary. Therefore, it is possible that the most recent return value of **KdRefreshDebuggerNotPresent** may not match the current value of KD_DEBUGGER_NOT_PRESENT.

The following sample shows how to use **KdRefreshDebuggerNotPresent**:

```cpp
if (KdRefreshDebuggerNotPresent() == FALSE)
{
    //  A kernel debugger is active.
    DbgPrint("A problem occurred\n");
 DbgBreakPoint();
}
else
{
 //  No kernel debugger attached, or kernel debugging not enabled.
 KeBugCheckEx(...);
}
```

## -see-also

[Determining if a Debugger is Attached](/windows-hardware/drivers/debugger/determining-if-a-debugger-is-attached)

[KD_DEBUGGER_ENABLED](/previous-versions/ff548118(v=vs.85))

[KD_DEBUGGER_NOT_PRESENT](/previous-versions/ff548125(v=vs.85))
