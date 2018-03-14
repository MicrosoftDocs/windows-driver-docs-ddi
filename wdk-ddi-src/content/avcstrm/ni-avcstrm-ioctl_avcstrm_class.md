---
UID: NI:avcstrm.IOCTL_AVCSTRM_CLASS
title: IOCTL_AVCSTRM_CLASS
author: windows-driver-content
description: An AV/C subunit driver uses the IRP_MJ_INTERNAL_DEVICE_CONTROL IRP, with the IoControlCode member set to IOCTL_AVCSTRM_CLASS, to communicate with avcstrm.sys.
old-location: stream\ioctl_avcstrm_class.htm
old-project: stream
ms.assetid: 50a5cbe1-acae-461f-892b-c1a3b5b218b3
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_AVCSTRM_CLASS, IOCTL_AVCSTRM_CLASS control code [Streaming Media Devices], avcsref_0e06e31a-7520-4162-8441-210cc367f65f.xml, avcstrm/IOCTL_AVCSTRM_CLASS, stream.ioctl_avcstrm_class
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
-	avcstrm.h
api_name:
-	IOCTL_AVCSTRM_CLASS
product: Windows
targetos: Windows
req.typenames: AVCSTRM_FUNCTION
---

# IOCTL_AVCSTRM_CLASS IOCTL


## -description



An AV/C subunit driver uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> IRP, with the <b>IoControlCode</b> member set to IOCTL_AVCSTRM_CLASS, to communicate with <i>avcstrm.sys</i>. The driver has access to all operations provided by the AV/C Streaming filter driver (<i>avcstrm.sys</i>) through this request.

For more information about IRPs and IOCTLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546847">Handling IRPs</a>.




## -ioctlparameters




### -input-buffer

On input, <b>Irp-&gt;Parameters-&gt;Others.Arguments1</b> points to an <a href="..\avcstrm\ns-avcstrm-_avc_stream_request_block.md">AVC_STREAM_REQUEST_BLOCK</a> structure. The <b>Function</b> member of the AVC_STREAM_REQUEST_BLOCK specifies the type of request. Do not set this member directly. Use the <a href="..\avcstrm\nf-avcstrm-init_avcstrm_header.md">INIT_AVCSTRM_HEADER</a> macro to initialize this member (as well as additional members of the AVC_STREAM_REQUEST_BLOCK structure). The <b>CommandData</b> member of the AVC_STREAM_REQUEST_BLOCK is a union that specifies the request-type-specific parameters of the request. The parameters and their meaning are documented with each request (function code). The <a href="..\avcstrm\ne-avcstrm-_avcstrm_function.md">AVCSTRM_FUNCTION</a> enumeration provides a list of function codes supported by <i>avcstrm.sys</i>.


### -input-buffer-length

Length of an <a href="..\avcstrm\ns-avcstrm-_avc_stream_request_block.md">AVC_STREAM_REQUEST_BLOCK</a> structure.


### -output-buffer

On output, <b>Irp-&gt;Parameters-&gt;Others.Arguments1</b> points to the <a href="..\avcstrm\ns-avcstrm-_avc_stream_request_block.md">AVC_STREAM_REQUEST_BLOCK</a> structure passed as input. As part of completing the request, the bus driver fills in certain members of the <b>CommandData</b> union of the AVC_STREAM_REQUEST_BLOCK structure with information for the driver.


### -output-buffer-length

Length of an <a href="..\avcstrm\ns-avcstrm-_avc_stream_request_block.md">AVC_STREAM_REQUEST_BLOCK</a> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The information the AV/C Streaming driver returns in the I/O Status Block is documented with each request.


## -remarks



Must be called at IRQL = PASSIVE_LEVEL.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554110">AVCSTRM_CLOSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554135">AVCSTRM_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554130">AVCSTRM_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554124">AVCSTRM_GET_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554107">AVCSTRM_ABORT_STREAMING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554132">AVCSTRM_SET_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554125">AVCSTRM_OPEN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554134">AVCSTRM_SET_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554121">AVCSTRM_GET_PROPERTY</a>



 

 


