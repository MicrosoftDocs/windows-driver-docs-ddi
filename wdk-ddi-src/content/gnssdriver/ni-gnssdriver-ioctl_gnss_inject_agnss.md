---
UID: NI:gnssdriver.IOCTL_GNSS_INJECT_AGNSS
title: IOCTL_GNSS_INJECT_AGNSS (gnssdriver.h)
description: The IOCTL_GNSS_INJECT_AGNSS control code is used by the GNSS adapter to inject AGNSS data into the driver. This IOCTL is sent as a result of the driver previously responding to a pending IOCTL_GNSS_LISTEN_AGNSS request.
old-location: gnss\ioctl_gnss_inject_agnss.htm
tech.root: gnss
ms.assetid: 68EC4397-1983-4D02-BF6E-599DC987E7E9
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_INJECT_AGNSS IOCTL"]
ms.keywords: IOCTL_GNSS_INJECT_AGNSS, IOCTL_GNSS_INJECT_AGNSS control, IOCTL_GNSS_INJECT_AGNSS control code [Sensor Devices], gnss.ioctl_gnss_inject_agnss, gnssdriver/IOCTL_GNSS_INJECT_AGNSS
f1_keywords:
 - "gnssdriver/IOCTL_GNSS_INJECT_AGNSS"
 - "IOCTL_GNSS_INJECT_AGNSS"
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
- IOCTL_GNSS_INJECT_AGNSS
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_INJECT_AGNSS IOCTL


## -description


The <b>IOCTL_GNSS_INJECT_AGNSS</b> control code is used by the GNSS adapter to inject AGNSS data into the driver. This IOCTL is sent as a result of the driver previously responding to a pending <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ni-gnssdriver-ioctl_gnss_listen_agnss">IOCTL_GNSS_LISTEN_AGNSS</a> request. 


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_agnss_inject">GNSS_AGNSS_INJECT</a> structure.


### -input-buffer-length

Set to sizeof(GNSS_AGNSS_INJECT).


### -output-buffer

Set to <b>NULL</b>.


### -output-buffer-length

Set to 0.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="Input"></a><a id="input"></a><a id="INPUT"></a>Input</h3>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_agnss_inject">GNSS_AGNSS_INJECT</a>


Depending on the InjectionType element, the appropriate data element is filled.

<h3><a id="Output"></a><a id="output"></a><a id="OUTPUT"></a>Output</h3>
NTSTATUS with the following indications:

<ul>
<li>
Success: AGNSS data injection was accepted.

</li>
<li>
Failed: AGNSS data injection failed.

</li>
</ul>
<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
When the GNSS adapter fails to get time for injection, it sets the InjectionStatus element. The driver must check that this element indicates success, before actually using the element data.

In case of failure in gathering injection data, the adapter does not automatically retry. It is up to the driver to retry the same request sequent.

This is a fire-and-forget IOCTL. The GNSS adapter does not handle error even if the driver returns a failure indicating that the injection data was not used.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The GNSS driver completes the I/O request after consuming the injection data.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

