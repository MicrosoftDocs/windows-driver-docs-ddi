---
UID: NI:gnssdriver.IOCTL_GNSS_SEND_DRIVERCOMMAND
title: IOCTL_GNSS_SEND_DRIVERCOMMAND
author: windows-driver-content
description: The IOCTL_GNSS_SEND_DRIVERCOMMAND control code is used by the GNSS adapter to execute well-defined commands on the driver and also to set driver configuration parameters.
old-location: sensors\ioctl_gnss_send_drivercommand.htm
old-project: sensors
ms.assetid: CC991E95-D7E2-4B40-9D51-EA38C6732C7B
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_GNSS_SEND_DRIVERCOMMAND, IOCTL_GNSS_SEND_DRIVERCOMMAND control code [Sensor Devices], gnssdriver/IOCTL_GNSS_SEND_DRIVERCOMMAND, sensors.ioctl_gnss_send_drivercommand
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	IOCTL_GNSS_SEND_DRIVERCOMMAND
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_SEND_DRIVERCOMMAND IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_GNSS_SEND_DRIVERCOMMAND</b> control code is used by the GNSS adapter to execute well-defined commands on the driver and also to set driver configuration parameters. Each call specifies a certain command type, and the associated data for the command (if one is applicable) through the <a href="..\gnssdriver\ns-gnssdriver-gnss_drivercommand_param.md">GNSS_DRIVERCOMMAND_PARAM</a> structure.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="..\gnssdriver\ns-gnssdriver-gnss_drivercommand_param.md">GNSS_DRIVERCOMMAND_PARAM</a> structure.


### -input-buffer-length

Set to sizeof(GNSS_DRIVERCOMMAND_PARAM).


### -output-buffer

Set to NULL.


### -output-buffer-length

Set to 0.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


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

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_SEND_DRIVERCOMMAND control code%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

