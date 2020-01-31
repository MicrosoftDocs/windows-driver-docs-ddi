---
UID: NI:scsiscan.IOCTL_SCSISCAN_GET_INFO
title: IOCTL_SCSISCAN_GET_INFO (scsiscan.h)
description: The IOCTL_SCSISCAN_GET_INFO I/O control code returns device information.
old-location: image\ioctl_scsiscan_get_info.htm
tech.root: image
ms.assetid: 48045e29-5982-44e6-b9a7-3b000e5cf338
ms.date: 05/03/2018
ms.keywords: IOCTL_SCSISCAN_GET_INFO, IOCTL_SCSISCAN_GET_INFO control, IOCTL_SCSISCAN_GET_INFO control code [Imaging Devices], image.ioctl_scsiscan_get_info, scsiscan/IOCTL_SCSISCAN_GET_INFO, stifnc_5897897c-6c10-42cd-9301-d5b5f54675fd.xml
f1_keywords:
 - "scsiscan/IOCTL_SCSISCAN_GET_INFO"
req.header: scsiscan.h
req.include-header: Scsiscan.h
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
- scsiscan.h
api_name:
- IOCTL_SCSISCAN_GET_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SCSISCAN_GET_INFO IOCTL

## -description

The **IOCTL_SCSISCAN_GET_INFO** I/O control code returns device information.

## -ioctlparameters

### -input-buffer

Set to NULL.

### -input-buffer-length

Set to 0.

### -output-buffer

Pointer to a [SCSISCAN_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiscan/ns-scsiscan-_scsiscan_info) structure.

### -output-buffer-length

Size of output buffer.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) code.

## -remarks

When the DeviceloControl function is called with the **IOCTL_SCSISCAN_GET_INFO** I/O control code, the caller must specify the address of a SCSISCAN_INFO structure as the function's lpOutbuffer parameter. The kernel-mode driver fills in the structure.

## -see-also

[Creating IOCTL Requests in Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[WdfIoTargetSendInternalIoctlOthersSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously)

[WdfIoTargetSendInternalIoctlSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously)

[WdfIoTargetSendIoctlSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously)
