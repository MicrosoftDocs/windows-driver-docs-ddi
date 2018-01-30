---
UID: NF:ks.KsGateTurnInputOn
title: KsGateTurnInputOn function
author: windows-driver-content
description: The KsGateTurnInputOn function turns on an existing input to Gate.
old-location: stream\ksgateturninputon.htm
old-project: stream
ms.assetid: 68c914bf-a293-42b0-85aa-c9e8f2ba18ac
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsGateTurnInputOn, KsGateTurnInputOn function [Streaming Media Devices], stream.ksgateturninputon, ks/KsGateTurnInputOn, avfunc_9aaa9c85-b3a1-49ae-8135-6402f7bc1755.xml
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
-	KsGateTurnInputOn
product: Windows
targetos: Windows
req.typenames: 
---

# KsGateTurnInputOn function


## -description


The<b> KsGateTurnInputOn</b> function turns on an existing input to <i>Gate</i>.


## -syntax


````
void __inline KsGateTurnInputOn(
  _In_opt_ PKSGATE Gate
);
````


## -parameters




### -param Gate [in, optional]

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure representing the gate that currently has an input in the OFF state to transition to the ON state. May be an AND gate or an OR gate.


## -returns


None



## -remarks


It is the minidriver's responsibility to verify that the gate that the minidriver passes to <b>KsGateTurnInputOn</b> has at least one OFF input. If you call this function with an AND gate that has no inputs currently in the OFF state, the call sets the AND gate into an invalid state. If you call this function with an OR gate that has no inputs currently in the OFF state, the result is equivalent to adding another input in the ON state to <i>Gate</i>.

Furthermore, if turning an input on would cause <i>Gate</i> to transition from the closed state to the open state, this call instead turns on an input to whatever gate is attached to <i>Gate</i>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>. 



## -see-also

<a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>

<a href="..\ks\nf-ks-ksgateaddoninputtoor.md">KsGateAddOnInputToOr</a>

<a href="..\ks\nf-ks-ksgateremoveoffinputfromor.md">KsGateRemoveOffInputFromOr</a>

<a href="..\ks\nf-ks-ksgateaddoninputtoand.md">KsGateAddOnInputToAnd</a>

<a href="..\ks\nf-ks-ksgateaddoffinputtoor.md">KsGateAddOffInputToOr</a>

<a href="..\ks\nf-ks-ksgateremoveoninputfromor.md">KsGateRemoveOnInputFromOr</a>

<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>

<a href="..\ks\nf-ks-ksgateremoveoffinputfromand.md">KsGateRemoveOffInputFromAnd</a>

<a href="..\ks\nf-ks-ksgateaddoffinputtoand.md">KsGateAddOffInputToAnd</a>

<a href="..\ks\nf-ks-ksgateremoveoninputfromand.md">KsGateRemoveOnInputFromAnd</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateTurnInputOn function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

