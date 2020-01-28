---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT (ucmtcpciportcontrollerrequests.h)
description: Sets the TRANSMIT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.
old-location: buses\ioctl_ucmtcpci_port_controller_set_transmit.htm
tech.root: usbref
ms.assetid: 5E833F26-2BEC-4021-8D19-F9EFD49C7584
ms.date: 05/07/2018
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT control, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT control code [Buses], buses.ioctl_ucmtcpci_port_controller_set_transmit, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT
f1_keywords:
 - "ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT"
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
- IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT IOCTL


## -description


Sets the TRANSMIT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_transmit_in_params">UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS</a> structure that contains the value to set in the TRANSMIT Register. To get the structure, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputbuffer">WdfRequestRetrieveInputBuffer</a> by passing the received framework request object. This structure is declared in UcmTcpciSpec.h.


### -input-buffer-length

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_transmit_in_params">UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS</a> structure.


### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



The UcmTcpciCx class extension sends this IOCTL request to set the TRANSMIT Register. The value to set is provided in the supplied structure. After setting the value in the register, client driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> to complete the request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

