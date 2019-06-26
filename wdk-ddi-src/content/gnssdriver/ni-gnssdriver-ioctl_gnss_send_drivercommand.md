---
UID: NI:gnssdriver.IOCTL_GNSS_SEND_DRIVERCOMMAND
title: IOCTL_GNSS_SEND_DRIVERCOMMAND (gnssdriver.h)
description: The IOCTL_GNSS_SEND_DRIVERCOMMAND control code is used by the GNSS adapter to execute well-defined commands on the driver and also to set driver configuration parameters.
old-location: gnss\ioctl_gnss_send_drivercommand.htm
tech.root: gnss
ms.assetid: CC991E95-D7E2-4B40-9D51-EA38C6732C7B
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_SEND_DRIVERCOMMAND, IOCTL_GNSS_SEND_DRIVERCOMMAND control, IOCTL_GNSS_SEND_DRIVERCOMMAND control code [Sensor Devices], gnss.ioctl_gnss_send_drivercommand, gnssdriver/IOCTL_GNSS_SEND_DRIVERCOMMAND
ms.topic: ioctl
req.header: gnssdriver.h
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
- gnssdriver.h
api_name:
- IOCTL_GNSS_SEND_DRIVERCOMMAND
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_SEND_DRIVERCOMMAND IOCTL


## -description


The <b>IOCTL_GNSS_SEND_DRIVERCOMMAND</b> control code is used by the GNSS adapter to execute well-defined commands on the driver and also to set driver configuration parameters. Each call specifies a certain command type, and the associated data for the command (if one is applicable) through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gnssdriver/ns-gnssdriver-gnss_drivercommand_param">GNSS_DRIVERCOMMAND_PARAM</a> structure.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gnssdriver/ns-gnssdriver-gnss_drivercommand_param">GNSS_DRIVERCOMMAND_PARAM</a> structure.


### -input-buffer-length

Set to sizeof(GNSS_DRIVERCOMMAND_PARAM).


### -output-buffer

Set to NULL.


### -output-buffer-length

Set to 0.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



The driver sets one of the following NTSTATUS values to indicate the result.

<ul>
<li>
STATUS_SUCCESS



</li>
<li>
Command Not Supported

</li>
<li>
Command Not Executed

</li>
<li>
Command Deferred

</li>
<li>
Command Failed

</li>
</ul>
<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
With the exception of a few commands, the GNSS adapter generally ignores any failures encountered in executing a specific command.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
If the GNSS driver does not support a specific command, it indicates so. Drivers are not required to support all commands defined in this protocol. The driver should complete the I/O only after finishing executing of the command.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

