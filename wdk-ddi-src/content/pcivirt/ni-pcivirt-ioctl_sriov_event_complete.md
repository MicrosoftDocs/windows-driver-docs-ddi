---
UID: NI:pcivirt.IOCTL_SRIOV_EVENT_COMPLETE
title: IOCTL_SRIOV_EVENT_COMPLETE (pcivirt.h)
description: The request indicates that the virtualization stack or the SR-IOV device received one of the events listed in SRIOV_PF_EVENT.
old-location: pci\ioctl-sriov-event-complete.htm
tech.root: PCI
ms.assetid: 5299ec17-1fcb-4449-9ec4-73a4d818df0d
ms.date: 02/24/2018
ms.keywords: IOCTL_SRIOV_EVENT_COMPLETE, IOCTL_SRIOV_EVENT_COMPLETE control code [Buses], PCI.ioctl-sriov-event-complete, pcivirt/IOCTL_SRIOV_EVENT_COMPLETE
f1_keywords:
 - "pcivirt/IOCTL_SRIOV_EVENT_COMPLETE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Pcivirt.h
api_name:
- IOCTL_SRIOV_EVENT_COMPLETE
product:
- Windows
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# IOCTL_SRIOV_EVENT_COMPLETE IOCTL


##  Major Code:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a>

## -description


The  request indicates that the virtualization stack  or the SR-IOV device received one of the events listed in
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ne-pcivirt-_sriov_pf_event">SRIOV_PF_EVENT</a>.


## -ioctlparameters




### -input-buffer

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_pnp_event_complete">SRIOV_PNP_EVENT_COMPLETE</a> structure that contains the NTSTATUS code with which <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_notification">IOCTL_SRIOV_NOTIFICATION</a> request must be completed.


### -input-buffer-length

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_pnp_event_complete">SRIOV_PNP_EVENT_COMPLETE</a> structure.


### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.


## -remarks



This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

The virtualization stack sends the <b>IOCTL_SRIOV_EVENT_COMPLETE</b> request when the physical function (PF) driver completes the previously sent <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_notification">IOCTL_SRIOV_NOTIFICATION</a> request. The <b>IOCTL_SRIOV_EVENT_COMPLETE</b> request can be completed
synchronously.  The stack provides the NTSTATUS code to set for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_pnp_event_complete">SRIOV_PNP_EVENT_COMPLETE</a> is the input buffer.
