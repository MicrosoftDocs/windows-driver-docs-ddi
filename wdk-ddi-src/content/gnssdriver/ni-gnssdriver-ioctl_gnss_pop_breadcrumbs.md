---
UID: NI:gnssdriver.IOCTL_GNSS_POP_BREADCRUMBS
title: IOCTL_GNSS_POP_BREADCRUMBS (gnssdriver.h)
description: The IOCTL_GNSS_POP_BREADCRUMBS control code is used to request a list of breadcrumbs contained in GNSS_BREADCRUMB_LIST.
old-location: gnss\ioctl_gnss_pop_breadcrumbs_.htm
tech.root: gnss
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_POP_BREADCRUMBS IOCTL"]
ms.keywords: IOCTL_GNSS_POP_BREADCRUMBS, IOCTL_GNSS_POP_BREADCRUMBS control, IOCTL_GNSS_POP_BREADCRUMBS control code [Sensor Devices], gnss.ioctl_gnss_pop_breadcrumbs_, gnssdriver/IOCTL_GNSS_POP_BREADCRUMBS
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_GNSS_POP_BREADCRUMBS
 - gnssdriver/IOCTL_GNSS_POP_BREADCRUMBS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - IOCTL_GNSS_POP_BREADCRUMBS
---

# IOCTL_GNSS_POP_BREADCRUMBS IOCTL


## -description

The <b>IOCTL_GNSS_POP_BREADCRUMBS</b> control code is used to request a list of breadcrumbs contained in <a href="/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_breadcrumb_list">GNSS_BREADCRUMB_LIST</a>.

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

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
