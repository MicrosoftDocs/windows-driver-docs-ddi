---
UID: NS:avcstrm._AVCSTRM_OPEN_STRUCT
title: "_AVCSTRM_OPEN_STRUCT"
author: windows-driver-content
description: The AVCSTRM_OPEN_STRUCT structure describes a data stream to be opened.
old-location: stream\avcstrm_open_struct.htm
old-project: stream
ms.assetid: c16a2f3c-a5be-4132-920a-b81f67c5ea02
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avcsref_6ed25af3-808f-4b20-88c8-e7d2cca25494.xml, PAVCSTRM_OPEN_STRUCT structure pointer [Streaming Media Devices], _AVCSTRM_OPEN_STRUCT, AVCSTRM_OPEN_STRUCT structure [Streaming Media Devices], *PAVCSTRM_OPEN_STRUCT, avcstrm/PAVCSTRM_OPEN_STRUCT, avcstrm/AVCSTRM_OPEN_STRUCT, PAVCSTRM_OPEN_STRUCT, AVCSTRM_OPEN_STRUCT, stream.avcstrm_open_struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	avcstrm.h
apiname:
-	AVCSTRM_OPEN_STRUCT
product: Windows
targetos: Windows
req.typenames: "*PAVCSTRM_OPEN_STRUCT, AVCSTRM_OPEN_STRUCT"
---

# _AVCSTRM_OPEN_STRUCT structure


## -description


The AVCSTRM_OPEN_STRUCT structure describes a data stream to be opened.


## -syntax


````
typedef struct _AVCSTRM_OPEN_STRUCT {
  KSPIN_DATAFLOW       DataFlow;
  PAVCSTRM_FORMAT_INFO AVCFormatInfo;
  PVOID                AVCStreamContext;
  HANDLE               hPlugLocal;
} AVCSTRM_OPEN_STRUCT, *PAVCSTRM_OPEN_STRUCT;
````


## -struct-fields




#### - DataFlow

Specifies the direction of the data-flow.


#### - AVCFormatInfo

Pointer to a description of the subunit stream format.


#### - AVCStreamContext

Pointer to a stream context (handle) that is passed to subsequent <i>avcstrm.sys</i> operations. Its content should not be used or altered.


#### - hPlugLocal

Specifies a local plug created by an AV/C subunit, which is used to connect to the target device.


## -remarks


The <b>AVCSTRM_OPEN</b> function code uses this structure to describe the open operation. If the operation is successful, a stream context (handle) is returned to the caller in the <b>AVCStrmContext </b>member of this structure, <i>not</i> the <b>AVCStrmContext</b> member in the AVC_STREAM_REQUEST_BLOCK structure.

This value can then be used in subsequent <i>avcstrm.sys</i> operations by placing it in the <b>AVCStrmContext</b> member of the AVC_STREAM_REQUEST_BLOCK structure.



## -see-also

<a href="..\avcstrm\ns-avcstrm-_avcstrm_format_info.md">AVCSTRM_FORMAT_INFO</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554125">AVCSTRM_OPEN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVCSTRM_OPEN_STRUCT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

