---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED (ucmtcpciportcontrollerrequests.h)
description: Notifies the client driver that the hot-plug detect status of the DisplayPort connection has changed so that the driver can perform additional tasks.
old-location: buses\ioctl_ucmtcpci_port_controller_displayport_hpd_status_changed.htm
tech.root: usbref
ms.assetid: 5FF692BE-14D2-403A-B7B3-C13CAFBECE05
ms.date: 05/07/2018
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED, IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED control, IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED control code [Buses], buses.ioctl_ucmtcpci_port_controller_displayport_hpd_status_changed, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED
ms.topic: ioctl
f1_keywords:
 - "ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED"
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
- IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED IOCTL


## -description


Notifies the client driver that the hot-plug detect status of the DisplayPort connection has changed so that the driver can perform additional tasks.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_hpd_status_changed_in_params">UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS</a> structure that contains status information.


### -input-buffer-length

The size of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_hpd_status_changed_in_params">UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS</a>.


### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



The UcmTcpciCx class extension sends this IOCTL request when the DisplayPort mode status changes. The client driver can determine the new status based on the values passed in the supplied structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

