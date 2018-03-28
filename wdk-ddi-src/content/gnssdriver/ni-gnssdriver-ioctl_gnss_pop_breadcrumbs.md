---
UID: NI:gnssdriver.IOCTL_GNSS_POP_BREADCRUMBS
title: IOCTL_GNSS_POP_BREADCRUMBS
author: windows-driver-content
description: The IOCTL_GNSS_POP_BREADCRUMBS control code is used to request a list of breadcrumbs contained in GNSS_BREADCRUMB_LIST.
old-location: gnss\ioctl_gnss_pop_breadcrumbs_.htm
old-project: gnss
ms.assetid: D5F7ACDC-25A0-49A4-95D4-C48B3E94CF69
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_GNSS_POP_BREADCRUMBS, IOCTL_GNSS_POP_BREADCRUMBS control code [Sensor Devices], gnss.ioctl_gnss_pop_breadcrumbs_, gnssdriver/IOCTL_GNSS_POP_BREADCRUMBS
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
-	IOCTL_GNSS_POP_BREADCRUMBS
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_POP_BREADCRUMBS IOCTL


## -description


The <b>IOCTL_GNSS_POP_BREADCRUMBS</b> control code is used to request a list of breadcrumbs contained in <a href="..\gnssdriver\ns-gnssdriver-gnss_breadcrumb_list.md">GNSS_BREADCRUMB_LIST</a>.


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



 

 

