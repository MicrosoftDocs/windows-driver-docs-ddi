---
UID: NI:d4drvif.IOCTL_DOT4_CREATE_SOCKET
title: IOCTL_DOT4_CREATE_SOCKET
author: windows-driver-content
description: This topic describes IOCTL_DOT4_CREATE_SOCKET.
old-location: print\ioctl_ioctl_dot4_create_socket.htm
old-project: print
ms.assetid: CF5BF5D1-FF78-4461-AC0D-A7A7529FB59E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_DOT4_CREATE_SOCKET, IOCTL_DOT4_CREATE_SOCKET control code [Print Devices], d4drvif/IOCTL_DOT4_CREATE_SOCKET, print.ioctl_ioctl_dot4_create_socket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: d4drvif.h
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
-	D4drvif.h
api_name:
-	IOCTL_DOT4_CREATE_SOCKET
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IOCTL_DOT4_CREATE_SOCKET IOCTL


## -description


This topic describes <b>IOCTL_DOT4_CREATE_SOCKET</b>.


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



 

 


