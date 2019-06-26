---
UID: NI:ntddscsi.IOCTL_SCSI_MINIPORT_DIAGNOSTIC
title: IOCTL_SCSI_MINIPORT_DIAGNOSTIC (ntddscsi.h)
description: The IOCTL_SCSI_MINIPORT_DIAGNOSTIC control code is use to perform a diagnostic request to the Miniport.
old-location: storage\ioctl_scsi_miniport_diagnostic.htm
tech.root: storage
ms.assetid: 79E89E4A-3B06-40FA-BFA6-598331C0A330
ms.date: 03/29/2018
ms.keywords: IOCTL_SCSI_MINIPORT_DIAGNOSTIC, IOCTL_SCSI_MINIPORT_DIAGNOSTIC control, IOCTL_SCSI_MINIPORT_DIAGNOSTIC control code [Storage Devices], ntddscsi/IOCTL_SCSI_MINIPORT_DIAGNOSTIC, storage.ioctl_scsi_miniport_diagnostic
ms.topic: ioctl
req.header: ntddscsi.h
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
- ntddscsi.h
api_name:
- IOCTL_SCSI_MINIPORT_DIAGNOSTIC
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SCSI_MINIPORT_DIAGNOSTIC IOCTL


## -description


The <b>IOCTL_SCSI_MINIPORT_DIAGNOSTIC</b> 
   control code is use to perform a diagnostic request to the Miniport.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).




## -remarks



To perform this operation, call the <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> 
   function with the following parameters.


<pre class="syntax">BOOL 
   WINAPI 
   DeviceIoControl( (HANDLE)       hDevice,         // handle to device
                    (DWORD)        IOCTL_SCSI_MINIPORT_DIAGNOSTIC, // dwIoControlCode
                    (LPDWORD)      lpInBuffer,      // input buffer
                    (DWORD)        nInBufferSize,   // size of input buffer
                    (LPDWORD)      lpOutBuffer,     // output buffer
                    (DWORD)        nOutBufferSize,  // size of output buffer
                    (LPDWORD)      lpBytesReturned, // number of bytes returned
                    (LPOVERLAPPED) lpOverlapped );  // OVERLAPPED structure</pre>



Parameters






## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_storage_diagnostic_mp_request">STORAGE_DIAGNOSTIC_MP_REQUEST</a>
 

 

