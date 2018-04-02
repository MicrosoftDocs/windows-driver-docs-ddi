---
UID: NF:ks.KsFilterFactoryGetFirstChildFilter
title: KsFilterFactoryGetFirstChildFilter function
author: windows-driver-content
description: The KsFilterFactoryGetFirstChildFilter function returns the first instantiated filter created by FilterFactory.
old-location: stream\ksfilterfactorygetfirstchildfilter.htm
old-project: stream
ms.assetid: 72eb23aa-4f0e-4ef5-baee-c0735253684e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterFactoryGetFirstChildFilter, KsFilterFactoryGetFirstChildFilter function [Streaming Media Devices], avfunc_1e512072-d270-48d9-8289-feaf8d2bcf35.xml, ks/KsFilterFactoryGetFirstChildFilter, stream.ksfilterfactorygetfirstchildfilter
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
-	KsFilterFactoryGetFirstChildFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryGetFirstChildFilter function


## -description


The<b> KsFilterFactoryGetFirstChildFilter</b> function returns the first instantiated filter created by <i>FilterFactory</i>.


## -parameters




### -param FilterFactory [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a> structure for which to find the first instantiated child filter.


## -returns



<b>KsFilterFactoryGetFirstChildFilter</b> returns a pointer to the first instantiated <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> structure created by <i>FilterFactory</i>. If there are no instantiated filters created by <i>FilterFactory</i>, <b>NULL</b> is returned.




## -remarks



This call is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562626">KsGetFirstChild</a>. Note that the object hierarchy is guaranteed to be stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562546">KsFilterGetNextSiblingFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562626">KsGetFirstChild</a>
 

 

