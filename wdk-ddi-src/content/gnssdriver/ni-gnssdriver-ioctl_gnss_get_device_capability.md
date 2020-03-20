---
UID: NI:gnssdriver.IOCTL_GNSS_GET_DEVICE_CAPABILITY
title: IOCTL_GNSS_GET_DEVICE_CAPABILITY (gnssdriver.h)
description: The IOCTL_GNSS_GET_DEVICE_CAPABILITY control code is used by the GNSS adapter to get the GNSS driver and device capabilities.
old-location: gnss\ioctl_gnss_get_device_capability.htm
tech.root: gnss
ms.assetid: 28673D2A-5DD6-42CD-BD91-5C30B905ECF0
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_GET_DEVICE_CAPABILITY IOCTL"]
ms.keywords: IOCTL_GNSS_GET_DEVICE_CAPABILITY, IOCTL_GNSS_GET_DEVICE_CAPABILITY control, IOCTL_GNSS_GET_DEVICE_CAPABILITY control code [Sensor Devices], gnss.ioctl_gnss_get_device_capability, gnssdriver/IOCTL_GNSS_GET_DEVICE_CAPABILITY
f1_keywords:
 - "gnssdriver/IOCTL_GNSS_GET_DEVICE_CAPABILITY"
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
- IOCTL_GNSS_GET_DEVICE_CAPABILITY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_GET_DEVICE_CAPABILITY IOCTL


## -description


The IOCTL_GNSS_GET_DEVICE_CAPABILITY control code is used by the GNSS adapter to get the GNSS driver and device capabilities. The GNSS driver also specifies various support requirements from the HLOS components. This information is needed by the GNSS driver as well as the location service for deferring location-specific functionality to the GNSS device.


## -ioctlparameters




### -input-buffer

Set to NULL.


### -input-buffer-length

Set to 0.


### -output-buffer

Pointer to a [GNSS_DEVICE_CAPABILITY](https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_device_capability) structure.


### -output-buffer-length

Set to sizeof(GNSS_DEVICE_CAPABILITY).


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
On completion, the GNSS adapter stores the capability information in its state variables and communicates the same to other location components. Depending on the specific device capabilities and/or support requirements, the GNSS adapter can also load/unload other components to provide the needed support.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
Driver fills the output buffer and completes the I/O.

This should be called when the GNSS adapter is initializing the GNSS driver.

Even if the driver supports a specific functionality or needs a specific functionality support from the HLOS, it is not guaranteed that the HLOS will leverage a specific driver capability, or will provided the needed level of support to the driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

