---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED (ucmtcpciportcontrollerrequests.h)
description: Notifies the client driver that an alternate mode is exited so that the driver can perform additional tasks.
old-location: buses\ioctl_ucmtcpci_port_controller_alternate_mode_exited.htm
tech.root: usbref
ms.assetid: 1B839FDC-E70B-4798-9169-AA3650625FDB
ms.date: 05/07/2018
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED, IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED control, IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED control code [Buses], buses.ioctl_ucmtcpci_port_controller_alternate_mode_exited, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED
ms.topic: ioctl
f1_keywords:
 - "ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED"
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- UcmTcpciPortControllerRequests.h
api_name:
- IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED IOCTL


## -description


Notifies the client driver that an alternate mode is exited so that the driver can perform additional tasks.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_alternate_mode_exited_in_params">UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED_IN_PARAMS</a> structure that contains information about the alternate mode. 


### -input-buffer-length

The size of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_alternate_mode_exited_in_params">UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED_IN_PARAMS</a>.


### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



The UcmTcpciCx class extension sends this IOCTL request when an alternate mode is exited. The client driver can determine the alternate mode that was entered based on the values passed in <i>SVID</i> and <i>Mode</i> of the supplied structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

