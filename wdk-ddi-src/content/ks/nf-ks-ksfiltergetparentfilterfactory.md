---
UID: NF:ks.KsFilterGetParentFilterFactory
title: KsFilterGetParentFilterFactory function
author: windows-driver-content
description: The KsFilterGetParentFilterFactory function returns the parent filter factory of the given filter.
old-location: stream\ksfiltergetparentfilterfactory.htm
tech.root: stream
ms.assetid: 08b02410-3e18-4bfd-8f10-2a12a5f94e16
ms.date: 4/23/2018
ms.keywords: KsFilterGetParentFilterFactory, KsFilterGetParentFilterFactory function [Streaming Media Devices], avfunc_fd87cd4c-2ce4-41c6-8b73-4ccebd6e3015.xml, ks/KsFilterGetParentFilterFactory, stream.ksfiltergetparentfilterfactory
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
-	KsFilterGetParentFilterFactory
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterGetParentFilterFactory function


## -description


The<b> KsFilterGetParentFilterFactory</b> function returns the parent filter factory of the given filter.


## -parameters




### -param Filter [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> structure for which to return the parent filter factory.


## -returns



<b>KsFilterGetParentFilterFactory</b> returns a pointer to the parent <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a> structure of <i>Filter.</i> This is the AVStream filter factory from which <i>Filter</i> was created.




## -remarks



This call is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562658">KsGetParent</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562658">KsGetParent</a>
 

 

