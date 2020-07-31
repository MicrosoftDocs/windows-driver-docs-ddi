---
UID: NI:acpiioct.IOCTL_ACPI_RELEASE_GLOBAL_LOCK
title: IOCTL_ACPI_RELEASE_GLOBAL_LOCK (acpiioct.h)
description: The IOCTL_ACPI_RELEASE_GLOBAL_LOCK device control request is reserved for internal use only.
old-location: acpi\ioctl_acpi_release_global_lock.htm
tech.root: acpi
ms.assetid: dcc74af4-500b-4fea-ba2b-9d1ea3a05ef6
ms.date: 02/15/2018
keywords: ["IOCTL_ACPI_RELEASE_GLOBAL_LOCK IOCTL"]
ms.keywords: IOCTL_ACPI_RELEASE_GLOBAL_LOCK, IOCTL_ACPI_RELEASE_GLOBAL_LOCK control, IOCTL_ACPI_RELEASE_GLOBAL_LOCK control code [ACPI Devices], acpi-meth-eval-ref_0b38285c-f188-4984-b214-86f9c3677c8d.xml, acpi.ioctl_acpi_release_global_lock, acpiioct/IOCTL_ACPI_RELEASE_GLOBAL_LOCK
f1_keywords:
 - "acpiioct/IOCTL_ACPI_RELEASE_GLOBAL_LOCK"
 - "IOCTL_ACPI_RELEASE_GLOBAL_LOCK"
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later versions of Windows.
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
- Acpiioct.h
api_name:
- IOCTL_ACPI_RELEASE_GLOBAL_LOCK
targetos: Windows
req.typenames: 
---

# IOCTL_ACPI_RELEASE_GLOBAL_LOCK IOCTL


## -description


The IOCTL_ACPI_RELEASE_GLOBAL_LOCK device control request is reserved for internal use only.


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



