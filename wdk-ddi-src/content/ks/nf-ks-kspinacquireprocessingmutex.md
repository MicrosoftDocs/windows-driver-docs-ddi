---
UID: NF:ks.KsPinAcquireProcessingMutex
title: KsPinAcquireProcessingMutex function
author: windows-driver-content
description: The KsPinAcquireProcessingMutex function acquires the processing mutex for the AVStream pin specified by Pin.
old-location: stream\kspinacquireprocessingmutex.htm
old-project: stream
ms.assetid: ce1fb470-6fee-4de0-a5db-15875a14e581
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avfunc_d06d3037-45b0-4931-86e4-ef7c586bcdf1.xml, ks/KsPinAcquireProcessingMutex, KsPinAcquireProcessingMutex function [Streaming Media Devices], KsPinAcquireProcessingMutex, stream.kspinacquireprocessingmutex
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsPinAcquireProcessingMutex
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinAcquireProcessingMutex function


## -description


The<b> KsPinAcquireProcessingMutex </b>function acquires the processing mutex for the AVStream pin specified by <i>Pin</i>.


## -syntax


````
void KsPinAcquireProcessingMutex(
  _In_ PKSPIN Pin
);
````


## -parameters




### -param Pin [in]

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure for which to acquire the processing mutex.


## -returns


None



## -remarks


For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.



## -see-also

<a href="..\ks\nf-ks-ksreleasecontrol.md">KsReleaseControl</a>

<a href="..\ks\nf-ks-kspinreleaseprocessingmutex.md">KsPinReleaseProcessingMutex</a>

<a href="..\ks\nf-ks-kspinacquirecontrol.md">KsPinAcquireControl</a>

<a href="..\ks\nf-ks-kspinreleasecontrol.md">KsPinReleaseControl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinAcquireProcessingMutex function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

