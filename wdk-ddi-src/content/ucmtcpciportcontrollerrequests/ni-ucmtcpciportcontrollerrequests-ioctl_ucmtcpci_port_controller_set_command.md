---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND (ucmtcpciportcontrollerrequests.h)
description: Sets the value of a command register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.
old-location: buses\ioctl_ucmtcpci_port_controller_set_command.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND IOCTL"]
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND control, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND control code [Buses], buses.ioctl_ucmtcpci_port_controller_set_command, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND
req.header: ucmtcpciportcontrollerrequests.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND
 - ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - UcmTcpciPortControllerRequests.h
api_name:
 - IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND IOCTL


## -description

Sets the value of a command register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

A pointer to a <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_command_in_params">UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS</a> structure. To get the structure, call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputbuffer">WdfRequestRetrieveInputBuffer</a> by passing the received framework request object.

### -input-buffer-length

The size of the <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_command_in_params">UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS</a> structure.

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.

## -remarks

The UcmTcpciCx class extension sends this IOCTL request to set the value of the command register. The value to set is provided in the supplied structure. After setting the value in the register, client driver must call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> to complete the request.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
