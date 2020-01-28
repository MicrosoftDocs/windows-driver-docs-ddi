---
UID: NF:avcstrm.INIT_AVCSTRM_HEADER
title: INIT_AVCSTRM_HEADER macro (avcstrm.h)
description: The INIT_AVCSTRM_HEADER macro initializes the SizeOfThisBlock, Version and Function members of the AVC_STREAM_REQUEST_BLOCK structure.
old-location: stream\init_avcstrm_header.htm
tech.root: stream
ms.assetid: 744d6e49-9321-4cba-a4e7-48a4abb02319
ms.date: 04/23/2018
ms.keywords: INIT_AVCSTRM_HEADER, INIT_AVCSTRM_HEADER macro [Streaming Media Devices], avcsref_97f7d983-5637-4ac4-ad1c-53328adca831.xml, avcstrm/INIT_AVCSTRM_HEADER, stream.init_avcstrm_header
f1_keywords:
 - "avcstrm/INIT_AVCSTRM_HEADER"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- avcstrm.h
api_name:
- INIT_AVCSTRM_HEADER
product:
- Windows
targetos: Windows
req.typenames: 
---

# INIT_AVCSTRM_HEADER macro

## -description

The **INIT_AVCSTRM_HEADER** macro initializes the **SizeOfThisBlock**, **Version** and **Function** members of the [AVC_STREAM_REQUEST_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/ns-avcstrm-_avc_stream_request_block) structure.

## -parameters

### -param AVCStrm [in]

Points to a caller-allocated AVC_STREAM_REQUEST_BLOCK structure.

### -param Request [in]

Indicates the type of the request (function code) from the [AVCSTRM_FUNCTION](https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/ne-avcstrm-_avcstrm_function) enumeration. Each function code is documented under the [IOCTL_AVCSTRM_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/ni-avcstrm-ioctl_avcstrm_class) topic.

## -remarks

The macro is defined as follows:

```cpp
#define INIT_AVCSTRM_HEADER( AVCStrm, Request ) \
    (AVCStrm)->;SizeOfThisBlock = sizeof(AVC_STREAM_REQUEST_BLOCK); \
    (AVCStrm)->;Function = Request;                    \
    (AVCStrm)->;Version  = CURRENT_AVCSTRM_DDI_VERSION;
```

## -see-also

[AVCSTRM_ABORT_STREAMING](https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-abort-streaming)

[AVCSTRM_CLOSE](https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-close)

[AVCSTRM_GET_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-get-property)

[AVCSTRM_GET_STATE](https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-get-state)

[AVCSTRM_OPEN](https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-open)

[AVCSTRM_READ](https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-read)

[AVCSTRM_SET_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-set-property)

[AVCSTRM_SET_STATE](https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-set-state)

[AVCSTRM_WRITE](https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-write)

[AVC_STREAM_REQUEST_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/ns-avcstrm-_avc_stream_request_block)

[IOCTL_AVCSTRM_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/ni-avcstrm-ioctl_avcstrm_class)
