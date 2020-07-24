---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL (ucmtcpciportcontrollerrequests.h)
description: Sets the value of a control register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.
old-location: buses\ioctl_ucmtcpci_port_controller_set_control.htm
tech.root: usbref
ms.assetid: F37BFBBE-B175-40AE-BE34-A4D6B00735D0
ms.date: 05/07/2018
keywords: ["IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL IOCTL"]
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL control, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL control code [Buses], buses.ioctl_ucmtcpci_port_controller_set_control, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL
f1_keywords:
 - "ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL"
 - "IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- UcmTcpciPortControllerRequests.h
api_name:
- IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL
targetos: Windows
req.typenames: 
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL IOCTL


## -description


Sets the value of a control register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. 


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_control_in_params">UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS</a> structure that contains the type of register and the value to set. 


### -input-buffer-length

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_control_in_params">UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS</a> structure.


### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



The UcmTcpciCx class extension sends this IOCTL request to set values to the control register. Only one register can be set per request. The type and value to set is provided in the supplied structure. After setting the value in the register, client driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> to complete the request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

