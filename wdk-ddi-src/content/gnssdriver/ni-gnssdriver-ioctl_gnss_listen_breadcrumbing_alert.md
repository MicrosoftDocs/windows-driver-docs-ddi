---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
title: IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
author: windows-driver-content
description: The IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control code is used to request alert information from GNSS_BREADCRUMBING_ALERT_DATA when the breadcrumbing buffer has reached a level at which OS read operations should be performed.
old-location: sensors\ioctl_gnss_listen_breadcrumbing_alert_.htm
old-project: sensors
ms.assetid: 14D396B1-5F55-4902-8986-BD4CC5B2ACC4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_SUPL_CERT_ACTION, GNSS_SUPL_CERT_ACTION
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
req.alt-api: IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
req.alt-loc: gnssdriver.h
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
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT IOCTL



## -description
The <b>IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT </b> 
   control code is used to request alert information  from <a href="..\gnssdriver\ns-gnssdriver-gnss_breadcrumbing_alert_data.md">GNSS_BREADCRUMBING_ALERT_DATA</a> when the breadcrumbing buffer has reached a level at which OS read
operations should be performed.



## -syntax

````
#define IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT \
    CTL_CODE( FILE_DEVICE_UNKNOWN, 0x072, METHOD_BUFFERED, FILE_ANY_ACCESS )
````


## -ioctlparameters

### -input-buffer
Pointer to the input buffer.


### -input-buffer-length
Size of the input buffer.


### -output-buffer
Pointer to the output buffer.


### -output-buffer-length
Size of the output buffer.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks
<b>IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT</b> is defined as follows in the gnssdriver.h header file:


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

