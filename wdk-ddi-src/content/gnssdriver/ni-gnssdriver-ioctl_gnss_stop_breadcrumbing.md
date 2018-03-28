---
UID: NI:gnssdriver.IOCTL_GNSS_STOP_BREADCRUMBING
title: IOCTL_GNSS_STOP_BREADCRUMBING
author: windows-driver-content
description: The IOCTL_GNSS_STOP_BREADCRUMBING control code is used to stop breadcrumbing.
old-location: gnss\ioctl_gnss_stop_breadcrumbing.htm
old-project: gnss
ms.assetid: FAA8B6B0-A95C-4E12-BB0C-585E676F602F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_GNSS_STOP_BREADCRUMBING, IOCTL_GNSS_STOP_BREADCRUMBING control code [Sensor Devices], gnss.ioctl_gnss_stop_breadcrumbing, gnssdriver/IOCTL_GNSS_STOP_BREADCRUMBING
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	IOCTL_GNSS_STOP_BREADCRUMBING
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_STOP_BREADCRUMBING IOCTL


## -description


The <b>IOCTL_GNSS_STOP_BREADCRUMBING</b> control code is used to stop breadcrumbing.


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

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also

<<<<<<< HEAD
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>
=======
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>
>>>>>>> 7b6bd3b88106eb7b25c8489b98269eb870735b73



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<<<<<<< HEAD
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>
=======
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>
>>>>>>> 7b6bd3b88106eb7b25c8489b98269eb870735b73



 

 

