---
UID: NF:wdm.IoWMISetNotificationCallback
title: IoWMISetNotificationCallback function (wdm.h)
description: The IoWMISetNotificationCallback routine registers a notification callback for a WMI event.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["IoWMISetNotificationCallback function"]
ms.keywords: IoWMISetNotificationCallback, IoWMISetNotificationCallback routine [Kernel-Mode Driver Architecture], k104_8ee391bd-0abe-4901-b0dc-6266d0c8f5c4.xml, kernel.iowmisetnotificationcallback, wdm/IoWMISetNotificationCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoWMISetNotificationCallback
 - wdm/IoWMISetNotificationCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoWMISetNotificationCallback
---

## -description

The **IoWMISetNotificationCallback** routine registers a notification callback for a WMI event.

## -parameters

### -param Object [in, out]

Pointer to a WMI data block object. The caller opens the data block object for the WMI event with the [IoWMIOpenBlock](/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock) routine. The object must be opened with the WMIGUID_NOTIFICATION access right.

### -param Callback [in]

Pointer to a function of the form:

```cpp
 XxxWmiNotificationCallback(PVOID Wnode, PVOID Context);
```

WMI calls this function to notify the caller that the specified event has occurred. The *Wnode* parameter of the callback routine points to the [**WNODE_EVENT_ITEM**](/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_item) structure returned by the driver triggering the event. The *Context* parameter of the callback routine points to the value specified in the *Context* parameter of the **IoWMISetNotificationCallback** routine.

### -param Context [in, optional]

Specifies the value that WMI passes to the callback routine when the event occurs.

## -returns

This routine returns STATUS_SUCCESS on success, and the appropriate NTSTATUS error code on failure.

## -see-also

[IoWMIOpenBlock](/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock)

[**WNODE_EVENT_ITEM**](/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_item)
