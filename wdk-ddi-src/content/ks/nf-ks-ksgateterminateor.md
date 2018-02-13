---
UID: NF:ks.KsGateTerminateOr
title: KsGateTerminateOr function
author: windows-driver-content
description: The KsGateTerminateOr function deletes an existing OR gate and removes an input from any attached AND gate.
old-location: stream\ksgateterminateor.htm
old-project: stream
ms.assetid: 6d73ce17-1fbc-4d12-87f0-ac10889b85be
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avfunc_b2bf57c5-4f08-456a-bbac-217531cf5bc3.xml, KsGateTerminateOr, ks/KsGateTerminateOr, KsGateTerminateOr function [Streaming Media Devices], stream.ksgateterminateor
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsGateTerminateOr
product: Windows
targetos: Windows
req.typenames: 
---

# KsGateTerminateOr function


## -description


The<b> KsGateTerminateOr</b> function deletes an existing OR gate and removes an input from any attached AND gate.


## -syntax


````
void __inline KsGateTerminateOr(
  _In_ PKSGATE OrGate
);
````


## -parameters




### -param OrGate [in]

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure that is the OR gate to delete. This gate must be at the beginning of a gate chain.


## -returns



None




## -remarks



Logical gates should be deleted in a front to back manner. <b>KsGateTerminateOr</b> does not update the gate chain for gates that are deleted at the end or in the middle. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.




## -see-also

<a href="..\ks\nf-ks-ksgateterminateand.md">KsGateTerminateAnd</a>



<a href="..\ks\nf-ks-ksgateinitializeand.md">KsGateInitializeAnd</a>



<a href="..\ks\nf-ks-ksgateinitializeor.md">KsGateInitializeOr</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateTerminateOr function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

