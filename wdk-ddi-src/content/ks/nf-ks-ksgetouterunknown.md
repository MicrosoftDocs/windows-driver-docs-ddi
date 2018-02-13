---
UID: NF:ks.KsGetOuterUnknown
title: KsGetOuterUnknown function
author: windows-driver-content
description: The KsGetOuterUnknown function returns the outer IUnknown of a given AVStream object.
old-location: stream\ksgetouterunknown.htm
old-project: stream
ms.assetid: e86e2c96-9ae5-4f6d-9c76-1c2816f318e7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsGetOuterUnknown, KsGetOuterUnknown function [Streaming Media Devices], ks/KsGetOuterUnknown, avfunc_5b660e76-03af-4fba-92f9-f11eeeaa3da0.xml, stream.ksgetouterunknown
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
-	KsGetOuterUnknown
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetOuterUnknown function


## -description


The<b> KsGetOuterUnknown </b>function returns the outer <b>IUnknown</b> of a given AVStream object.


## -syntax


````
PUNKNOWN KsGetOuterUnknown(
  _In_ PVOID Object
);
````


## -parameters




### -param Object [in]

A pointer to an AVStream object for which to return the outer <b>IUnknown</b> interface.


## -returns



<b>KsGetOuterUnknown</b> returns a pointer to the outer <b>IUnknown</b> interface of <i>Object</i>. The client can then call the <b>QueryInterface</b> method to determine whether the component supports a given interface.




## -remarks



Minidrivers should not call this function directly. Instead, use one of the inline versions that perform automatic typecasting: <a href="..\ks\nf-ks-ksdevicegetouterunknown.md">KsDeviceGetOuterUnknown</a>, <a href="..\ks\nf-ks-ksfilterfactorygetouterunknown.md">KsFilterFactoryGetOuterUnknown</a>, <a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>, <a href="..\ks\nf-ks-kspingetouterunknown.md">KsPinGetOuterUnknown</a>.

Minidrivers using this function must include <i>kcom.h</i> and use a C++ compiler.




## -see-also

<a href="..\ks\nf-ks-ksdevicegetouterunknown.md">KsDeviceGetOuterUnknown</a>



<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>



<a href="..\ks\nf-ks-kspingetouterunknown.md">KsPinGetOuterUnknown</a>



<a href="..\ks\nf-ks-ksfilterfactorygetouterunknown.md">KsFilterFactoryGetOuterUnknown</a>



<a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>



<a href="..\ks\nn-ks-ikscontrol.md">IKsControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetOuterUnknown function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

