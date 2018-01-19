---
UID: NI:pcivirt.IOCTL_SRIOV_EVENT_COMPLETE
title: IOCTL_SRIOV_EVENT_COMPLETE
author: windows-driver-content
description: The request indicates that the virtualization stack or the SR-IOV device received one of the events listed in SRIOV_PF_EVENT.
old-location: pci\ioctl-sriov-event-complete.htm
old-project: PCI
ms.assetid: 5299ec17-1fcb-4449-9ec4-73a4d818df0d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SRIOV_PF_EVENT, SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SRIOV_EVENT_COMPLETE
req.alt-loc: Pcivirt.h
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
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# IOCTL_SRIOV_EVENT_COMPLETE IOCTL



## -description
The  request indicates that the virtualization stack  or the SR-IOV device received one of the events listed in
<a href="https://msdn.microsoft.com/e2b40a9d-57e6-49b1-839a-d34acb108807">SRIOV_PF_EVENT</a>.



## -syntax

````
    case IOCTL_SRIOV_NOTIFICATION:
        TraceEvents(TRACE_LEVEL_VERBOSE, DBG_IOCTL, 
            "IOCTL_SRIOV_NOTIFICATION:\n");

        status = WdfRequestForwardToIoQueue(Request,
                                            fdoContext->NotificationQueue);
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




````


## -ioctlparameters

### -input-buffer
A pointer to an <a href="https://msdn.microsoft.com/3b40d780-8084-4c19-bb8e-9d1ab3dadc95">SRIOV_PNP_EVENT_COMPLETE</a> structure that contains the NTSTATUS code with which <a href="https://msdn.microsoft.com/3f2d67e0-abab-40a1-b4a9-cb65e81884e9">IOCTL_SRIOV_NOTIFICATION</a> request must be completed.


### -input-buffer-length
The size of the <a href="https://msdn.microsoft.com/3b40d780-8084-4c19-bb8e-9d1ab3dadc95">SRIOV_PNP_EVENT_COMPLETE</a> structure.


### -output-buffer

<text></text>

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks
This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

The virtualization stack sends the <b>IOCTL_SRIOV_EVENT_COMPLETE</b> request when the physical function (PF) driver completes the previously sent <a href="https://msdn.microsoft.com/3f2d67e0-abab-40a1-b4a9-cb65e81884e9">IOCTL_SRIOV_NOTIFICATION</a> request. The <b>IOCTL_SRIOV_EVENT_COMPLETE</b> request can be completed
synchronously.  The stack provides the NTSTATUS code to set for the <a href="https://msdn.microsoft.com/3b40d780-8084-4c19-bb8e-9d1ab3dadc95">SRIOV_PNP_EVENT_COMPLETE</a> is the input buffer. The code indicates the status code o use for completion of the event.
</p>