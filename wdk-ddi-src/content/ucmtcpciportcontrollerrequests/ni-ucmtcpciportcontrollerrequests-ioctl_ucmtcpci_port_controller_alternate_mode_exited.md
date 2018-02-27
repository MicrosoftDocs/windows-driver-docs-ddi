---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED
author: windows-driver-content
description: Notifies the client driver that an alternate mode is exited so that the driver can perform additional tasks.
old-location: buses\ioctl_ucmtcpci_port_controller_alternate_mode_exited.htm
old-project: usbref
ms.assetid: 1B839FDC-E70B-4798-9169-AA3650625FDB
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED, IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED control code [Buses], buses.ioctl_ucmtcpci_port_controller_alternate_mode_exited, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UcmTcpciPortControllerRequests.h
api_name:
-	IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_IOCTL
req.product: Windows 10 or later.
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED IOCTL


##  Major Code: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


Notifies the client driver that an alternate mode is exited so that the driver can perform additional tasks.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="..\ucmtcpciportcontrollerrequests\ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_alternate_mode_exited_in_params.md">UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED_IN_PARAMS</a> structure that contains information about the alternate mode. 


### -input-buffer-length

The size of <a href="..\ucmtcpciportcontrollerrequests\ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_alternate_mode_exited_in_params.md">UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED_IN_PARAMS</a>.


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



The UcmTcpciCx class extension sends this IOCTL request when an alternate mode is exited. The client driver can determine the alternate mode that was entered based on the values passed in <i>SVID</i> and <i>Mode</i> of the supplied structure.




## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

