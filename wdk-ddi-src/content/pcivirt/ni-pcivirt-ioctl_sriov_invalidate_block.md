---
UID: NI:pcivirt.IOCTL_SRIOV_INVALIDATE_BLOCK
title: IOCTL_SRIOV_INVALIDATE_BLOCK
author: windows-driver-content
description: The IOCTL_SRIOV_INVALIDATE_BLOCK request indicates that the virtualization stack wants to reset the contents of the specified configuration block.
old-location: pci\ioctl-sriov-invalidate-block.htm
tech.root: PCI
ms.assetid: b6f0e65f-c8e4-418f-a4b2-a7037368d5a3
ms.date: 02/24/2018
ms.keywords: IOCTL_SRIOV_INVALIDATE_BLOCK, IOCTL_SRIOV_INVALIDATE_BLOCK control code [Buses], PCI.ioctl-sriov-invalidate-block, pcivirt/IOCTL_SRIOV_INVALIDATE_BLOCK
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
-	IOCTL_SRIOV_INVALIDATE_BLOCK
product:
- Windows
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# IOCTL_SRIOV_INVALIDATE_BLOCK IOCTL


##  Major Code:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


The  <b>IOCTL_SRIOV_INVALIDATE_BLOCK</b> request indicates that the virtualization stack wants to reset the contents of the specified configuration block.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://msdn.microsoft.com/483e6144-9752-4d47-9ed4-7e73bc0a59cc">SRIOV_INVALIDATE_BLOCK</a> structure  that contains the configuration block to invalidate.


### -input-buffer-length

The size of the <a href="https://msdn.microsoft.com/483e6144-9752-4d47-9ed4-7e73bc0a59cc">SRIOV_INVALIDATE_BLOCK</a> structure.


### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.


## -remarks



This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

The   request  is sent to the physical function (PF) driver by VSP.
The PF driver completes the request when the driver wants to indicate to the virtual function (VF) driver that
one or more of the configuration blocks need  to be read again.



