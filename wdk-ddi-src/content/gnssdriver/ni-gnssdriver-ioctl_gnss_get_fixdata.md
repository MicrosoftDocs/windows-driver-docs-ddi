---
UID: NI:gnssdriver.IOCTL_GNSS_GET_FIXDATA
title: IOCTL_GNSS_GET_FIXDATA (gnssdriver.h)
description: The IOCTL_GNSS_GET_FIXDATA control code is used by the GNSS adapter to register to receive the next fix data from an active fix session.
old-location: gnss\ioctl_gnss_get_fixdata.htm
tech.root: gnss
ms.assetid: 037B5AD9-39C2-4F50-8E63-0736EA37FEF9
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_GET_FIXDATA, IOCTL_GNSS_GET_FIXDATA control, IOCTL_GNSS_GET_FIXDATA control code [Sensor Devices], gnss.ioctl_gnss_get_fixdata, gnssdriver/IOCTL_GNSS_GET_FIXDATA
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
- IOCTL_GNSS_GET_FIXDATA
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_GET_FIXDATA IOCTL


## -description


The <b>IOCTL_GNSS_GET_FIXDATA</b> 
   control code is used by the GNSS adapter to register to receive the next fix data from an active fix session. This IOCTL provides the GNSS driver with a pending I/O request, the asynchronous resolution of which notifies the adapter that data is being provided through the overlapped structures <b>GnssEvent</b> member as a data buffer. The GnssEvent member is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gnssdriver/ns-gnssdriver-gnss_event">GNSS_EVENT</a> structure.



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








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="Input"></a><a id="input"></a><a id="INPUT"></a>Input</h3>
<b>FixSessionID</b>: Session ID for an active fix.

<h3><a id="Output"></a><a id="output"></a><a id="OUTPUT"></a>Output</h3>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gnssdriver/ns-gnssdriver-gnss_event">GNSS_EVENT</a>


The <b>EventType</b> element must be set to <b>GNSS_Event_FixAvailable</b>.

The data associated with this event is of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gnssdriver/ns-gnssdriver-gnss_fixdata">GNSS_FIXDATA</a>.

<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter issues one or more get fix request after starting a fix session. This call creates a pending I/O against which the GNSS driver can return fix data when it is available from the underlying GNSS engine or cache value.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
Whenever a fix data is ready, the driver fills the buffer and completes the I/O. The driver must ensure that the data is returned for the specified fix session ID.

Whenever fix data is ready, the driver must fill the buffer and complete the I/O request. It is the driver’s responsibility to ensure that the data is returned for the specified fix session ID. Additionally, when a fix session is stopped by the GNSS adapter issuing an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gnssdriver/ni-gnssdriver-ioctl_gnss_stop_fixsession">IOCTL_GNSS_STOP_FIXSESSION</a>, the driver must cancel all pending get fix requests for the given fix session ID.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

