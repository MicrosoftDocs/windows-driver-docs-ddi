---
UID: NI:pcivirt.IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
title: IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
author: windows-driver-content
description: The request determines the ranges of memory-mapped I/O space that must mitigated.
old-location: pci\ioctl-sriov-query-mitigated-range-count.htm
old-project: PCI
ms.assetid: 68fd97a5-b7ea-43c0-96ed-b64445fd21dd
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
req.alt-api: IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT
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

# IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT IOCTL



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

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
TBD

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks
This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

The virtualization stack uses an I/O MMU to differentiate traffic coming from the various interfaces that the device exposes, enforcing policy about which regions of memory a device can access and which interrupts it can generate. 

The request is sent to the physical function (PF) driver by the virtualization stack to find out the ranges of memory-mapped I/O space
in which the stack must place
intercepts  on those pages and send the requests to read and write values
within those pages to the PF driver.</p>