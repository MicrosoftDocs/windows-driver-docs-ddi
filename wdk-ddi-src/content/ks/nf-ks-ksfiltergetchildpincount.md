---
UID: NF:ks.KsFilterGetChildPinCount
title: KsFilterGetChildPinCount function
author: windows-driver-content
description: The KsFilterGetChildPinCountfunctionreturns the number of pins of a given type that are currently instantiated on a given filter.
old-location: stream\ksfiltergetchildpincount.htm
old-project: stream
ms.assetid: 29e78bc3-0dc2-4e76-b683-c1e9a2d454d4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsFilterGetChildPinCount, KsFilterGetChildPinCount function [Streaming Media Devices], KsFilterGetChildPinCount, avfunc_cddbf6bc-da19-47a6-96d5-0d4151e70ff8.xml, stream.ksfiltergetchildpincount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsFilterGetChildPinCount
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterGetChildPinCount function


## -description


The<b> KsFilterGetChildPinCount</b><b></b>function<b></b>returns the number of pins of a given type that are currently instantiated on a given filter.


## -syntax


````
ULONG KsFilterGetChildPinCount(
  _In_ PKSFILTER Filter,
  _In_ ULONG     PinId
);
````


## -parameters




### -param Filter [in]

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure for which to find the number of instantiated pins of type <i>PinID</i>.


### -param PinId [in]

The pin type for which to find the number of instantiated pins. <i>PinID</i> is an index into the array of pin descriptors for the filter to which the pin belongs.


## -returns



<b>KsFilterGetChildPinCount</b> returns the number of pins of type <i>PinID</i> that are currently instantiated on <i>Filter</i>. If no such pins exist or if <i>PinID</i> is out of range, zero is returned.




## -remarks



The count returned by this call is guaranteed to be correct only if the function is called while the filter control mutex is held. The count remains correct after the call as long as this mutex continues to be held. As soon as the mutex is released, other pins can be added or removed, thereby altering the actual pin count.

For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also

<a href="..\ks\nf-ks-kspingetnextsiblingpin.md">KsPinGetNextSiblingPin</a>



<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>



<a href="..\ks\nf-ks-ksfiltergetfirstchildpin.md">KsFilterGetFirstChildPin</a>



<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterGetChildPinCount function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

