---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES
title: IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES
author: windows-driver-content
description: A silo driver sends this IOCTL to the storage device stack to query for storage device properties. The Enhanced Storage Class Driver (EHSTOR) will handle the request and return the available properties.
old-location: storage\ioctl_ehstor_device_query_properties.htm
old-project: storage
ms.assetid: 2F9B880F-7F3A-4B2B-816E-AD85ADFB280B
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PDO_TYPE, PDO_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES
req.alt-loc: EhStorIoctl.h
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
req.typenames: PDO_TYPE
---

# IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES IOCTL



## -description
A silo driver sends this IOCTL to the storage device stack to query for storage device properties. The   Enhanced Storage Class Driver (EHSTOR) will handle the request and return the available properties.



## -syntax

````
typedef struct _EHSTOR_DEVICE_PROPERTIES
{
    ULONG  StructSize;
    ULONG  BytesPerSector;
} EHSTOR_DEVICE_PROPERTIES;
````


## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an  <b>EHSTOR_DEVICE_PROPERTIES</b>  structure. <b>EHSTOR_DEVICE_PROPERTIES</b> is declared in <i>ehstorioctl.h</i> as the following.



The size of the structure. This is set to <b>sizeof</b>(EHSTOR_DEVICE_PROPERTIES).

The size, in bytes, of a sector on the underlying storage device.


### -output-buffer-length
an  <b>EHSTOR_DEVICE_PROPERTIES</b>  structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
STATUS_SUCCESS is returned in the <b>Status</b> field if device properties are returned in the system buffer. Otherwise, another appropriate status code  is returned.


## -remarks
Currently, bytes per sector is the only property available in <b>EHSTOR_DEVICE_PROPERTIES</b>.


## -see-also
<dl>
<dt>
<a href="..\ehstorioctl\ns-ehstorioctl-tagact_authz_state.md">SILO_DRIVER_CAPABILITES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

