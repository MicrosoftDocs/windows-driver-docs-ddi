---
UID: NF:ks.KsFilterRegisterAggregatedClientUnknown
title: KsFilterRegisterAggregatedClientUnknown function
author: windows-driver-content
description: This inline function is a wrapper for KsRegisterAggregatedClientUnknown.
old-location: stream\ksfilterregisteraggregatedclientunknown.htm
old-project: stream
ms.assetid: aac70408-83b8-4bfd-8ce9-9b74483f6282
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: avfunc_c485334a-83bd-474e-abfc-ced331ca55db.xml, KsFilterRegisterAggregatedClientUnknown function [Streaming Media Devices], KsFilterRegisterAggregatedClientUnknown, ks/KsFilterRegisterAggregatedClientUnknown, stream.ksfilterregisteraggregatedclientunknown
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsFilterRegisterAggregatedClientUnknown
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterRegisterAggregatedClientUnknown function


## -description


This inline function is a wrapper for <a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>.


## -syntax


````
PUNKNOWN __inline KsFilterRegisterAggregatedClientUnknown(
  _In_ PKSFILTER Filter,
  _In_ PUNKNOWN  ClientUnknown
);
````


## -parameters




### -param Filter [in]

A pointer to the specified AVStream <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure.


### -param ClientUnknown [in]

The client <b>IUnknown</b> interface object.


## -returns



<b>KsFilterRegisterAggregatedClientUnknown</b> returns a pointer to an <b>IUnknown</b> interface representing the newly created aggregate object.




## -remarks



Note that this inline function only performs a typecast and then calls <a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>.




## -see-also

<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterRegisterAggregatedClientUnknown function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

