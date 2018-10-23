---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_DRIVER_REQUEST
title: IOCTL_GNSS_LISTEN_DRIVER_REQUEST
author: windows-driver-content
description: The IOCTL_GNSS_LISTEN_DRIVER_REQUEST control code is used by the GNSS driver to get data from the HLOS.
old-location: gnss\ioctl_gnss_listen_driver_request.htm
tech.root: gnss
ms.assetid: 204D6F80-A458-45F8-B25F-4F5D3C33EB75
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_LISTEN_DRIVER_REQUEST, IOCTL_GNSS_LISTEN_DRIVER_REQUEST control, IOCTL_GNSS_LISTEN_DRIVER_REQUEST control code [Sensor Devices], gnss.ioctl_gnss_listen_driver_request, gnssdriver/IOCTL_GNSS_LISTEN_DRIVER_REQUEST
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
-	IOCTL_GNSS_LISTEN_DRIVER_REQUEST
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_LISTEN_DRIVER_REQUEST IOCTL


## -description


The <b>IOCTL_GNSS_LISTEN_DRIVER_REQUEST</b> control code is used by the GNSS driver to get data from the HLOS.


## -ioctlparameters




### -input-buffer

Set to NULL.


### -input-buffer-length

Set to 0.


### -output-buffer

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925134">GNSS_EVENT</a> structure.

The <b>EventType</b> must be set to <b>GNSS_Event_DriverRequest</b> and the <b>DriverRequestedData</b> member filled in.


### -output-buffer-length

Set to sizeof(GNSS_EVENT).


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter keeps a pending request all the time.

When the driver completes the I/O call, the adapter issues another IOCTL to receive the next driver request.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
There will be a pending IOCTL all the time. Whenever there is a need to request data from HLOS the I/O operation should be completed. The GNSS driver should fill out the required data requested by filling the <a href="https://msdn.microsoft.com/library/windows/hardware/dn925126">GNSS_DRIVER_REQUEST_DATA</a> structure.

The driver should use this IOCTL to get data in only rare circumstances and not during normal operations. On possible use case would be to request SUPL configuration if somehow the configuration is lost.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

