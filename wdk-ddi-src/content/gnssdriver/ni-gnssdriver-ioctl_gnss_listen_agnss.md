---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_AGNSS
title: IOCTL_GNSS_LISTEN_AGNSS
author: windows-driver-content
description: The IOCTL_GNSS_LISTEN_AGNSS control code is used by the GNSS adapter to start listening for AGNSS requests issued by the GNSS driver.
old-location: sensors\ioctl_gnss_listen_agnss.htm
old-project: sensors
ms.assetid: B065CDE1-BB6D-4209-881B-50743A38EDBE
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: sensors.ioctl_gnss_listen_agnss, IOCTL_GNSS_LISTEN_AGNSS control code [Sensor Devices], IOCTL_GNSS_LISTEN_AGNSS, gnssdriver/IOCTL_GNSS_LISTEN_AGNSS
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
-	IOCTL_GNSS_LISTEN_AGNSS
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_LISTEN_AGNSS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_GNSS_LISTEN_AGNSS</b> control code is used by the GNSS adapter to start listening for AGNSS requests issued by the GNSS driver. This IOCTL effectively provides the GNSS driver with a pending I/O request, the asynchronous resolution of which notifies the adapter, through the overlapped structures GnssEvent member, that the driver requires an AGNSS injection. The GnssEvent member is a <a href="..\gnssdriver\ne-gnssdriver-gnss_event_type.md">GNSS_EVENT</a> structure. The GNSS adapter ensures that this request is always pending and will issue a new request as soon as the pending one is resolved. When the I/O request is resolved the GNSS adapter will issue a corresponding <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_inject_agnss.md">IOCTL_GNSS_INJECT_AGNSS</a> with the appropriate injection data.


## -ioctlparameters




### -input-buffer

Set to NULL.


### -input-buffer-length

Set to 0.


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



<h3><a id="Output"></a><a id="output"></a><a id="OUTPUT"></a>Output</h3>

<a href="..\gnssdriver\ns-gnssdriver-gnss_event.md">GNSS_EVENT</a>


The EventType must be set to <b>GNSS_Event_RequireAGNSS</b> and the <b>AGNSSRequest</b> member filled in.

<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter ensures that this request is always pending, so that the driver can indicate that it requires AGNSS injection.

When the driver completes the I/O call, the adapter issues another IOCTL to continue waiting for further AGNSS requests.

Depending on the <b>AGNSSRequest.RequestType</b> element, the driver issues <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_inject_agnss.md">IOCTL_GNSS_INJECT_AGNSS</a> with the appropriate injection data.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
Whenever the GNSS driver requires assistance data, it completes the I/O operation to seek injection data from the adapter





## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_LISTEN_AGNSS control code%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

