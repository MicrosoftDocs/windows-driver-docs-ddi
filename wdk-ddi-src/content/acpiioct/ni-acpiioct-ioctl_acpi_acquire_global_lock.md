---
UID: NI:acpiioct.IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK
title: IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK
author: windows-driver-content
description: The IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK device control request is reserved for internal use only.
old-location: acpi\ioctl_acpi_acquire_global_lock.htm
old-project: acpi
ms.assetid: 359bd4d4-2557-4755-8904-32162645cdc0
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: acpi.ioctl_acpi_acquire_global_lock, IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK control code [ACPI Devices], IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK, acpiioct/IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK, acpi-meth-eval-ref_e6fd9b97-db9e-4a08-88bb-e6e84f08359b.xml
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
-	IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK
product: Windows
targetos: Windows
req.typenames: "*PUNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS"
---

# IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The IOCTL_ACPI_ACQUIRE_GLOBAL_LOCK device control request is reserved for internal use only.


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


