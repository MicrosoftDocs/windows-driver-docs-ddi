---
UID: NF:ks.KsGetOuterUnknown
title: KsGetOuterUnknown function
author: windows-driver-content
description: The KsGetOuterUnknown function returns the outer IUnknown of a given AVStream object.
old-location: stream\ksgetouterunknown.htm
old-project: stream
ms.assetid: e86e2c96-9ae5-4f6d-9c76-1c2816f318e7
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsGetOuterUnknown, KsGetOuterUnknown function [Streaming Media Devices], avfunc_5b660e76-03af-4fba-92f9-f11eeeaa3da0.xml, ks/KsGetOuterUnknown, stream.ksgetouterunknown
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
-	KsGetOuterUnknown
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGetOuterUnknown function


## -description


The<b> KsGetOuterUnknown </b>function returns the outer <b>IUnknown</b> of a given AVStream object.


## -parameters




### -param Object [in]

A pointer to an AVStream object for which to return the outer <b>IUnknown</b> interface.


## -returns



<b>KsGetOuterUnknown</b> returns a pointer to the outer <b>IUnknown</b> interface of <i>Object</i>. The client can then call the <b>QueryInterface</b> method to determine whether the component supports a given interface.




## -remarks



Minidrivers should not call this function directly. Instead, use one of the inline versions that perform automatic typecasting: <a href="https://msdn.microsoft.com/library/windows/hardware/ff561686">KsDeviceGetOuterUnknown</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562535">KsFilterFactoryGetOuterUnknown</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562547">KsFilterGetOuterUnknown</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff563515">KsPinGetOuterUnknown</a>.

Minidrivers using this function must include <i>kcom.h</i> and use a C++ compiler.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559766">IKsControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561686">KsDeviceGetOuterUnknown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562535">KsFilterFactoryGetOuterUnknown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562547">KsFilterGetOuterUnknown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563515">KsPinGetOuterUnknown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>
 

 

