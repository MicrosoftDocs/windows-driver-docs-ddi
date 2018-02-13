---
UID: NF:ks.KsGateTurnInputOff
title: KsGateTurnInputOff function
author: windows-driver-content
description: The KsGateTurnInputOff function turns off an existing input to Gate.
old-location: stream\ksgateturninputoff.htm
old-project: stream
ms.assetid: cbcbb49a-8c45-4843-8c21-6c4d8c7bc6c6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsGateTurnInputOff function [Streaming Media Devices], KsGateTurnInputOff, ks/KsGateTurnInputOff, avfunc_ba116904-80e2-4288-a8d1-d03c0194ef51.xml, stream.ksgateturninputoff
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
-	KsGateTurnInputOff
product: Windows
targetos: Windows
req.typenames: 
---

# KsGateTurnInputOff function


## -description


The<b> KsGateTurnInputOff</b> function turns off an existing input to <i>Gate</i>.


## -syntax


````
void __inline KsGateTurnInputOff(
  _In_opt_ PKSGATE Gate
);
````


## -parameters




### -param Gate [in, optional]

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure that is the gate to transition to the OFF state. Must currently have an input in the ON state. May be an AND gate or an OR gate.


## -returns



None




## -remarks



It is the minidriver's responsibility to verify that the gate that the minidriver passes to <b>KsGateTurnInputOff</b> has at least one ON input. If you call this function with an OR gate that has no inputs currently in the ON state, the call sets the OR gate into an invalid state. If you call this function with an AND gate that has no inputs currently in the ON state, the result is equivalent to adding another input in the OFF state to <i>Gate</i>.

Furthermore, if turning an input off would cause <i>Gate</i> to transition from the open state to the closed state, this call instead turns off an input to whatever gate is attached to <i>Gate</i>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.




## -see-also

<a href="..\ks\nf-ks-ksgateremoveoffinputfromor.md">KsGateRemoveOffInputFromOr</a>



<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>



<a href="..\ks\nf-ks-ksgateaddoffinputtoor.md">KsGateAddOffInputToOr</a>



<a href="..\ks\nf-ks-ksgateaddoninputtoor.md">KsGateAddOnInputToOr</a>



<a href="..\ks\nf-ks-ksgateaddoffinputtoand.md">KsGateAddOffInputToAnd</a>



<a href="..\ks\nf-ks-ksgateaddoninputtoand.md">KsGateAddOnInputToAnd</a>



<a href="..\ks\nf-ks-ksgateremoveoninputfromand.md">KsGateRemoveOnInputFromAnd</a>



<a href="..\ks\nf-ks-ksgateremoveoffinputfromand.md">KsGateRemoveOffInputFromAnd</a>



<a href="..\ks\nf-ks-ksgateremoveoninputfromor.md">KsGateRemoveOnInputFromOr</a>



<a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateTurnInputOff function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

