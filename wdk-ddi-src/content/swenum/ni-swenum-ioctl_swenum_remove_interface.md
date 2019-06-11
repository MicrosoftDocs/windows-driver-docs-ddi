---
UID: NI:swenum.IOCTL_SWENUM_REMOVE_INTERFACE
title: IOCTL_SWENUM_REMOVE_INTERFACE (swenum.h)
description: 
old-location: stream\ioctl_swenum_remove_interface.htm
tech.root: stream
ms.assetid: 89E7498F-8568-4A24-8731-E84AC8D1CE94
ms.date: 04/23/2018
ms.keywords: IOCTL_SWENUM_REMOVE_INTERFACE, IOCTL_SWENUM_REMOVE_INTERFACE control, IOCTL_SWENUM_REMOVE_INTERFACE control code [Streaming Media Devices], stream.ioctl_swenum_remove_interface, swenum/IOCTL_SWENUM_REMOVE_INTERFACE
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- swenum.h
api_name:
- IOCTL_SWENUM_REMOVE_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SWENUM_REMOVE_INTERFACE IOCTL


## -description





## -ioctlparameters




### -input-buffer




### -input-buffer-length




### -output-buffer




### -output-buffer-length




### -in-out-buffer




### -inout-buffer-length




### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

