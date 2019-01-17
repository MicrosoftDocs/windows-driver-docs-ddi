---
UID: NI:pcivirt.IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
title: IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
description: The request determines the ranges of memory-mapped I/O space that must mitigated.
old-location: pci\ioctl-sriov-query-mitigated-range-count.htm
tech.root: PCI
ms.assetid: 68fd97a5-b7ea-43c0-96ed-b64445fd21dd
ms.date: 02/24/2018
ms.keywords: IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT, IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT control code [Buses], PCI.ioctl-sriov-query-mitigated-range-count, pcivirt/IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
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
-	IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
product:
- Windows
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT IOCTL


##  Major Code:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


 The request determines the ranges of memory-mapped I/O space that must mitigated.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://msdn.microsoft.com/7de35a35-2b90-421d-bbde-4c5cb760070a">SRIOV_MITIGATED_RANGE_COUNT_INPUT</a> structure. Set the <b>VfIndex</b> member to 0.


### -input-buffer-length

The size of the <a href="https://msdn.microsoft.com/7de35a35-2b90-421d-bbde-4c5cb760070a">SRIOV_MITIGATED_RANGE_COUNT_INPUT</a> structure.


### -output-buffer

A pointer to a <a href="https://msdn.microsoft.com/b89c0758-beed-4c29-b966-78cb319258b1">SRIOV_MITIGATED_RANGE_COUNT_OUTPUT</a> structure that is filled by the physical function (PF) driver with  ranges of memory-mapped I/O space.


### -output-buffer-length

The size of the <a href="https://msdn.microsoft.com/b89c0758-beed-4c29-b966-78cb319258b1">SRIOV_MITIGATED_RANGE_COUNT_OUTPUT</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

TBD

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.


## -remarks



This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_MITIGABLE_DEVICE_INTERFACE.

The virtualization stack uses an I/O MMU to differentiate traffic coming from the various interfaces that the device exposes, enforcing policy about which regions of memory a device can access and which interrupts it can generate.

The request is sent to the physical function (PF) driver by the virtualization stack to find out the ranges of memory-mapped I/O space
in which the stack must place
intercepts  on those pages and send the requests to read and write values
within those pages to the PF driver.



