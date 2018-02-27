---
UID: NF:ks.KsFilterReleaseProcessingMutex
title: KsFilterReleaseProcessingMutex function
author: windows-driver-content
description: The KsFilterReleaseProcessingMutex function releases the processing mutex for the AVStream filter specified by Filter.
old-location: stream\ksfilterreleaseprocessingmutex.htm
old-project: stream
ms.assetid: 8ccf24a4-f087-4d61-8a9e-4bc05d7ec7bf
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterReleaseProcessingMutex, KsFilterReleaseProcessingMutex function [Streaming Media Devices], avfunc_35026563-e7aa-4305-a4fc-2558c1b21aa7.xml, ks/KsFilterReleaseProcessingMutex, stream.ksfilterreleaseprocessingmutex
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsFilterReleaseProcessingMutex
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterReleaseProcessingMutex function


## -description


The<b> KsFilterReleaseProcessingMutex </b>function releases the processing mutex for the AVStream filter specified by <i>Filter</i>.


## -syntax


````
void KsFilterReleaseProcessingMutex(
  _In_ PKSFILTER Filter
);
````


## -parameters




### -param Filter [in]

A pointer to a <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure representing the AVStream filter for which to release the processing mutex.


## -returns



None




## -remarks



For more AVStream-specific information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a> and <a href="https://msdn.microsoft.com/dd84fe3f-352e-4641-99d7-792ccecb0b40">Processing Mutex in AVStream</a>.




## -see-also

<a href="..\ks\nf-ks-ksfilteracquireprocessingmutex.md">KsFilterAcquireProcessingMutex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterReleaseProcessingMutex function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

