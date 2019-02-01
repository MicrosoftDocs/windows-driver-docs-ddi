---
UID: NI:pcivirt.IOCTL_SRIOV_NOTIFICATION
title: IOCTL_SRIOV_NOTIFICATION (pcivirt.h)
description: The request indicates that the virtualization stack wants to be notified when one of the events listed in SRIOV_PF_EVENT occurs.
old-location: pci\ioctl-sriov-notification.htm
tech.root: PCI
ms.assetid: 3f2d67e0-abab-40a1-b4a9-cb65e81884e9
ms.date: 02/24/2018
ms.keywords: IOCTL_SRIOV_NOTIFICATION, IOCTL_SRIOV_NOTIFICATION control code [Buses], PCI.ioctl-sriov-notification, pcivirt/IOCTL_SRIOV_NOTIFICATION
ms.topic: ioctl
req.header: pcivirt.h
req.include-header:
req.target-type: Windows
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
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Pcivirt.h
api_name:
-	IOCTL_SRIOV_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# IOCTL_SRIOV_NOTIFICATION IOCTL


##  Major Code:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


The  request indicates that the virtualization stack wants to be notified when one of the events listed in
<a href="https://msdn.microsoft.com/e2b40a9d-57e6-49b1-839a-d34acb108807">SRIOV_PF_EVENT</a> occurs.


## -ioctlparameters


### -output-buffer

A buffer that contains an <a href="https://msdn.microsoft.com/e2b40a9d-57e6-49b1-839a-d34acb108807">SRIOV_PF_EVENT</a>-type value that is filled by the  physical function (PF) driver when it completes the request.


### -output-buffer-length

A pointer to the variable, which is assigned the number of written bytes to the output buffer when the request is completed.


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.


## -remarks



This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

The <b>IOCTL_SRIOV_NOTIFICATION</b> request is held in a queue by the PF driver until the request is either cancelled by sender or the device experiences one of the events listed in
<a href="https://msdn.microsoft.com/e2b40a9d-57e6-49b1-839a-d34acb108807">SRIOV_PF_EVENT</a>. The driver then completes the pending request.


If the PF driver receives this IOCTL request while processing a Plug and Play event  for which the driver has not yet completed a notification, it should complete the IOCTL request immediately with the event details in the output buffer.  Otherwise, the driver should queue the request until either it is cancelled or a Plug and Play event that requires notification occurs.

The virtualization stack can send the <b>IOCTL_SRIOV_NOTIFICATION</b> request immediately after the previous <b>IOCTL_SRIOV_NOTIFICATION</b> request completes.   The PF driver must keep track of the fact
that an event notification has been delivered and must not complete two IOCTL requests for the same event twice.

  It is pended by the PF driver until it is canceled by the sender or until the PF driver experiences one of several PnP events, at which point it is completed.

```cpp

case IOCTL_SRIOV_NOTIFICATION:
        TraceEvents(TRACE_LEVEL_VERBOSE, DBG_IOCTL,
            "IOCTL_SRIOV_NOTIFICATION:\n");

        status = WdfRequestForwardToIoQueue(Request,
                                            fdoContext-&gt;NotificationQueue);
        if (!NT_SUCCESS(status))
        {
            // not able to push it into manual queue, too bad.
            TraceEvents(TRACE_LEVEL_ERROR, DBG_PNP,
                        "WdfRequestForwardToIoQueue failed status=%!STATUS!\n",
                        status);
            break;
        }

        //
        // Pnp might arrived before SRIOV_NOTIFICATION. Serve the new
        // outstanding pnp if there is one.
        //
        CheckPendingNotifications(fdoContext);
        status = STATUS_PENDING;
        break;



```

```cpp
VOID
CheckPendingNotifications(
    __in PDEVICE_CONTEXT DeviceContext
    )
/*++

Routine Description:

    This routine checks if there is a pending event and a pending request
    for notification and if so completes the request.

Arguments:

    DeviceContext - Pointer to the device context

Return Value:

    None.

--*/
{
    PSRIOV_PF_EVENT notification;
    WDFQUEUE        queue;
    WDFREQUEST      request;
    NTSTATUS        status;

    PAGED_CODE();

    WdfWaitLockAcquire(DeviceContext-&gt;PnpStateLock, NULL);

    queue = DeviceContext-&gt;NotificationQueue;
    if (DeviceContext-&gt;PnpEventNew
        &amp;&amp; NT_SUCCESS(WdfIoQueueRetrieveNextRequest(queue, &amp;request)))
    {
        NT_ASSERT(DeviceContext-&gt;PnpEventPending != FALSE);
        DeviceContext-&gt;PnpEventNew = FALSE;

        status = WdfRequestRetrieveOutputBuffer(request,
                                                sizeof(*notification),
                                                &amp;notification,
                                                NULL);
        if (!NT_SUCCESS(status))
        {
            TraceEvents(TRACE_LEVEL_ERROR, DBG_PNP,
                "WdfRequestRetrieveOutputBuffer[SRIOV_NOTIFICATION] fail: %!STATUS!", status);
            WdfRequestComplete(request, status);
        }
        else
        {
            TraceEvents(TRACE_LEVEL_VERBOSE, DBG_IOCTL, "Retrieved IoQueue request buffer (notification)\n");

            *notification = DeviceContext-&gt;PnpEventCode;
            WdfRequestCompleteWithInformation(request,
                                              STATUS_SUCCESS,
                                              sizeof(*notification));
        }
    }

    WdfWaitLockRelease(DeviceContext-&gt;PnpStateLock);

    return;
}
```


