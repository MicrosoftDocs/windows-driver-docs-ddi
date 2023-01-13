---
UID: NF:wdm.IoReportTargetDeviceChangeAsynchronous
title: IoReportTargetDeviceChangeAsynchronous function (wdm.h)
description: The IoReportTargetDeviceChangeAsynchronous routine notifies the PnP manager that a custom event has occurred on a device.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["IoReportTargetDeviceChangeAsynchronous function"]
ms.keywords: IoReportTargetDeviceChangeAsynchronous, IoReportTargetDeviceChangeAsynchronous routine [Kernel-Mode Driver Architecture], k104_b66839d5-f3b6-4f30-bf24-7b4ee869e733.xml, kernel.ioreporttargetdevicechangeasynchronous, wdm/IoReportTargetDeviceChangeAsynchronous
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - IoReportTargetDeviceChangeAsynchronous
 - wdm/IoReportTargetDeviceChangeAsynchronous
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoReportTargetDeviceChangeAsynchronous
---

## -description

The **IoReportTargetDeviceChangeAsynchronous** routine notifies the PnP manager that a custom event has occurred on a device.

## -parameters

### -param PhysicalDeviceObject [in]

Pointer to the PDO of the device being reported.

### -param NotificationStructure [in]

Pointer to a caller-supplied [**TARGET_DEVICE_CUSTOM_NOTIFICATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_target_device_custom_notification) structure describing the custom event. The PnP manager sends this structure to drivers that registered for notification of the event.

*NotificationStructure*.**FileObject** must be **NULL**. *NotificationStructure*.**Event** must contain the custom GUID for the event. The other fields of the *NotificationStructure* must be filled in as appropriate for the custom event.

The PnP manager fills in the *NotificationStructure*.**FileObject** field when it sends notifications to registrants.

### -param Callback [in, optional]

Optionally points to a caller-supplied routine that the PnP manager calls after it finishes notifying drivers that registered for this custom event.

The callback routine has the following type:

```cpp
typedef
VOID
(*PDEVICE_CHANGE_COMPLETE_CALLBACK)(
    IN PVOID Context
    );
```

A device-change-complete callback routine should not block and must not call synchronous routines that generate PnP events.

The PnP manager calls device-change-complete callback routines at IRQL = PASSIVE_LEVEL.

### -param Context [in, out]

Optionally points to a caller-supplied context structure that the PnP manager passes to the *Callback* routine. The caller must allocate this structure from nonpaged memory.

## -returns

| Return code | Description |
|---|---|
| **STATUS_INVALID_DEVICE_REQUEST** | The caller specified a system PnP event, such as GUID_TARGET_DEVICE_QUERY_REMOVE. This routine is only for custom events. |

## -remarks

After the **IoReportTargetDeviceChangeAsynchronous** routine notifies the PnP manager that a custom event has occurred on a device, the routine returns immediately; it does not wait while the PnP manager sends notification of the event to drivers that registered for notification on the device. Do not use this routine to report system PnP events, such as GUID_TARGET_DEVICE_REMOVE_COMPLETE.

A driver that defines a custom device event calls **IoReportTargetDeviceChangeAsynchronous** to inform the PnP manager that the custom event has occurred. Custom notification can be used for events like a volume label change.

The custom notification structure contains a driver-defined event with its own GUID. Driver writers can generate GUIDs with Uuidgen.exe or Guidgen.exe (which are included in the Microsoft Windows SDK).

When a driver calls this routine while handling an event, an [IRP_MN_REMOVE_DEVICE](/windows-hardware/drivers/kernel/irp-mn-remove-device), or an [IRP_MN_SURPRISE_REMOVAL](/windows-hardware/drivers/kernel/irp-mn-surprise-removal), the PnP manager calls the driver's *Callback* routine after the driver returns and the stack unwinds.

Callers of **IoReportTargetDeviceChangeAsynchronous** must be running at IRQL <= DISPATCH_LEVEL. If a driver writer calls this routine at IRQL = DISPATCH_LEVEL, the *NotificationStructure* must be allocated from nonpaged memory.

## -see-also

[IoReportTargetDeviceChange](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreporttargetdevicechange)

[**TARGET_DEVICE_CUSTOM_NOTIFICATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_target_device_custom_notification)
