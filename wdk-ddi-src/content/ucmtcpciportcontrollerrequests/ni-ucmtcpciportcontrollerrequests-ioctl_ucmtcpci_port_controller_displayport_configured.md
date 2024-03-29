---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED (ucmtcpciportcontrollerrequests.h)
description: Notifies the client driver that the DisplayPort alternate mode on the partner device has been configured with pin assignment so that the driver can perform additional tasks.
old-location: buses\ioctl_ucmtcpci_port_controller_displayport_configured.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED IOCTL"]
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED, IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED control, IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED control code [Buses], buses.ioctl_ucmtcpci_port_controller_displayport_configured, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED
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
 - IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED
 - ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - UcmTcpciPortControllerRequests.h
api_name:
 - IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED IOCTL


## -description

Notifies the client driver that the DisplayPort alternate mode on the partner device has been configured  with pin assignment so that the driver can perform additional tasks.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

A pointer to a <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_configured_in_params">UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS</a> structure that contains information about the pin assignment.

### -input-buffer-length

The size of <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_configured_in_params">UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS</a>.

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.

## -remarks

The UcmTcpciCx class extension sends this IOCTL request when the DisplayPort mode is configured. The client driver can determine the pin assignment based on the values passed in the supplied structure.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
