---
UID: NI:pcivirt.IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
title: IOCTL_SRIOV_MITIGATED_RANGE_UPDATE (pcivirt.h)
description: The IOCTL_SRIOV_MITIGATED_RANGE_UPDATE request indicates that the virtualization stack wants to update to the mitigation ranges.
old-location: pci\ioctl-sriov-mitigated-range-update.htm
tech.root: PCI
ms.date: 07/28/2025
keywords: ["IOCTL_SRIOV_MITIGATED_RANGE_UPDATE IOCTL"]
ms.keywords: IOCTL_SRIOV_MITIGATED_RANGE_UPDATE, IOCTL_SRIOV_MITIGATED_RANGE_UPDATE control code [Buses], PCI.ioctl-sriov-mitigated-range-update, pcivirt/IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
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
 - IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
 - pcivirt/IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pcivirt.h
api_name:
 - IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
---

# IOCTL_SRIOV_MITIGATED_RANGE_UPDATE IOCTL

## Major Code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/ifs/irp-mj-device-control)

## -description

The  **IOCTL_SRIOV_MITIGATED_RANGE_UPDATE** request indicates that the virtualization stack wants to update to the mitigation ranges.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/ifs/irp-mj-device-control)

### -input-buffer

A pointer to a [SRIOV_MITIGATED_RANGE_UPDATE_INPUT](ns-pcivirt-_sriov_mitigated_range_update_input.md) structure.

### -input-buffer-length

Size of the [SRIOV_MITIGATED_RANGE_UPDATE_INPUT](ns-pcivirt-_sriov_mitigated_range_update_input.md) structure.

### -output-buffer

A buffer that contains an [SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT](ns-pcivirt-_sriov_mitigated_range_update_output.md)-type value filled by the physical function (PF) driver when it completes the request.

### -output-buffer-length

A pointer to a variable to contain the number of bytes written to the output buffer when the request is completed.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) code.

## -remarks

This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes MITIGABLE_DEVICE_INTERFACE.

The stack uses an I/O MMU to differentiate traffic coming from the various interfaces that the device exposes, enforcing policy about which regions of memory a device can access and which interrupts it can generate. When that range of memory is updated, the stack sends this request.

The physical function (PF driver) keeps the **IOCTL_SRIOV_MITIGATED_RANGE_UPDATE** request in its queue until the request is either cancelled by the virtualization stack or the PF driver
wants to send a request to the virtual function (VF) driver to update to the mitigation ranges for a particular VF. When the VF completes the request, the PF completes the **IOCTL_SRIOV_MITIGATED_RANGE_UPDATE** request. Upon completion, the virtualization stack reinitializes the mitigation maps by sending [IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT](ni-pcivirt-ioctl_sriov_query_mitigated_range_count.md) and [IOCTL_SRIOV_QUERY_MITIGATED_RANGES](ni-pcivirt-ioctl_sriov_query_mitigated_ranges.md) requests. The stack may additionally  call any user mode device simulation for additional ranges to mitigate. The **IOCTL_SRIOV_MITIGATED_RANGE_UPDATE** request is sent for each active virtual function.
