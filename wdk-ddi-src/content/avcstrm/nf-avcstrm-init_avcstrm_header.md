---
UID: NF:avcstrm.INIT_AVCSTRM_HEADER
title: INIT_AVCSTRM_HEADER macro
author: windows-driver-content
description: The INIT_AVCSTRM_HEADER macro initializes the SizeOfThisBlock, Version and Function members of the AVC_STREAM_REQUEST_BLOCK structure.
old-location: stream\init_avcstrm_header.htm
tech.root: stream
ms.assetid: 744d6e49-9321-4cba-a4e7-48a4abb02319
ms.date: 4/23/2018
ms.keywords: INIT_AVCSTRM_HEADER, INIT_AVCSTRM_HEADER macro [Streaming Media Devices], avcsref_97f7d983-5637-4ac4-ad1c-53328adca831.xml, avcstrm/INIT_AVCSTRM_HEADER, stream.init_avcstrm_header
ms.topic: macro
req.header: avcstrm.h
req.include-header: Avcstrm.h
req.target-type: Desktop
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
-	INIT_AVCSTRM_HEADER
product:
- Windows
targetos: Windows
req.typenames: 
---

# INIT_AVCSTRM_HEADER macro


## -description


The <b>INIT_AVCSTRM_HEADER</b> macro initializes the <b>SizeOfThisBlock</b>, <b>Version</b> and <b>Function</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554194">AVC_STREAM_REQUEST_BLOCK</a> structure.


## -parameters




### -param AVCStrm [in]

Points to a caller-allocated AVC_STREAM_REQUEST_BLOCK structure.


### -param Request [in]

Indicates the type of the request (function code) from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554120">AVCSTRM_FUNCTION</a> enumeration. Each function code is documented under the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560778">IOCTL_AVCSTRM_CLASS</a> topic.


## -remarks



The macro is defined as follows:

<pre class="syntax" xml:space="preserve"><code>#define INIT_AVCSTRM_HEADER( AVCStrm, Request )             \
        (AVCStrm)-&gt;SizeOfThisBlock = sizeof(AVC_STREAM_REQUEST_BLOCK); \
        (AVCStrm)-&gt;Function = Request;                    \
        (AVCStrm)-&gt;Version  = CURRENT_AVCSTRM_DDI_VERSION;</code></pre>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554107">AVCSTRM_ABORT_STREAMING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554110">AVCSTRM_CLOSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554121">AVCSTRM_GET_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554124">AVCSTRM_GET_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554125">AVCSTRM_OPEN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554130">AVCSTRM_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554132">AVCSTRM_SET_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554134">AVCSTRM_SET_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554135">AVCSTRM_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554194">AVC_STREAM_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560778">IOCTL_AVCSTRM_CLASS</a>
 

 

