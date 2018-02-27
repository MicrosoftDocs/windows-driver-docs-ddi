---
UID: NF:ks.KsDeviceGetOuterUnknown
title: KsDeviceGetOuterUnknown function
author: windows-driver-content
description: The KsDeviceGetOuterUnknown function returns the outer IUnknown of the AVStream device specified by Device.
old-location: stream\ksdevicegetouterunknown.htm
old-project: stream
ms.assetid: a63cdc50-6bbb-4bff-8536-0bf31fed01de
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsDeviceGetOuterUnknown, KsDeviceGetOuterUnknown function [Streaming Media Devices], avfunc_c1b85ab7-92b9-4c7c-a9c8-0cf1f9e93458.xml, ks/KsDeviceGetOuterUnknown, stream.ksdevicegetouterunknown
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsDeviceGetOuterUnknown
product: Windows
targetos: Windows
req.typenames: 
---

# KsDeviceGetOuterUnknown function


## -description


The<b> KsDeviceGetOuterUnknown</b> function returns the outer <b>IUnknown</b> of the AVStream device specified by <i>Device</i>.


## -syntax


````
PUNKNOWN __inline KsDeviceGetOuterUnknown(
  _In_ PKSDEVICE Device
);
````


## -parameters




### -param Device [in]

A pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure for which to get the outer unknown interface.


## -returns



Returns a pointer to an outer <b>IUnknown</b> of <i>Device</i>. This interface can then be used to query for other interfaces.




## -remarks



This call is an inline function call to <a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>.




## -see-also

<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>



<a href="..\ks\nf-ks-kspingetouterunknown.md">KsPinGetOuterUnknown</a>



<a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a>



<a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>



<a href="..\ks\nf-ks-ksfilterfactorygetouterunknown.md">KsFilterFactoryGetOuterUnknown</a>



<a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDeviceGetOuterUnknown function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

