---
UID: NI:pcivirt.IOCTL_SRIOV_QUERY_MITIGATED_RANGES
title: IOCTL_SRIOV_QUERY_MITIGATED_RANGES
author: windows-driver-content
description: The request determines the specific ranges on which intercepts must be placed.
old-location: pci\ioctl-sriov-query-mitigated-ranges.htm
old-project: PCI
ms.assetid: 58b6e53d-be7a-4563-a27d-db216a12d60d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_SRIOV_QUERY_MITIGATED_RANGES, IOCTL_SRIOV_QUERY_MITIGATED_RANGES control code [Buses], PCI.ioctl-sriov-query-mitigated-ranges, pcivirt/IOCTL_SRIOV_QUERY_MITIGATED_RANGES
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
-	IOCTL_SRIOV_QUERY_MITIGATED_RANGES
product:
- Windows
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# IOCTL_SRIOV_QUERY_MITIGATED_RANGES IOCTL


##  Major Code: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


The request determines the specific ranges on which intercepts must be placed. 


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://msdn.microsoft.com/40b81630-997f-4427-8d02-5004de6fc943">SRIOV_MITIGATED_RANGES_INPUT</a> structure that specifies the virtual function (VF) whose ranges are to be mitigated.


### -input-buffer-length

The size of the <a href="https://msdn.microsoft.com/40b81630-997f-4427-8d02-5004de6fc943">SRIOV_MITIGATED_RANGES_INPUT</a> structure.


### -output-buffer

A pointer to a <a href="https://msdn.microsoft.com/f33f602e-0bce-4ac2-8bd8-8640b2376278">SRIOV_MITIGATED_RANGES_OUTPUT</a> structure that specifies the virtual function (VF) whose ranges were to mitigated.


### -output-buffer-length

The size of the <a href="https://msdn.microsoft.com/f33f602e-0bce-4ac2-8bd8-8640b2376278">SRIOV_MITIGATED_RANGES_OUTPUT</a> structure.


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_MITIGABLE_DEVICE_INTERFACE.

The virtualization stack uses an I/O MMU to differentiate traffic coming from the various interfaces that the device exposes, enforcing policy about which regions of memory a device can access and which interrupts it can generate. 

The request  is sent to the physical function (PF) by virtualization stack to get the specific ranges on which intercepts must be placed.



