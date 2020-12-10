---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED (ucmtcpciportcontrollerrequests.h)
description: Notifies the client driver that an alternate mode is entered so that the driver can perform additional tasks.
old-location: buses\ioctl_ucmtcpci_port_controller_alternate_mode_entered.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED IOCTL"]
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED, IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED control, IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED control code [Buses], buses.ioctl_ucmtcpci_port_controller_alternate_mode_entered, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED
 - ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - UcmTcpciPortControllerRequests.h
api_name:
 - IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED IOCTL


## -description

Notifies the client driver that an alternate mode is entered so that the driver can perform additional tasks.

## -ioctlparameters

### -input-buffer

A pointer to a <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_alternate_mode_entered_in_params">UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS</a> structure that contains information about the alternate mode.

### -input-buffer-length

The size of <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_alternate_mode_entered_in_params">UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS</a>.

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.

## -remarks

The UcmTcpciCx class extension sends this IOCTL request when an alternate mode is entered. The client driver can determine the alternate mode that was entered based on the values passed in <i>SVID</i> and <i>Mode</i> of the supplied structure.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
