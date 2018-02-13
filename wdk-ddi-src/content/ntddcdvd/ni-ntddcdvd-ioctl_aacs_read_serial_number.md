---
UID: NI:ntddcdvd.IOCTL_AACS_READ_SERIAL_NUMBER
title: IOCTL_AACS_READ_SERIAL_NUMBER
author: windows-driver-content
description: Reads the Advanced Access Content System (AACS)-specific prerecorded media serial number.
old-location: storage\ioctl_aacs_read_serial_number.htm
old-project: storage
ms.assetid: 258224d7-adc1-4002-8c90-4487134dbfd7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_aacs_read_serial_number, IOCTL_AACS_READ_SERIAL_NUMBER control code [Storage Devices], IOCTL_AACS_READ_SERIAL_NUMBER, ntddcdvd/IOCTL_AACS_READ_SERIAL_NUMBER, k307_039c336e-5b51-4a22-83bc-1b28d5ba5a33.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddcdvd.h
apiname:
-	IOCTL_AACS_READ_SERIAL_NUMBER
product: Windows
targetos: Windows
req.typenames: "*PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT"
---

# IOCTL_AACS_READ_SERIAL_NUMBER IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


Reads the Advanced Access Content System (AACS)-specific prerecorded media serial number. 


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID). 


### -input-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a>.


### -output-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the value of type <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_serial_number.md">AACS_SERIAL_NUMBER</a> that specifies the volume ID.


### -output-buffer-length

Length of a <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_serial_number.md">AACS_SERIAL_NUMBER</a>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks



The IOCTL_AACS_READ_SERIAL_NUMBER request corresponds to the part of the AACS authentication protocol that is responsible for transferring the prerecorded media serial number. For a complete description of this protocol, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA). 

The AGID is automatically released after the IOCTL_AACS_READ_SERIAL_NUMBER request completes. 



