---
UID: NI:acpiioct.IOCTL_ACPI_RELEASE_GLOBAL_LOCK
title: IOCTL_ACPI_RELEASE_GLOBAL_LOCK
author: windows-driver-content
description: The IOCTL_ACPI_RELEASE_GLOBAL_LOCK device control request is reserved for internal use only.
old-location: acpi\ioctl_acpi_release_global_lock.htm
old-project: acpi
ms.assetid: dcc74af4-500b-4fea-ba2b-9d1ea3a05ef6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: acpi.ioctl_acpi_release_global_lock, IOCTL_ACPI_RELEASE_GLOBAL_LOCK control code [ACPI Devices], IOCTL_ACPI_RELEASE_GLOBAL_LOCK, acpiioct/IOCTL_ACPI_RELEASE_GLOBAL_LOCK, acpi-meth-eval-ref_0b38285c-f188-4984-b214-86f9c3677c8d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Acpiioct.h
apiname:
-	IOCTL_ACPI_RELEASE_GLOBAL_LOCK
product: Windows
targetos: Windows
req.typenames: "*PUNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS"
---

# IOCTL_ACPI_RELEASE_GLOBAL_LOCK IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The IOCTL_ACPI_RELEASE_GLOBAL_LOCK device control request is reserved for internal use only.


## -ioctlparameters




### -input-buffer



<text></text>




### -input-buffer-length



<text></text>




### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [XREF-LINK:NTSTATUS Values].



