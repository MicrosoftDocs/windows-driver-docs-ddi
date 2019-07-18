---
UID: NI:swenum.IOCTL_SWENUM_INSTALL_INTERFACE
title: IOCTL_SWENUM_INSTALL_INTERFACE (swenum.h)
description: 
old-location: stream\ioctl_swenum_install_interface.htm
tech.root: stream
ms.assetid: 23EC4771-44DF-4437-88E1-4039E0EB6F8F
ms.date: 04/23/2018
ms.keywords: IOCTL_SWENUM_INSTALL_INTERFACE, IOCTL_SWENUM_INSTALL_INTERFACE control, IOCTL_SWENUM_INSTALL_INTERFACE control code [Streaming Media Devices], stream.ioctl_swenum_install_interface, swenum/IOCTL_SWENUM_INSTALL_INTERFACE
ms.topic: ioctl
f1_keywords:
 - "swenum/IOCTL_SWENUM_INSTALL_INTERFACE"
req.header: swenum.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- swenum.h
api_name:
- IOCTL_SWENUM_INSTALL_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SWENUM_INSTALL_INTERFACE IOCTL


## -description





## -ioctlparameters




### -input-buffer




### -input-buffer-length




### -output-buffer




### -output-buffer-length




### -in-out-buffer




### -inout-buffer-length




### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

