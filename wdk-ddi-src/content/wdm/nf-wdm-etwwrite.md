---
UID: NF:wdm.EtwWrite
title: EtwWrite function (wdm.h)
description: The EtwWrite function is a tracing function for publishing events in your kernel-mode driver code.
tech.root: devtest
ms.date: 01/12/2023
keywords: ["EtwWrite function"]
ms.keywords: EtwWrite, EtwWrite function [Driver Development Tools], devtest.etwwrite, etw_km_af581b5c-6124-4bb0-8756-c4a0009e7a00.xml, wdm/EtwWrite
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
req.irql: Any level (See Comments section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - EtwWrite
 - wdm/EtwWrite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - EtwWrite
---

## -description

The **EtwWrite** function is a tracing function for publishing events in your kernel-mode driver code.

## -parameters

### -param RegHandle [in]

A pointer to the event provider registration handle, which is returned by the [EtwRegister](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwregister) function if the event provider registration is successful.

### -param EventDescriptor [in]

A pointer to the [EVENT_DESCRIPTOR](/windows/win32/api/evntprov/ns-evntprov-event_descriptor) structure.

### -param ActivityId [in, optional]

The identifier that indicates the activity associated with the event. The *ActivityID* provides a way to group related events and is used in end-to-end tracing.

### -param UserDataCount [in]

The number of EVENT_DATA_DESCRIPTOR structures in *UserData*.

### -param UserData [in, optional]

A pointer to the array of EVENT_DATA_DESCRIPTOR structures.

## -returns

If the event was successfully published, **EtwWrite** returns STATUS_SUCCESS.

If the pointer to the event provider registration handle is invalid, **EtwWrite** returns STATUS_INVALID_HANDLE. The event provider must be registered before **EtwWrite** is called. **EtwWrite** can also return STATUS_INVALID_HANDLE if it is unable to log the event.

If the number of EVENT_DATA_DESCRIPTOR structures specified in *UserDataCount* is greater than the maximum allowed (128), **EtwWrite** returns STATUS_INVALID_PARAMETER.

If *ActivityID* is specified, but there is insufficient memory available to log the data associated with the event, **EtwWrite** returns STATUS_NO_MEMORY.

If the provider is not enabled for any session, **EtwWrite** returns STATUS_SUCCESS and the events are not logged.

Events can be lost for several reasons; for example, if the event rate is too high or if the event size is greater than the buffer size. In these cases, the **EventsLost** counter, a member of the EVENT_TRACE_PROPERTIES structure for the corresponding logger, is updated with the number of events that were not recorded.

## -remarks

The **EtwWrite** function is the kernel-mode equivalent of the user-mode **EventWrite** function. To ensure that there is a consumer for the event you are publishing, you can precede the call to **EtwWrite** with a call to [EtwEventEnabled](/windows-hardware/drivers/ddi/wdm/nf-wdm-etweventenabled) or [EtwProviderEnabled](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwproviderenabled).

Before you can call **EtwWrite** function to publish an event, you must register the provider with **EtwRegister**. No tracing calls should be made that fall outside of the code bounded by the **EtwRegister** and **EtwUnregister** functions. For the best performance, you can call the **EtwRegister** function in your **DriverEntry** routine and the **EtwUnregister** function in your **DriverUnload** routine.

If you are using the optional *UserData* parameter in the **EtwWrite** function to log additional event data, you can use the **EventDataDescCreate** macro to simplify the creation of the EVENT_DATA_DESCRIPTOR structures. The following example uses the **EventDataDescCreate** macro to initialize EVENT_DATA_DESCRIPTOR structures with  the name of the device and its status. The **EventDataDescCreate** macro stores pointers to the data (that is, it does not store copies of the data). The pointers must remain valid until the call to **EtwWrite** returns.

You can call **EtwWrite** at any IRQL. However, when IRQL is greater than APC_LEVEL, any data passed to the **EtwWrite**, [EtwWriteEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwwriteex), **EtwWriteString**, **EtwWriteTransfer** functions must not be pageable. That is, any kernel-mode routine that is running at IRQL greater than APC_LEVEL cannot access pageable memory.  Data passed to the **EtwWrite**, **EtwWriteEx**, **EtwWriteString**, and **EtwWriteTransfer** functions must reside in system-space memory, regardless of what the IRQL is.

### Example

```cpp
 
 //
 // Register the provider with ETW in DriverEntry
 // Unregister the provider in DriverUnload 
    //
 //  Build the EVENT_DATA_DESCRIPTOR structures using 
 //   the EventDataDescCreate macros 
 
 if (RegHandle != (REGHANDLE)NULL) {
 //
 // Log an Event with : DeviceNameLength
 //                      DeviceName
 //                      Status
 //
 
 EventDataDescCreate(&EventDataDescriptor[0],
                            (PVOID)&DeviceName.Length,
 sizeof(USHORT));
 

 EventDataDescCreate(&EventDataDescriptor[1],
                            (PVOID)DeviceName.Buffer,
 DeviceName.Length);
 
 EventDataDescCreate(&EventDataDescriptor[2],
                            (PVOID)&Status,
 sizeof(ULONG));
 
 EtwWrite(RegHandle,            // Handle from EtwRegister
                 &StartEvent,          // EventDescriptor
                 NULL,                 // Activity ID
                 3,                    // Number of data items
 EventDataDescriptor); // Array of data descriptors
    }              

//
```

## -see-also

[EtwEventEnabled](/windows-hardware/drivers/ddi/wdm/nf-wdm-etweventenabled)

[EtwProviderEnabled](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwproviderenabled)

[EtwRegister](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwregister)

[EtwUnregister](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwunregister)

[EtwWriteEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwwriteex)

[EtwWriteString](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwwritestring)

[EtwWriteTransfer](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwwritetransfer)

[EventDataDescCreate](/windows/win32/api/evntprov/nf-evntprov-eventdatadesccreate)
