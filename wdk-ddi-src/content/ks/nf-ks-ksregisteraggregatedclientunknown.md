---
UID: NF:ks.KsRegisterAggregatedClientUnknown
title: KsRegisterAggregatedClientUnknown function
author: windows-driver-content
description: In a manner very similar to COM, the KsRegisterAggregatedClientUnknown function aggregates two objects:\_the specified AVStream object and a client unknown object.
old-location: stream\ksregisteraggregatedclientunknown.htm
old-project: stream
ms.assetid: b0e18e39-2435-4823-aab4-ba52d218294a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.ksregisteraggregatedclientunknown, KsRegisterAggregatedClientUnknown, ks/KsRegisterAggregatedClientUnknown, KsRegisterAggregatedClientUnknown function [Streaming Media Devices], avfunc_1b7f6d25-4aae-4580-b8d2-5050c9ffede1.xml
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
-	KsRegisterAggregatedClientUnknown
product: Windows
targetos: Windows
req.typenames: 
---

# KsRegisterAggregatedClientUnknown function


## -description


In a manner very similar to COM, the <b>KsRegisterAggregatedClientUnknown</b> function aggregates two objects: the specified AVStream object and a client unknown object.


## -syntax


````
PUNKNOWN KsRegisterAggregatedClientUnknown(
  _In_ PVOID    Object,
  _In_ PUNKNOWN ClientUnknown
);
````


## -parameters




### -param Object [in]

A pointer to the AVStream object to become the outer unknown interface.


### -param ClientUnknown [in]

A pointer to an <b>IUnknown</b> interface.


## -returns



Returns the newly created aggregate object.




## -remarks



The client unknown becomes the inner part of the aggregate object, and the AVStream object becomes the outer unknown. When an interface is queried that AVStream does not handle, AVStream passes the query is to the inner aggregate.

If a client unknown is already aggregated on the AVStream object, AVStream releases the previously registered aggregate and uses the unknown passed to <b>KsRegisterAggregatedClientUnknown</b> as the new inner unknown.

There are four wrappers to <b>KsRegisterAggregatedClientUnknown</b> that perform typecasts.

Minidrivers do not need to be running in a C++ environment to use this function.




## -see-also

<a href="..\ks\nf-ks-ksdeviceregisteraggregatedclientunknown.md">KsDeviceRegisterAggregatedClientUnknown</a>



<a href="..\ks\nf-ks-ksfilterregisteraggregatedclientunknown.md">KsFilterRegisterAggregatedClientUnknown</a>



<a href="..\ks\nf-ks-kspinregisteraggregatedclientunknown.md">KsPinRegisterAggregatedClientUnknown</a>



<a href="..\ks\nf-ks-ksfilterfactoryregisteraggregatedclientunknown.md">KsFilterFactoryRegisterAggregatedClientUnknown</a>



<a href="..\ks\nf-ks-ksdeviceregisteraggregatedclientunknown.md">KsDeviceRegisterAggregatedClientUnknown</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsRegisterAggregatedClientUnknown function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

