---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES
title: IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES
author: windows-driver-content
description: A silo driver sends this IOCTL to the storage device stack to query for storage device properties. The Enhanced Storage Class Driver (EHSTOR) will handle the request and return the available properties.
old-location: storage\ioctl_ehstor_device_query_properties.htm
old-project: storage
ms.assetid: 2F9B880F-7F3A-4B2B-816E-AD85ADFB280B
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES, IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES control, IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES, storage.ioctl_ehstor_device_query_properties
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	EhStorIoctl.h
api_name:
-	IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES IOCTL


## -description


A silo driver sends this IOCTL to the storage device stack to query for storage device properties. The   Enhanced Storage Class Driver (EHSTOR) will handle the request and return the available properties.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an  <b>EHSTOR_DEVICE_PROPERTIES</b>  structure. <b>EHSTOR_DEVICE_PROPERTIES</b> is declared in <i>ehstorioctl.h</i> as the following.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _EHSTOR_DEVICE_PROPERTIES
{
    ULONG  StructSize;
    ULONG  BytesPerSector;
} EHSTOR_DEVICE_PROPERTIES;</pre>
</td>
</tr>
</table></span></div>



#### -BytesPerSector

The size, in bytes, of a sector on the underlying storage device.


#### -StructSize

The size of the structure. This is set to <b>sizeof</b>(EHSTOR_DEVICE_PROPERTIES).


### -output-buffer-length

an  <b>EHSTOR_DEVICE_PROPERTIES</b>  structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

STATUS_SUCCESS is returned in the <b>Status</b> field if device properties are returned in the system buffer. Otherwise, another appropriate status code  is returned.


## -remarks



Currently, bytes per sector is the only property available in <b>EHSTOR_DEVICE_PROPERTIES</b>.




## -see-also




<a href="https://msdn.microsoft.com/32bb774f-b1eb-4198-8e4c-febcac83153d">SILO_DRIVER_CAPABILITES</a>
 

 

