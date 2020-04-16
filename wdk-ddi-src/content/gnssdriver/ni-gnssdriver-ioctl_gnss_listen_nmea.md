---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_NMEA
title: IOCTL_GNSS_LISTEN_NMEA (gnssdriver.h)
description: The IOCTL_GNSS_LISTEN_NMEA control code is used to start listening for NMEA events from the driver.
old-location: gnss\ioctl_gnss_listen_nmea.htm
tech.root: gnss
ms.assetid: 975F5FB4-503D-44E7-8D4C-2AEFE72B672B
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_LISTEN_NMEA IOCTL"]
ms.keywords: IOCTL_GNSS_LISTEN_NMEA, IOCTL_GNSS_LISTEN_NMEA control, IOCTL_GNSS_LISTEN_NMEA control code [Sensor Devices], gnss.ioctl_gnss_listen_nmea, gnssdriver/IOCTL_GNSS_LISTEN_NMEA
f1_keywords:
 - "gnssdriver/IOCTL_GNSS_LISTEN_NMEA"
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
- IOCTL_GNSS_LISTEN_NMEA
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_LISTEN_NMEA IOCTL


## -description


The <b>IOCTL_GNSS_LISTEN_NMEA</b> control code is used to start listening for NMEA events from the driver.


## -ioctlparameters




### -input-buffer

Set to NULL.


### -input-buffer-length

Set to 0.




### -output-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_event">GNSS_EVENT</a> structure.




### -output-buffer-length

Set to sizeof(GNSS_EVENT).




### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



The <b>EventType</b> must be set to <b>GNSS_Event_NmeaData</b>.

<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter does not use this IOCTL.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The driver can complete this call when it has NMEA data to send to the calling client. This calling client will typically be a test tool created by the OEM.

The calling client that wishes to receive NMEA data needs to do the following tasks:

<ul>
<li>
Ensure that NMEA logging is active.

</li>
<li>
Ensures that this request is always pending, so that the driver can return NMEA data when available.

</li>
</ul>
When the driver completes the I/O call, the calling client will need to issue another IOCTL to continue waiting for further NMEA data.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

