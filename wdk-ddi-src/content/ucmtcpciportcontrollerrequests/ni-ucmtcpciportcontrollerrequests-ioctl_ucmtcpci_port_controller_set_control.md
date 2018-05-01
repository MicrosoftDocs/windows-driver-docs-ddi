---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL
author: windows-driver-content
description: Sets the value of a control register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.
old-location: buses\ioctl_ucmtcpci_port_controller_set_control.htm
old-project: usbref
ms.assetid: F37BFBBE-B175-40AE-BE34-A4D6B00735D0
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL control, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL control code [Buses], buses.ioctl_ucmtcpci_port_controller_set_control, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UcmTcpciPortControllerRequests.h
api_name:
-	IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL IOCTL


## -description


Sets the value of a control register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. 


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt805883">UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS</a> structure that contains the type of register and the value to set. 


### -input-buffer-length

The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805883">UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS</a> structure.


### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



The UcmTcpciCx class extension sends this IOCTL request to set values to the control register. Only one register can be set per request. The type and value to set is provided in the supplied structure. After setting the value in the register, client driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

