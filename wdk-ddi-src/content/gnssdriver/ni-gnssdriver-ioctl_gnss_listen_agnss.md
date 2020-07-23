---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_AGNSS
title: IOCTL_GNSS_LISTEN_AGNSS (gnssdriver.h)
description: The IOCTL_GNSS_LISTEN_AGNSS control code is used by the GNSS adapter to start listening for AGNSS requests issued by the GNSS driver.
old-location: gnss\ioctl_gnss_listen_agnss.htm
tech.root: gnss
ms.assetid: B065CDE1-BB6D-4209-881B-50743A38EDBE
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_LISTEN_AGNSS IOCTL"]
ms.keywords: IOCTL_GNSS_LISTEN_AGNSS, IOCTL_GNSS_LISTEN_AGNSS control, IOCTL_GNSS_LISTEN_AGNSS control code [Sensor Devices], gnss.ioctl_gnss_listen_agnss, gnssdriver/IOCTL_GNSS_LISTEN_AGNSS
f1_keywords:
 - "gnssdriver/IOCTL_GNSS_LISTEN_AGNSS"
 - "IOCTL_GNSS_LISTEN_AGNSS"
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
- IOCTL_GNSS_LISTEN_AGNSS
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_LISTEN_AGNSS IOCTL


## -description


The <b>IOCTL_GNSS_LISTEN_AGNSS</b> control code is used by the GNSS adapter to start listening for AGNSS requests issued by the GNSS driver. This IOCTL effectively provides the GNSS driver with a pending I/O request, the asynchronous resolution of which notifies the adapter, through the overlapped structures GnssEvent member, that the driver requires an AGNSS injection. The GnssEvent member is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_event">GNSS_EVENT</a> structure. The GNSS adapter ensures that this request is always pending and will issue a new request as soon as the pending one is resolved. When the I/O request is resolved the GNSS adapter will issue a corresponding <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ni-gnssdriver-ioctl_gnss_inject_agnss">IOCTL_GNSS_INJECT_AGNSS</a> with the appropriate injection data.


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








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="Output"></a><a id="output"></a><a id="OUTPUT"></a>Output</h3>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_event">GNSS_EVENT</a>


The EventType must be set to <b>GNSS_Event_RequireAGNSS</b> and the <b>AGNSSRequest</b> member filled in.

<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter ensures that this request is always pending, so that the driver can indicate that it requires AGNSS injection.

When the driver completes the I/O call, the adapter issues another IOCTL to continue waiting for further AGNSS requests.

Depending on the <b>AGNSSRequest.RequestType</b> element, the driver issues <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ni-gnssdriver-ioctl_gnss_inject_agnss">IOCTL_GNSS_INJECT_AGNSS</a> with the appropriate injection data.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
Whenever the GNSS driver requires assistance data, it completes the I/O operation to seek injection data from the adapter





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

