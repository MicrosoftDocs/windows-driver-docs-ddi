---
UID: NI:gnssdriver.IOCTL_GNSS_MODIFY_FIXSESSION
title: IOCTL_GNSS_MODIFY_FIXSESSION
author: windows-driver-content
description: The IOCTL_GNSS_MODIFY_FIXSESSION control code is used by the GNSS adapter to modify the fix session parameters of an active fix session.
old-location: sensors\ioctl_gnss_modify_fixsession.htm
old-project: sensors
ms.assetid: AFBD14A5-AEDC-4C8B-AF5F-0F4D8DD61B78
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_GNSS_MODIFY_FIXSESSION, IOCTL_GNSS_MODIFY_FIXSESSION control code [Sensor Devices], gnssdriver/IOCTL_GNSS_MODIFY_FIXSESSION, sensors.ioctl_gnss_modify_fixsession
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
-	IOCTL_GNSS_MODIFY_FIXSESSION
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_MODIFY_FIXSESSION IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_GNSS_MODIFY_FIXSESSION</b> control code is used by the GNSS adapter to modify the fix session parameters of an active fix session. This is only required when the GNSS driver does not support multiple fix session of the same fix type, for example, when the <b>SupportMultipleFixSession</b> capability of the driver is FALSE.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="..\gnssdriver\ns-gnssdriver-gnss_fixsession_param.md">GNSS_FIXSESSION_PARAM</a> structure.




### -input-buffer-length

Set to sizeof(GNSS_FIXSESSION_PARAM).


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



The driver sets an NTSTATUS value to indicate one of the following results.

<ul>
<li>
The fix session was successfully modified.

</li>
<li>
The fix session is currently stopped or not active.

</li>
<li>
The fix session parameter could not be modified.

</li>
</ul>
<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter uses this IOCTL to change the fix session parameters of an active fix session to accommodate new fix requests from the LBS applications. 


If the call fails, the GNSS adapter will not multiplex the new fix request into the existing active session. Instead it will continue expecting that the active fix session has remained unchanged.

If the call succeeds, the GNSS adapter will expect the subsequent fix data to adhere to the newly specified session parameters.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
If multi-session support is not present, the GNSS driver must support this IOCTL and change the fix session parameters on the fly for the active session.

Once the GNSS driver accepts the fix session parameters, validates them, and sends them to the GNSS engine, it should immediately complete the I/O request with a success return code.

Upon successful completion, the GNSS driver should return all fix data according to the new fix session parameters. However, fix data that’s already in the process of being provided to the GNSS adapter should still be made available and should not be discarded. 





## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_MODIFY_FIXSESSION control code%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

