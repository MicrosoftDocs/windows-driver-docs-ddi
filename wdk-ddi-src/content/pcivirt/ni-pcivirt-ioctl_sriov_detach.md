---
UID: NI:pcivirt.IOCTL_SRIOV_DETACH
title: IOCTL_SRIOV_DETACH (pcivirt.h)
description: The request indicates that the virtualization stack wants to unregister for Plug and Play events (previously registered through the IOCTL_SRIOV_ATTACH request).
old-location: pci\ioctl-sriov-detach.htm
tech.root: PCI
ms.assetid: 8ede4a48-317b-46be-834a-a67b638b28c0
ms.date: 02/24/2018
keywords: ["IOCTL_SRIOV_DETACH IOCTL"]
ms.keywords: IOCTL_SRIOV_DETACH, IOCTL_SRIOV_DETACH control code [Buses], PCI.ioctl-sriov-detach, pcivirt/IOCTL_SRIOV_DETACH
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
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
f1_keywords:
 - IOCTL_SRIOV_DETACH
 - pcivirt/IOCTL_SRIOV_DETACH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pcivirt.h
api_name:
 - IOCTL_SRIOV_DETACH
---

# IOCTL_SRIOV_DETACH IOCTL


##  Major Code:


<a href="/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a>


## -description

The  request indicates that the virtualization stack wants to unregister for Plug and Play events (previously registered through the <a href="/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_attach">IOCTL_SRIOV_ATTACH</a> request).

## -ioctlparameters

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.

## -remarks

This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

From here on, the PF should not expect to receive  <a href="/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_event_complete">IOCTL_SRIOV_EVENT_COMPLETE</a> and <a href="/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_notification">IOCTL_SRIOV_NOTIFICATION</a> requests.


The driver that must stop waiting for <a href="/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_event_complete">IOCTL_SRIOV_EVENT_COMPLETE</a>.
If the driver is currently waiting it should stop waiting and continue
 processing Plug and Play IRPs.

In this example handling of the IOCTL_SRIOV_DETACH request, the PF driver maintains PnP states in its device context. The deviceContext->PnpRebalancing is set to TRUE, when the driver receives <a href="/windows-hardware/drivers/kernel/irp-mn-query-stop-device">IRP_MN_QUERY_STOP_DEVICE</a> and set to FALSE when it receives IRP_MN_START_DEVICE.


```cpp
    case IOCTL_SRIOV_DETACH:

        WdfWaitLockAcquire(deviceContext->PnpStateLock, NULL);

        deviceContext->PnpVspAttached = FALSE;

        if (deviceContext->PnpRebalancing != FALSE)
        {
            //
            // Any new client (VSP state machine) will not know about
            // the current rebalance is it should block attach until
            // rebalance is over.
            //

    								deviceContext>PnpSafeToAttach = FALSE;
    								KeClearEvent(&deviceContext>PnpSafeEvent);

        }

        //
        // Unblock the PnP thread if it waiting for an IO control from the
        // client as the client just detached.
        //
        deviceContext->PnpEventStatus = STATUS_SUCCESS;
        KeSetEvent(&deviceContext->PnpUnblockEvent, IO_NO_INCREMENT, FALSE);

        WdfWaitLockRelease(deviceContext->PnpStateLock);

        status = STATUS_SUCCESS;
        break;



```


## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_attach">IOCTL_SRIOV_ATTACH</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>