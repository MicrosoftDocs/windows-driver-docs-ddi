---
UID: NF:ksproxy.IKsControl.KsMethod
title: IKsControl::KsMethod method
author: windows-driver-content
description: The KsMethod method sends a method to a KS object, along with any other defined support operations available on a method set.
old-location: stream\ikscontrol_ksmethod.htm
old-project: stream
ms.assetid: 9f9121be-786d-4a1c-bb01-7bf3c1d3b6cf
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsMethod method [Streaming Media Devices], ksproxy/IKsControl::KsMethod, stream.ikscontrol_ksmethod, IKsControl, KsMethod, IKsControl interface [Streaming Media Devices], KsMethod method, IKsControl::KsMethod, KsMethod method [Streaming Media Devices], IKsControl interface, ksproxy_700d1bc3-f01e-4fff-9976-f64cdfd54f82.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: ksproxy.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsControl.KsMethod
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsControl::KsMethod method


## -description


The <b>KsMethod</b> method sends a method to a KS object, along with any other defined support operations available on a method set. 


## -syntax


````
HRESULT KsMethod(
  [in]      PKSMETHOD Method,
  [in]      ULONG     MethodLength,
  [in, out] LPVOID    MethodData,
  [in]      ULONG     DataLength,
  [in, out] ULONG     *BytesReturned
);
````


## -parameters




### -param Method [in]

Pointer to a <a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a> structure that describes a method and the request type of the method request. 


### -param MethodLength [in]

Size, in bytes, of the buffer at <i>Method</i>. 


### -param MethodData [in, out]

Pointer to a buffer that contains data and buffer space for a KSMETHOD_TYPE_SEND operation, or buffer space that receives data for all other operations. 


### -param DataLength [in]

Size, in bytes, of the buffer at <i>MethodData</i>. 


### -param BytesReturned [in, out]

Pointer to a variable that receives the size, in bytes, of the data that <b>KsMethod</b> stores in the buffer at <i>MethodData</i>. 


## -returns


Returns NOERROR if successful; otherwise, returns an error code.



## -remarks


This is a synchronous call. It will not complete until the method is completed from kernel-mode.

To determine the buffer size that is required for a specific method request, you can call this method with MethodData set to <b>NULL</b> and DataLength equal to zero. The method returns HRESULT_FROM_WIN32(ERROR_MORE_DATA and BytesReturned contains the size of the required buffer.



## -see-also

<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsControl::KsMethod method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

