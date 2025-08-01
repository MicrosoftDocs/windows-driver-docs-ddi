---
UID: NI:pcivirt.IOCTL_SRIOV_EVENT_COMPLETE
title: IOCTL_SRIOV_EVENT_COMPLETE (pcivirt.h)
description: The request indicates that the virtualization stack or the SR-IOV device received one of the events listed in SRIOV_PF_EVENT.
old-location: pci\ioctl-sriov-event-complete.htm
tech.root: PCI
ms.date: 08/01/2025
keywords: ["IOCTL_SRIOV_EVENT_COMPLETE IOCTL"]
ms.keywords: IOCTL_SRIOV_EVENT_COMPLETE, IOCTL_SRIOV_EVENT_COMPLETE control code [Buses], PCI.ioctl-sriov-event-complete, pcivirt/IOCTL_SRIOV_EVENT_COMPLETE
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
 - IOCTL_SRIOV_EVENT_COMPLETE
 - pcivirt/IOCTL_SRIOV_EVENT_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pcivirt.h
api_name:
 - IOCTL_SRIOV_EVENT_COMPLETE
---

# IOCTL_SRIOV_EVENT_COMPLETE IOCTL

## Major Code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/ifs/irp-mj-device-control)

## -description

The request indicates that the virtualization stack or the SR-IOV device received one of the events listed in [SRIOV_PF_EVENT](ne-pcivirt-_sriov_pf_event.md).

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/ifs/irp-mj-device-control)

### -input-buffer

A pointer to an [SRIOV_PNP_EVENT_COMPLETE](ns-pcivirt-_sriov_pnp_event_complete.md) structure that contains the NTSTATUS code with which [IOCTL_SRIOV_NOTIFICATION](ni-pcivirt-ioctl_sriov_notification.md) request must be completed.

### -input-buffer-length

The size of the [SRIOV_PNP_EVENT_COMPLETE](ns-pcivirt-_sriov_pnp_event_complete.md) structure.

### -output-buffer

None.

### -output-buffer-length

Zero.

### -in-out-buffer

None.

### -inout-buffer-length

Zero.

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) code.

## -remarks

This IOCTL request is sent by the virtualization stack to the PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

The virtualization stack sends the **IOCTL_SRIOV_EVENT_COMPLETE** request when the physical function (PF) driver completes the previously sent [IOCTL_SRIOV_NOTIFICATION](ni-pcivirt-ioctl_sriov_notification.md) request. The **IOCTL_SRIOV_EVENT_COMPLETE** request can be completed synchronously. The stack provides the NTSTATUS code to set for the [SRIOV_PNP_EVENT_COMPLETE](ns-pcivirt-_sriov_pnp_event_complete.md) is the input buffer.
