---
UID: NF:ks.KsPinReleaseControl
title: KsPinReleaseControl function
author: windows-driver-content
description: The KsPinReleaseControl function releases the control mutex for the AVStream pin specified by Pin.
old-location: stream\kspinreleasecontrol.htm
old-project: stream
ms.assetid: ead50a69-fe33-4e6c-84f9-98491d188140
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsPinReleaseControl, KsPinReleaseControl function [Streaming Media Devices], avfunc_24f35b7d-4ecc-4a64-8b78-9972ba7bab5c.xml, ks/KsPinReleaseControl, stream.kspinreleasecontrol
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
-	KsPinReleaseControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinReleaseControl function


## -description


The<b> KsPinReleaseControl </b>function releases the control mutex for the AVStream pin specified by <i>Pin</i>.


## -parameters




### -param Pin [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure representing the pin for which to release the control mutex.


## -returns



None




## -remarks



The pin control mutex is the same mutex that is used by <i>Pin</i>'s parent. In other words, the pin control mutex <i>is</i> the filter control mutex of <i>Pin</i>'s parent. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

Note that this function is an inline call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566780">KsReleaseControl</a>. Minidrivers manipulating a pin should call this function instead of calling <b>KsReleaseControl</b> directly. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560908">KsAcquireControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563485">KsPinAcquireControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566780">KsReleaseControl</a>
 

 

