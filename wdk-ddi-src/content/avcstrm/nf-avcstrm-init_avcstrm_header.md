---
UID: NF:avcstrm.INIT_AVCSTRM_HEADER
title: INIT_AVCSTRM_HEADER macro
author: windows-driver-content
description: The INIT_AVCSTRM_HEADER macro initializes the SizeOfThisBlock, Version and Function members of the AVC_STREAM_REQUEST_BLOCK structure.
old-location: stream\init_avcstrm_header.htm
old-project: stream
ms.assetid: 744d6e49-9321-4cba-a4e7-48a4abb02319
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: INIT_AVCSTRM_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: avcstrm.h
req.include-header: Avcstrm.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: INIT_AVCSTRM_HEADER
req.alt-loc: avcstrm.h
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
req.typenames: AVCSTRM_FUNCTION
---

# INIT_AVCSTRM_HEADER macro



## -description
The <b>INIT_AVCSTRM_HEADER</b> macro initializes the <b>SizeOfThisBlock</b>, <b>Version</b> and <b>Function</b> members of the <a href="..\avcstrm\ns-avcstrm-_avc_stream_request_block.md">AVC_STREAM_REQUEST_BLOCK</a> structure.



## -syntax

````
VOID INIT_AVCSTRM_HEADER(
  [in] PAVC_STREAM_REQUEST_BLOCK AVCStrm,
  [in] AVCSTRM_FUNCTION          Request
);
````


## -parameters

### -param AVCStrm [in]

Points to a caller-allocated AVC_STREAM_REQUEST_BLOCK structure.


### -param Request [in]

Indicates the type of the request (function code) from the <a href="..\avcstrm\ne-avcstrm-_avcstrm_function.md">AVCSTRM_FUNCTION</a> enumeration. Each function code is documented under the <a href="..\avcstrm\ni-avcstrm-ioctl_avcstrm_class.md">IOCTL_AVCSTRM_CLASS</a> topic.


## -remarks
The macro is defined as follows:


## -see-also
<dl>
<dt>
<a href="..\avcstrm\ns-avcstrm-_avc_stream_request_block.md">AVC_STREAM_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="..\avcstrm\ni-avcstrm-ioctl_avcstrm_class.md">IOCTL_AVCSTRM_CLASS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554130">AVCSTRM_READ</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554135">AVCSTRM_WRITE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554107">AVCSTRM_ABORT_STREAMING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554125">AVCSTRM_OPEN</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554110">AVCSTRM_CLOSE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554124">AVCSTRM_GET_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554134">AVCSTRM_SET_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554121">AVCSTRM_GET_PROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554132">AVCSTRM_SET_PROPERTY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20INIT_AVCSTRM_HEADER macro%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

