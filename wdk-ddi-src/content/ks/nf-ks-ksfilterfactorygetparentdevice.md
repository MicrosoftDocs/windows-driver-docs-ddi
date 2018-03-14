---
UID: NF:ks.KsFilterFactoryGetParentDevice
title: KsFilterFactoryGetParentDevice function
author: windows-driver-content
description: The KsFilterFactoryGetParentDevice function returns the parent device of the given filter factory.
old-location: stream\ksfilterfactorygetparentdevice.htm
old-project: stream
ms.assetid: ac1d10dc-d3cb-4a83-9f52-34ea90d2193b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterFactoryGetParentDevice, KsFilterFactoryGetParentDevice function [Streaming Media Devices], avfunc_35d9d582-f7d6-4c1f-8998-a6664527db2c.xml, ks/KsFilterFactoryGetParentDevice, stream.ksfilterfactorygetparentdevice
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
req.lib: 
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
-	KsFilterFactoryGetParentDevice
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryGetParentDevice function


## -description


The<b> KsFilterFactoryGetParentDevice</b> function returns the parent device of the given filter factory.


## -syntax


````
PKSDEVICE __inline KsFilterFactoryGetParentDevice(
  _In_ PKSFILTERFACTORY FilterFactory
);
````


## -parameters




### -param FilterFactory [in]

A pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure for which to return the parent device.


## -returns



<b>KsFilterFactoryGetParentDevice</b> returns a pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure representing the parent device of the filter factory. This is the AVStream device to which the filter factory belongs.




## -remarks



This call is an inline function call to <a href="..\ks\nf-ks-ksgetparent.md">KsGetParent</a>. Note that the object hierarchy is guaranteed to be stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>



<a href="..\ks\nf-ks-ksgetparent.md">KsGetParent</a>



 

 


