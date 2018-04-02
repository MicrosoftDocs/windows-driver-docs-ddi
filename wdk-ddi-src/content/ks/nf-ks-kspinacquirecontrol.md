---
UID: NF:ks.KsPinAcquireControl
title: KsPinAcquireControl function
author: windows-driver-content
description: The KsPinAcquireControl function acquires the control mutex for the AVStream pin specified by Pin.
old-location: stream\kspinacquirecontrol.htm
old-project: stream
ms.assetid: 05ff1829-8305-4bc4-be22-233d391a5dc0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinAcquireControl, KsPinAcquireControl function [Streaming Media Devices], avfunc_fd5d1466-6403-42cf-aab7-d044014c4abf.xml, ks/KsPinAcquireControl, stream.kspinacquirecontrol
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
-	KsPinAcquireControl
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinAcquireControl function


## -description


The<b> KsPinAcquireControl</b> function acquires the control mutex for the AVStream pin specified by <i>Pin</i>.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> for which to acquire the control mutex.


## -returns



None




## -remarks



The pin control mutex is the same mutex that is used by <i>Pin</i>'s parent. This means that the mutex for <i>Pin</i> is also a filter control mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

<b>KsPinAcquireControl</b> is an inline call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560908">KsAcquireControl</a> with the appropriate typecasting. Minidrivers manipulating pins should call <b>KsPinAcquireControl</b> instead of calling <b>KsAcquireControl</b> directly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560908">KsAcquireControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563526">KsPinReleaseControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566780">KsReleaseControl</a>
 

 

