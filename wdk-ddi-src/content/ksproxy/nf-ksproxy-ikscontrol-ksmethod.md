---
UID: NF:ksproxy.IKsControl.KsMethod
title: IKsControl::KsMethod (ksproxy.h)
description: The KsMethod method sends a method to a KS object, along with any other defined support operations available on a method set.
old-location: stream\ikscontrol_ksmethod.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsControl::KsMethod"]
ms.keywords: IKsControl interface [Streaming Media Devices],KsMethod method, IKsControl.KsMethod, IKsControl::KsMethod, KsMethod, KsMethod method [Streaming Media Devices], KsMethod method [Streaming Media Devices],IKsControl interface, ksproxy/IKsControl::KsMethod, ksproxy_700d1bc3-f01e-4fff-9976-f64cdfd54f82.xml, stream.ikscontrol_ksmethod
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: DesktopMobile
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsControl::KsMethod
 - ksproxy/IKsControl::KsMethod
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsControl.KsMethod
---

# IKsControl::KsMethod (ksproxy.h)


## -description

The <b>KsMethod</b> method sends a method to a KS object, along with any other defined support operations available on a method set.

## -parameters

### -param Method 

[in]
Pointer to a <a href="/previous-versions/ff563398(v=vs.85)">KSMETHOD</a> structure that describes a method and the request type of the method request.

### -param MethodLength 

[in]
Size, in bytes, of the buffer at <i>Method</i>.

### -param MethodData 

[in, out]
Pointer to a buffer that contains data and buffer space for a KSMETHOD_TYPE_SEND operation, or buffer space that receives data for all other operations.

### -param DataLength 

[in]
Size, in bytes, of the buffer at <i>MethodData</i>.

### -param BytesReturned 

[in, out]
Pointer to a variable that receives the size, in bytes, of the data that <b>KsMethod</b> stores in the buffer at <i>MethodData</i>.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

This is a synchronous call. It will not complete until the method is completed from kernel-mode.

To determine the buffer size that is required for a specific method request, you can call this method with MethodData set to <b>NULL</b> and DataLength equal to zero. The method returns HRESULT_FROM_WIN32(ERROR_MORE_DATA and BytesReturned contains the size of the required buffer.

## -see-also

<a href="/previous-versions/ff563398(v=vs.85)">KSMETHOD</a>
