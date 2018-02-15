---
UID: NI:ntddpar.IOCTL_PAR_QUERY_RAW_DEVICE_ID
title: IOCTL_PAR_QUERY_RAW_DEVICE_ID
author: windows-driver-content
description: The IOCTL_PAR_QUERY_RAW_DEVICE_ID request returns a raw device ID, which includes the following:\_a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the IEEE 1284 device ID; and a NULL terminator.
old-location: parports\ioctl_par_query_raw_device_id.htm
old-project: parports
ms.assetid: 3d7b99ea-eb53-4466-bd98-15c147c00d35
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: parports.ioctl_par_query_raw_device_id, IOCTL_PAR_QUERY_RAW_DEVICE_ID control code [Parallel Ports], IOCTL_PAR_QUERY_RAW_DEVICE_ID, ntddpar/IOCTL_PAR_QUERY_RAW_DEVICE_ID, cisspd_422dd85c-1d22-4968-9b4c-fd1ef03432e5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddpar.h
req.include-header: Ntddpar.h
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
-	ntddpar.h
apiname:
-	IOCTL_PAR_QUERY_RAW_DEVICE_ID
product: Windows
targetos: Windows
req.typenames: "*POFFLOAD_SECURITY_ASSOCIATION, OFFLOAD_SECURITY_ASSOCIATION"
---

# IOCTL_PAR_QUERY_RAW_DEVICE_ID IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The IOCTL_PAR_QUERY_RAW_DEVICE_ID request returns a raw device ID, which includes the following: a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the IEEE 1284 device ID; and a <b>NULL</b> terminator.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that the client allocates to output a raw device ID. The buffer contains the following contiguous sequence of information: a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the device ID; and a <b>NULL</b> terminator.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member specifies the size, in bytes, of the output buffer that can hold the following: a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the device ID; and a <b>NULL</b> terminator. An IEEE 1284 device ID can be up to 64 KB in size.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of the information returned in the output buffer. Otherwise, the <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to one of the following values:




#### -STATUS_BUFFER_TOO_SMALL

The output buffer that <b>AssociatedIrp.SystemBuffer</b> points to is less than the size, in bytes, of a two-byte prefix, the IEEE 1284 device ID, and a <b>NULL</b> terminator.


#### -STATUS_IO_DEVICE_ERROR

A device I/O error occurred.


## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id_size.md">IOCTL_PAR_QUERY_DEVICE_ID_SIZE</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id.md">IOCTL_PAR_QUERY_DEVICE_ID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_PAR_QUERY_RAW_DEVICE_ID control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

