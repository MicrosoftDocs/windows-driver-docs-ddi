---
UID: NI:gnssdriver.IOCTL_GNSS_MODIFY_FIXSESSION
title: IOCTL_GNSS_MODIFY_FIXSESSION (gnssdriver.h)
description: The IOCTL_GNSS_MODIFY_FIXSESSION control code is used by the GNSS adapter to modify the fix session parameters of an active fix session.
old-location: gnss\ioctl_gnss_modify_fixsession.htm
tech.root: gnss
ms.assetid: AFBD14A5-AEDC-4C8B-AF5F-0F4D8DD61B78
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_MODIFY_FIXSESSION, IOCTL_GNSS_MODIFY_FIXSESSION control, IOCTL_GNSS_MODIFY_FIXSESSION control code [Sensor Devices], gnss.ioctl_gnss_modify_fixsession, gnssdriver/IOCTL_GNSS_MODIFY_FIXSESSION
ms.topic: ioctl
f1_keywords:
 - "gnssdriver/IOCTL_GNSS_MODIFY_FIXSESSION"
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
- IOCTL_GNSS_MODIFY_FIXSESSION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_MODIFY_FIXSESSION IOCTL


## -description


The <b>IOCTL_GNSS_MODIFY_FIXSESSION</b> control code is used by the GNSS adapter to modify the fix session parameters of an active fix session. This is only required when the GNSS driver does not support multiple fix session of the same fix type, for example, when the <b>SupportMultipleFixSession</b> capability of the driver is FALSE.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_fixsession_param">GNSS_FIXSESSION_PARAM</a> structure.




### -input-buffer-length

Set to sizeof(GNSS_FIXSESSION_PARAM).


### -output-buffer

Set to NULL.


### -output-buffer-length

Set to 0.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

