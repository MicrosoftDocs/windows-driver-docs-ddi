---
UID: NI:pcivirt.IOCTL_SRIOV_QUERY_MITIGATED_RANGES
title: IOCTL_SRIOV_QUERY_MITIGATED_RANGES (pcivirt.h)
description: The request determines the specific ranges on which intercepts must be placed.
old-location: pci\ioctl-sriov-query-mitigated-ranges.htm
tech.root: PCI
ms.date: 08/01/2025
keywords: ["IOCTL_SRIOV_QUERY_MITIGATED_RANGES IOCTL"]
ms.keywords: IOCTL_SRIOV_QUERY_MITIGATED_RANGES, IOCTL_SRIOV_QUERY_MITIGATED_RANGES control code [Buses], PCI.ioctl-sriov-query-mitigated-ranges, pcivirt/IOCTL_SRIOV_QUERY_MITIGATED_RANGES
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
 - IOCTL_SRIOV_QUERY_MITIGATED_RANGES
 - pcivirt/IOCTL_SRIOV_QUERY_MITIGATED_RANGES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pcivirt.h
api_name:
 - IOCTL_SRIOV_QUERY_MITIGATED_RANGES
---

# IOCTL_SRIOV_QUERY_MITIGATED_RANGES IOCTL

## Major Code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/ifs/irp-mj-device-control)

## -description

The request determines the specific ranges on which intercepts must be placed.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/ifs/irp-mj-device-control)

### -input-buffer

A pointer to a [SRIOV_MITIGATED_RANGES_INPUT](ns-pcivirt-_sriov_mitigated_ranges_input.md) structure that specifies the virtual function (VF) whose ranges are to be mitigated.

### -input-buffer-length

The size of the [SRIOV_MITIGATED_RANGES_INPUT](ns-pcivirt-_sriov_mitigated_ranges_input.md) structure.

### -output-buffer

A pointer to a [SRIOV_MITIGATED_RANGES_OUTPUT](ns-pcivirt-_sriov_mitigated_ranges_output.md) structure that specifies the virtual function (VF) whose ranges were to mitigated.

### -output-buffer-length

The size of the [SRIOV_MITIGATED_RANGES_OUTPUT](ns-pcivirt-_sriov_mitigated_ranges_output.md) structure.

### -in-out-buffer

Not used with this operation; set this parameter to **NULL**.

### -inout-buffer-length

Not used with this operation; set this parameter to zero.

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) code.

## -remarks

This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_MITIGABLE_DEVICE_INTERFACE.

The virtualization stack uses an I/O MMU to differentiate traffic coming from the various interfaces that the device exposes, enforcing policy about which regions of memory a device can access and which interrupts it can generate.

The request  is sent to the physical function (PF) by virtualization stack to get the specific ranges on which intercepts must be placed.
