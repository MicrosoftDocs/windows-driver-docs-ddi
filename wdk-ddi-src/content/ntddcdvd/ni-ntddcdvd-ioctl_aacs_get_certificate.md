---
UID: NI:ntddcdvd.IOCTL_AACS_GET_CERTIFICATE
title: IOCTL_AACS_GET_CERTIFICATE (ntddcdvd.h)
description: Queries the logical unit for the device certificate.
old-location: storage\ioctl_aacs_get_certificate.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_AACS_GET_CERTIFICATE IOCTL"]
ms.keywords: IOCTL_AACS_GET_CERTIFICATE, IOCTL_AACS_GET_CERTIFICATE control, IOCTL_AACS_GET_CERTIFICATE control code [Storage Devices], k307_53c85a18-def4-48b8-bc19-12347714d191.xml, ntddcdvd/IOCTL_AACS_GET_CERTIFICATE, storage.ioctl_aacs_get_certificate
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_AACS_GET_CERTIFICATE
 - ntddcdvd/IOCTL_AACS_GET_CERTIFICATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdvd.h
api_name:
 - IOCTL_AACS_GET_CERTIFICATE
---

# IOCTL_AACS_GET_CERTIFICATE IOCTL


## -description

Queries the logical unit for the device certificate.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a value of type <a href="/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID). The AGID identifies the secure session.

### -input-buffer-length

Length of a <a href="/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a>.

### -output-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the drive certificate with a format of <a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_certificate">AACS_CERTIFICATE</a>.

### -output-buffer-length

Length of an <a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_certificate">AACS_CERTIFICATE</a>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.

## -remarks

The IOCTL_AACS_GET_CERTIFICATE request corresponds to the step of the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth) in which the drive provides its certificate and nonce to the host. For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).
