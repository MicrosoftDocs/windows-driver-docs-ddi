---
UID: NI:gnssdriver.IOCTL_GNSS_SEND_PLATFORM_CAPABILITY
title: IOCTL_GNSS_SEND_PLATFORM_CAPABILITY (gnssdriver.h)
description: The IOCTL_GNSS_SEND_PLATFORM_CAPABILITY control code is used by the GNSS adapter to communicate the various location-specific platform capabilities.
old-location: gnss\ioctl_gnss_send_platform_capability.htm
tech.root: gnss
ms.assetid: EF979267-BDF3-4C42-B18E-C77E2584BC2D
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_SEND_PLATFORM_CAPABILITY IOCTL"]
ms.keywords: IOCTL_GNSS_SEND_PLATFORM_CAPABILITY, IOCTL_GNSS_SEND_PLATFORM_CAPABILITY control, IOCTL_GNSS_SEND_PLATFORM_CAPABILITY control code [Sensor Devices], gnss.ioctl_gnss_send_platform_capability, gnssdriver/IOCTL_GNSS_SEND_PLATFORM_CAPABILITY
f1_keywords:
 - "gnssdriver/IOCTL_GNSS_SEND_PLATFORM_CAPABILITY"
 - "IOCTL_GNSS_SEND_PLATFORM_CAPABILITY"
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
- IOCTL_GNSS_SEND_PLATFORM_CAPABILITY
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_SEND_PLATFORM_CAPABILITY IOCTL


## -description


The <b>IOCTL_GNSS_SEND_PLATFORM_CAPABILITY</b> control code is used by the GNSS adapter to communicate the various location-specific platform capabilities. The GNSS driver can use this data in various ways. For example, if the platform does not support injection of assistance data, the GNSS driver can use the mobile operation network to seek such information. The use of the individual capability information is optional and the driver can ignore the platform capability information for its operation.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_platform_capability">GNSS_PLATFORM_CAPABILITY</a> structure.




### -input-buffer-length

Set to sizeof(GNSS_PLATFORM_CAPABILITY).


### -output-buffer

Set to NULL.


### -output-buffer-length

Set to 0.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



The driver sets one of the following NTSTATUS values to indicate result.

<ul>
<li>
<b>STATUS_SUCCESS</b>, when the driver processes the capability information successfully.

</li>
<li>
<b>Failed</b>, when the driver does not process the capability information successfully.

</li>
<li>
<b>Ignored</b>, when the driver ignores the capability information.

</li>
</ul>
<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
This is a void fire-and-forget style call to the driver. The GNSS adapter does not do any special error handling even when the call fails.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The driver can record the capability information in state variables and pass on to the engine as needed. The I/O should be completed as soon as the configuration information is copied.

This should be called when the GNSS adapter is initializing the GNSS driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

