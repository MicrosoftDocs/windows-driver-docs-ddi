---
UID: NF:ks.KsPinGetOuterUnknown
title: KsPinGetOuterUnknown function
author: windows-driver-content
description: The KsPinGetOuterUnknown function returns the outer IUnknown of the pin specified by Pin.
old-location: stream\kspingetouterunknown.htm
old-project: stream
ms.assetid: 58b14ddd-6698-487a-925d-7d559057e55d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinGetOuterUnknown, KsPinGetOuterUnknown function [Streaming Media Devices], avfunc_6a9c21cd-38ab-4277-8379-346af4c9c4c9.xml, ks/KsPinGetOuterUnknown, stream.kspingetouterunknown
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsPinGetOuterUnknown
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinGetOuterUnknown function


## -description


The<b> KsPinGetOuterUnknown</b> function returns the outer <b>IUnknown</b> of the pin specified by <i>Pin</i>.


## -syntax


````
PUNKNOWN __inline KsPinGetOuterUnknown(
  _In_ PKSPIN Pin
);
````


## -parameters




### -param Pin [in]

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure for which to return the outer <b>IUnknown</b>.


## -returns



<b>KsPinGetOuterUnknown</b> returns a pointer to the outer <b>IUnknown</b> interface of <i>Pin</i>. This can subsequently be used to query for other interfaces.




## -remarks



<b>KsPinGetOuterUnknown</b> is an inline function call to <a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>. 




## -see-also

<a href="..\ks\nf-ks-ksdevicegetouterunknown.md">KsDeviceGetOuterUnknown</a>



<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>



<a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>



<a href="..\ks\nf-ks-ksfilterfactorygetouterunknown.md">KsFilterFactoryGetOuterUnknown</a>



<a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a>



<a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a>



<a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetOuterUnknown function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

