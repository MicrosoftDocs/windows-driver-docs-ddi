---
UID: NC:avc.PFNAVCINTERSECTHANDLER
title: PFNAVCINTERSECTHANDLER
author: windows-driver-content
description: The AV/C intersect handler determines if the data ranges are compatible.
old-location: stream\av_c_intersect_handler.htm
old-project: stream
ms.assetid: 65ab5b68-9b76-497b-b560-9a4867d4d34e
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: stream.av_c_intersect_handler, PFNAVCINTERSECTHANDLER function pointer [Streaming Media Devices], PFNAVCINTERSECTHANDLER, avc/PFNAVCINTERSECTHANDLER, avcref_6aa55400-08b6-4a96-af38-23e69fed1621.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: avc.h
req.include-header: Avc.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	avc.h
apiname:
-	PFNAVCINTERSECTHANDLER
product: Windows
targetos: Windows
req.typenames: KBUGCHECK_DATA, *PKBUGCHECK_DATA
---

# PFNAVCINTERSECTHANDLER callback


## -description


The AV/C intersect handler determines if the data ranges are compatible. This is a user-defined function based on the following prototype:


## -prototype


````
typedef NTSTATUS ( *PFNAVCINTERSECTHANDLER)(
  _In_      PVOID        Context,
  _In_      ULONG        PinId,
  _In_      PKSDATARANGE CallerDataRange,
  _In_      PKSDATARANGE DescriptorDataRange,
  _In_      ULONG        DataBufferSize,
  _Out_opt_ PVOID        Data,
  _Out_     PULONG       ReportedDataSize
);
````


## -parameters




### -param Context [in]

An optional value expected by the intersect handler. This value is either provided by the subunit driver (if the subunit driver provides the intersect handler), or by the lower driver providing the intersect handler.


### -param PinId [in]

Specifies the offset (or ID) of the pin for which the intersection is being done.


### -param DataRange


### -param MatchingDataRange


### -param DataBufferSize [in]

The size of the buffer passed by the <b>Data</b> member. If this is nonzero, then the intersect handler should attempt to return the data format resulting from a matching pair of data ranges. If this is zero, then the intersect handler should provide the required buffer size in <b>ReportedDataSize</b>, and return STATUS_BUFFER_OVERFLOW.


### -param Data [out, optional]

An optional buffer to receive the data format resulting from a matching pair of data ranges. This member is ignored if <b>DataBufferSize </b>is zero.


### -param DataSize








#### - CallerDataRange [in]

The first of two data ranges being compared.


#### - DescriptorDataRange [in]

The second of two data ranges being compared.


#### - ReportedDataSize [out]

The actual size of the resulting data format. If <b>DataBufferSize</b> was zero, then this contains the required size of the buffer, but no format is returned.


## -returns



The intersect handler should return STATUS_SUCCESS if the data ranges are compatible, and there was enough buffer space to return the resulting format.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MATCH</b></dt>
</dl>
</td>
<td width="60%">
The data ranges are not compatible.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
There was an unexpected format size mismatch.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The intersect handler returns the required buffer size through the <b>ReportedDataSize</b> member.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The intersect handler was not provided with a buffer large enough to hold the resulting format. The intersect handler must be called again with the <b>DataBufferSize</b> set to zero to determine the required buffer size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
An internal buffer allocation failed.

</td>
</tr>
</table>
 




## -remarks



The AV/C intersect handler is user-defined, based on the function prototype above.

The handler is used in conjunction with the <b>AVC_FUNCTION_GET_PIN_DESCRIPTOR</b> function code. The purpose of the handler  is to match identical pin data formats and return them to the caller.




## -see-also

<a href="..\ks\nc-ks-pfnksintersecthandlerex.md">AVStrMiniIntersectHandlerEx</a>



<a href="..\avc\ns-avc-_avc_pin_descriptor.md">AVC_PIN_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554160">AVC_FUNCTION_GET_PIN_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/44281574-8258-47a3-857d-fd44bb949f17">DataRange Intersections in AVStream</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNAVCINTERSECTHANDLER function pointer%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

