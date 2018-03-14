---
UID: NI:swenum.IOCTL_SWENUM_INSTALL_INTERFACE
title: IOCTL_SWENUM_INSTALL_INTERFACE
author: windows-driver-content
description: 
old-location: stream\ioctl_swenum_install_interface.htm
old-project: stream
ms.assetid: 23EC4771-44DF-4437-88E1-4039E0EB6F8F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_SWENUM_INSTALL_INTERFACE, IOCTL_SWENUM_INSTALL_INTERFACE control code [Streaming Media Devices], stream.ioctl_swenum_install_interface, swenum/IOCTL_SWENUM_INSTALL_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: swenum.h
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
-	swenum.h
api_name:
-	IOCTL_SWENUM_INSTALL_INTERFACE
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# IOCTL_SWENUM_INSTALL_INTERFACE IOCTL


## -description





## -ioctlparameters




### -input-buffer




### -input-buffer-length




### -output-buffer




### -output-buffer-length




### -in-out-buffer




### -inout-buffer-length




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



 

 


