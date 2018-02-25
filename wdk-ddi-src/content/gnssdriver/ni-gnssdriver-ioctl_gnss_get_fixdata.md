---
UID: NI:gnssdriver.IOCTL_GNSS_GET_FIXDATA
title: IOCTL_GNSS_GET_FIXDATA
author: windows-driver-content
description: The IOCTL_GNSS_GET_FIXDATA control code is used by the GNSS adapter to register to receive the next fix data from an active fix session.
old-location: sensors\ioctl_gnss_get_fixdata.htm
old-project: sensors
ms.assetid: 037B5AD9-39C2-4F50-8E63-0736EA37FEF9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_GNSS_GET_FIXDATA, IOCTL_GNSS_GET_FIXDATA control code [Sensor Devices], gnssdriver/IOCTL_GNSS_GET_FIXDATA, sensors.ioctl_gnss_get_fixdata
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	IOCTL_GNSS_GET_FIXDATA
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_GET_FIXDATA IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_GNSS_GET_FIXDATA</b> 
   control code is used by the GNSS adapter to register to receive the next fix data from an active fix session. This IOCTL provides the GNSS driver with a pending I/O request, the asynchronous resolution of which notifies the adapter that data is being provided through the overlapped structures <b>GnssEvent</b> member as a data buffer. The GnssEvent member is a <a href="..\gnssdriver\ne-gnssdriver-gnss_event_type.md">GNSS_EVENT</a> structure.



## -ioctlparameters




### -input-buffer

Pointer to a DWORD value that represents the fix session ID.




### -input-buffer-length

Set to sizeof(DWORD).




### -output-buffer

Set to NULL


### -output-buffer-length

Set to 0.




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



<h3><a id="Input"></a><a id="input"></a><a id="INPUT"></a>Input</h3>
<b>FixSessionID</b>: Session ID for an active fix.

<h3><a id="Output"></a><a id="output"></a><a id="OUTPUT"></a>Output</h3>

<a href="..\gnssdriver\ns-gnssdriver-gnss_event.md">GNSS_EVENT</a>


The <b>EventType</b> element must be set to <b>GNSS_Event_FixAvailable</b>.

The data associated with this event is of type <a href="..\gnssdriver\ns-gnssdriver-gnss_fixdata.md">GNSS_FIXDATA</a>.

<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter issues one or more get fix request after starting a fix session. This call creates a pending I/O against which the GNSS driver can return fix data when it is available from the underlying GNSS engine or cache value.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
Whenever a fix data is ready, the driver fills the buffer and completes the I/O. The driver must ensure that the data is returned for the specified fix session ID.

Whenever fix data is ready, the driver must fill the buffer and complete the I/O request. It is the driver’s responsibility to ensure that the data is returned for the specified fix session ID. Additionally, when a fix session is stopped by the GNSS adapter issuing an <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_stop_fixsession.md">IOCTL_GNSS_STOP_FIXSESSION</a>, the driver must cancel all pending get fix requests for the given fix session ID.




## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_GET_FIXDATA control code%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

