---
UID: NF:ks.KsGateAddOnInputToOr
title: KsGateAddOnInputToOr function
author: windows-driver-content
description: The KsGateAddOnInputToOr function adds a new input in the ON state to a given OR gate.
old-location: stream\ksgateaddoninputtoor.htm
old-project: stream
ms.assetid: aaa6891b-f9f9-40d5-b0eb-e17f511e2611
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGateAddOnInputToOr, KsGateAddOnInputToOr function [Streaming Media Devices], avfunc_f19411cd-eca5-4acb-b0ca-f470a72a4afd.xml, ks/KsGateAddOnInputToOr, stream.ksgateaddoninputtoor
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsGateAddOnInputToOr
product: Windows
targetos: Windows
req.typenames: 
---

# KsGateAddOnInputToOr function


## -description


The<b> KsGateAddOnInputToOr</b> function adds a new input in the ON state to a given OR gate.


## -syntax


````
void __inline KsGateAddOnInputToOr(
  _In_ PKSGATE OrGate
);
````


## -parameters




### -param OrGate [in]

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure representing the OR gate to which to add a new ON input.


## -returns



None




## -remarks



Adding an ON input to an OR gate in the OFF or closed state results in the gate opening and the transition being propagated to any gates attached to <i>OrGate</i>. Use this function only with gates that were specifically created as OR gates. AVStream does not verify that the given gate is an OR gate.

This call is an inline function call to <a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>. Minidrivers should call <b>KsGateAddOnInputToOr</b> rather than <b>KsGateTurnInputOn</b> if conceptually adding a new input to the gate. 




## -see-also

<a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>



<a href="..\ks\nf-ks-ksgateremoveoffinputfromor.md">KsGateRemoveOffInputFromOr</a>



<a href="..\ks\nf-ks-ksgateremoveoninputfromor.md">KsGateRemoveOnInputFromOr</a>



<a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>



<a href="..\ks\nf-ks-ksgateaddoffinputtoor.md">KsGateAddOffInputToOr</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateAddOnInputToOr function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

