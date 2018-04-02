---
UID: NF:ks.KsReleaseControl
title: KsReleaseControl function
author: windows-driver-content
description: The KsReleaseControl function releases the control mutex for Object.
old-location: stream\ksreleasecontrol.htm
old-project: stream
ms.assetid: f585f1ad-7ed0-49b1-ab35-a6b879118b38
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsReleaseControl, KsReleaseControl function [Streaming Media Devices], avfunc_b568770e-1fe0-47d5-8fd4-ac210cd4be30.xml, ks/KsReleaseControl, stream.ksreleasecontrol
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
-	KsReleaseControl
product: Windows
targetos: Windows
req.typenames: 
---

# KsReleaseControl function


## -description


The<b> KsReleaseControl </b>function releases the control mutex for <i>Object</i>.


## -parameters




### -param Object [in]

The object for which to release the control mutex.


## -returns



None




## -remarks



<i>Object</i> should be either a filter or a pin cast to PVOID.

Minidrivers typically do not call <b>KsReleaseControl</b> directly, but instead call <a href="https://msdn.microsoft.com/library/windows/hardware/ff562551">KsFilterReleaseControl</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563526">KsPinReleaseControl</a>. These versions automatically provide the necessary typecasting to PVOID.

For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560908">KsAcquireControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562523">KsFilterAcquireControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562551">KsFilterReleaseControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563485">KsPinAcquireControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563526">KsPinReleaseControl</a>
 

 

