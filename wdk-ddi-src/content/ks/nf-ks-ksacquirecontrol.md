---
UID: NF:ks.KsAcquireControl
title: KsAcquireControl function (ks.h)
description: The KsAcquireControl function acquires the filter control mutex for Object.
old-location: stream\ksacquirecontrol.htm
tech.root: stream
ms.assetid: c316382c-8416-43c2-b5fd-2d52d01e1419
ms.date: 04/23/2018
ms.keywords: KsAcquireControl, KsAcquireControl function [Streaming Media Devices], avfunc_a3c1eb2c-db95-463f-98f5-a158dd1e14f5.xml, ks/KsAcquireControl, stream.ksacquirecontrol
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
-	KsAcquireControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAcquireControl function


## -description


The <b>KsAcquireControl</b> function acquires the filter control mutex for <i>Object</i>. 


## -parameters




### -param Object [in]

A pointer to the object for which to acquire the filter control mutex. This should be a pointer to either a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>, cast to PVOID.


## -returns



None




## -remarks



Minidrivers typically do not call this function directly, but instead call either <a href="https://msdn.microsoft.com/library/windows/hardware/ff562523">KsFilterAcquireControl</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563485">KsPinAcquireControl</a>. These functions provide the necessary typecasting to PVOID automatically.

For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562523">KsFilterAcquireControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563485">KsPinAcquireControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566780">KsReleaseControl</a>
 

 

