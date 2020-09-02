---
UID: NI:pcivirt.IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
title: IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT (pcivirt.h)
description: The request determines the ranges of memory-mapped I/O space that must mitigated.
old-location: pci\ioctl-sriov-query-mitigated-range-count.htm
tech.root: PCI
ms.assetid: 68fd97a5-b7ea-43c0-96ed-b64445fd21dd
ms.date: 02/24/2018
keywords: ["IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT IOCTL"]
ms.keywords: IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT, IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT control code [Buses], PCI.ioctl-sriov-query-mitigated-range-count, pcivirt/IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
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
 - IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
 - pcivirt/IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pcivirt.h
api_name:
 - IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
---

# IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT IOCTL


##  Major Code:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a>


## -description

 The request determines the ranges of memory-mapped I/O space that must mitigated.

## -ioctlparameters

### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_mitigated_range_count_input">SRIOV_MITIGATED_RANGE_COUNT_INPUT</a> structure. Set the <b>VfIndex</b> member to 0.

### -input-buffer-length

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_mitigated_range_count_input">SRIOV_MITIGATED_RANGE_COUNT_INPUT</a> structure.

### -output-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_mitigated_range_count_output">SRIOV_MITIGATED_RANGE_COUNT_OUTPUT</a> structure that is filled by the physical function (PF) driver with  ranges of memory-mapped I/O space.

### -output-buffer-length

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_mitigated_range_count_output">SRIOV_MITIGATED_RANGE_COUNT_OUTPUT</a> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

TBD

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.

## -remarks

This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_MITIGABLE_DEVICE_INTERFACE.

The virtualization stack uses an I/O MMU to differentiate traffic coming from the various interfaces that the device exposes, enforcing policy about which regions of memory a device can access and which interrupts it can generate.

The request is sent to the physical function (PF) driver by the virtualization stack to find out the ranges of memory-mapped I/O space
in which the stack must place
intercepts  on those pages and send the requests to read and write values
within those pages to the PF driver.

