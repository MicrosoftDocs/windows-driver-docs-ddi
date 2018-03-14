---
UID: NI:ks.IOCTL_KS_READ_STREAM
title: IOCTL_KS_READ_STREAM
author: windows-driver-content
description: An application can use IOCTL_KS_READ_STREAM to read data from a pin. The application passes IOCTL_KS_READ_STREAM with the parameters described below to the KsSynchronousDeviceControl function.
old-location: stream\ioctl_ks_read_stream.htm
old-project: stream
ms.assetid: 92110e27-5f1a-4c4d-b999-d9deb546e6a6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_KS_READ_STREAM, IOCTL_KS_READ_STREAM control code [Streaming Media Devices], ks-ioctl_677f9dd3-bd4b-4c15-8ee1-67ede429c958.xml, ks/IOCTL_KS_READ_STREAM, stream.ioctl_ks_read_stream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ks.h
req.include-header: Ks.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	IOCTL_KS_READ_STREAM
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_READ_STREAM IOCTL


## -description


An application can use IOCTL_KS_READ_STREAM to read data from a pin. The application passes IOCTL_KS_READ_STREAM with the parameters described below to the <a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a> function.


## -ioctlparameters




### -input-buffer

The application places a pointer to an array of <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a> structures in the <b>InBuffer</b> parameter. Each describes a packet of data to be read. The headers can also contain the presentation time and duration.


### -input-buffer-length

The <b>InLength</b> parameter specifies the size, in bytes, of the input buffer contents.


### -output-buffer

Stream data is returned in the buffers pointed to by the stream headers.  Upon return, <b>BytesReturned</b> contains the number of bytes read.


### -output-buffer-length

<b>OutLength</b> specifies the size, in bytes, of the output buffer contents.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.


## -see-also

<a href="..\ks\nf-ks-ksprobestreamirp.md">KsProbeStreamIrp</a>



<a href="..\ks\ni-ks-ioctl_ks_write_stream.md">IOCTL_KS_WRITE_STREAM</a>



 

 


