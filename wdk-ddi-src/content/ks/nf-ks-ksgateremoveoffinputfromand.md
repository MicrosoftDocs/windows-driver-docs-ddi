---
UID: NF:ks.KsGateRemoveOffInputFromAnd
title: KsGateRemoveOffInputFromAnd function
author: windows-driver-content
description: The KsGateRemoveOffInputFromAnd function removes an existing input that is in the OFF state from an AND gate.
old-location: stream\ksgateremoveoffinputfromand.htm
old-project: stream
ms.assetid: 37f463bb-6b7a-4262-9e4b-3650025acb7c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KsGateRemoveOffInputFromAnd function [Streaming Media Devices], avfunc_604705b6-08f8-4048-8b29-f89b645f971a.xml, stream.ksgateremoveoffinputfromand, ks/KsGateRemoveOffInputFromAnd, KsGateRemoveOffInputFromAnd
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
-	KsGateRemoveOffInputFromAnd
product: Windows
targetos: Windows
req.typenames: 
---

# KsGateRemoveOffInputFromAnd function


## -description


The<b> KsGateRemoveOffInputFromAnd</b> function removes an existing input that is in the OFF state from an AND gate.


## -syntax


````
void __inline KsGateRemoveOffInputFromAnd(
  _In_ PKSGATE AndGate
);
````


## -parameters




### -param AndGate [in]

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure representing the AND gate from which to remove an OFF input.


## -returns



None




## -remarks



Removing the last OFF input from the gate results in the gate opening and the transition being propagated to any gates connected to <i>AndGate</i>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

<b>KsGateRemoveOffInputFromAnd</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

<b>KsGateRemoveOffInputFromAnd</b> is an inline function call to <a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>. If conceptually removing an existing input to the gate rather than turning it off, a minidriver should call <b>KsGateRemoveOffInputFromAnd</b> instead of <b>KsGateTurnInputOn</b>.




## -see-also

<a href="..\ks\nf-ks-ksgateaddoffinputtoand.md">KsGateAddOffInputToAnd</a>



<a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>



<a href="..\ks\nf-ks-ksgateremoveoninputfromand.md">KsGateRemoveOnInputFromAnd</a>



<a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>



<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>



<a href="..\ks\nf-ks-ksgateaddoninputtoand.md">KsGateAddOnInputToAnd</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateRemoveOffInputFromAnd function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

