---
UID: NS:ksproxy._KSSTREAM_SEGMENT
title: "_KSSTREAM_SEGMENT"
author: windows-driver-content
description: The KSSTREAM_SEGMENT structure contains information that describes an I/O operation occurring on a stream.
old-location: stream\ksstream_segment.htm
old-project: stream
ms.assetid: 433b1346-f0f1-46f7-a1d8-e6397b2f7f05
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksproxy_ce88ef52-d88e-4dc8-952d-53dce519518f.xml, PKSSTREAM_SEGMENT, ksproxy/KSSTREAM_SEGMENT, KSSTREAM_SEGMENT structure [Streaming Media Devices], ksproxy/PKSSTREAM_SEGMENT, stream.ksstream_segment, KSSTREAM_SEGMENT, *PKSSTREAM_SEGMENT, PKSSTREAM_SEGMENT structure pointer [Streaming Media Devices], _KSSTREAM_SEGMENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
-	ksproxy.h
apiname:
-	KSSTREAM_SEGMENT
product: Windows
targetos: Windows
req.typenames: "*PKSSTREAM_SEGMENT, KSSTREAM_SEGMENT"
---

# _KSSTREAM_SEGMENT structure


## -description


The KSSTREAM_SEGMENT structure contains information that describes an I/O operation occurring on a stream.


## -syntax


````
typedef struct _KSSTREAM_SEGMENT {
  IKsInterfaceHandler *KsInterfaceHandler;
  IKsDataTypeHandler  *KsDataTypeHandler;
  KSIOOPERATION       IoOperation;
  HANDLE              CompletionEvent;
} KSSTREAM_SEGMENT, *PKSSTREAM_SEGMENT;
````


## -struct-fields




### -field KsInterfaceHandler

Pointer to a <a href="..\ksproxy\nn-ksproxy-iksinterfacehandler.md">IKsInterfaceHandler</a> interface for the I/O operation.


### -field KsDataTypeHandler

Pointer to a <a href="..\ksproxy\nn-ksproxy-iksdatatypehandler.md">IKsDataTypeHandler</a> interface for the I/O operation.


### -field IoOperation

Value that specifies the type of I/O operation. This value can be one of the following values from the KSIOOPERATION enumerated type:
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>KsIoOperation_Write</b>

</td>
<td>
Write data to stream.

</td>
</tr>
<tr>
<td>
<b>KsIoOperation_Read</b>

</td>
<td>
Read data from stream.

</td>
</tr>
</table> 


### -field CompletionEvent

Handle to an event that is used to signal that the I/O operation completed.


## -see-also

<a href="..\ksproxy\nn-ksproxy-iksdatatypehandler.md">IKsDataTypeHandler</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559869">IKsInterfaceHandler::KsProcessMediaSamples</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559862">IKsInterfaceHandler::KsCompleteIo</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560713">IKsPin::KsMediaSamplesCompleted</a>

<a href="..\ksproxy\nn-ksproxy-iksinterfacehandler.md">IKsInterfaceHandler</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSSTREAM_SEGMENT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

