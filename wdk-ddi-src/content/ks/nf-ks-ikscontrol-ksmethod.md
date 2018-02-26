---
UID: NF:ks.IKsControl.KsMethod
title: IKsControl::KsMethod method
author: windows-driver-content
description: The IKsControl::KsMethod method sends a method to a KS object, together with any other defined support operations available on a method set.
old-location: stream\ikscontrol_ksmethod2.htm
old-project: stream
ms.assetid: 75100366-ba79-4ff2-b8e0-64c5c3f5f3b9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, C, I, IKsControl, IKsControl interface [Streaming Media Devices], KsMethod method, IKsControl::KsMethod, K, KsMethod method [Streaming Media Devices], KsMethod method [Streaming Media Devices], IKsControl interface, KsMethod,IKsControl.KsMethod, M, avintfc_6cf0dd96-36e2-4d0a-8bb8-f2f49ab9eb1f.xml, d, e, h, ks/IKsControl::KsMethod, l, n, o, r, s, stream.ikscontrol_ksmethod2, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ks.h
req.include-header: Ks.h
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
req.lib: ks.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ks.h
apiname:
-	IKsControl.KsMethod
product: Windows
targetos: Windows
req.typenames: 
---

# IKsControl::KsMethod method


## -description


The <b>IKsControl::KsMethod</b> method sends a method to a KS object, together with any other defined support operations available on a method set. 


## -syntax


````
NTSTATUS KsMethod(
  [in]      PKSMETHOD Method,
  [in]      ULONG     MethodLength,
  [in, out] PVOID     MethodData,
  [in]      ULONG     DataLength,
  [out]     ULONG     *BytesReturned
);
````


## -parameters




### -param Method [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a> structure that describes a method and the request type of the method request. 


### -param MethodLength [in]

Specifies size, in bytes, of the buffer at <i>Method</i>. 


### -param MethodData [in, out]

Pointer to a buffer that contains data and buffer space for a KSMETHOD_TYPE_SEND operation, or buffer space that receives data for all other operations. 


### -param DataLength [in]

Specifies size, in bytes, of the buffer at <i>MethodData</i>. 


### -param BytesReturned [out]

Pointer to a variable that receives the size, in bytes, of the data that <b>KsMethod</b> stores in the buffer at <i>MethodData</i>. 


## -returns



The <b>IKsControl::KsMethod</b> method returns the same value that would be returned if the method had been sent by IOCTL.




## -remarks



To determine the buffer size that is required for a specific method request, you can call this method with MethodData set to <b>NULL</b> and DataLength equal to zero. The method returns HRESULT_FROM_WIN32(ERROR_MORE_DATA and BytesReturned contains the size of the required buffer.




## -see-also

<a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>



<a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsControl::KsMethod method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

