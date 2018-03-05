---
UID: NF:ks.KsGateAddOnInputToAnd
title: KsGateAddOnInputToAnd function
author: windows-driver-content
description: The KsGateAddOnInputToAnd function adds a new input in the ON state to a given AND gate.
old-location: stream\ksgateaddoninputtoand.htm
old-project: stream
ms.assetid: cde5e5d8-9af7-452e-afaa-8669c5749c9e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGateAddOnInputToAnd, KsGateAddOnInputToAnd function [Streaming Media Devices], avfunc_a7d04c8d-b1d7-46a8-bd34-2ec9de4f2196.xml, ks/KsGateAddOnInputToAnd, stream.ksgateaddoninputtoand
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
-	KsGateAddOnInputToAnd
product: Windows
targetos: Windows
req.typenames: 
---

# KsGateAddOnInputToAnd function


## -description


The<b> KsGateAddOnInputToAnd</b> function adds a new input in the ON state to a given AND gate.


## -syntax


````
void __inline KsGateAddOnInputToAnd(
  _In_ PKSGATE AndGate
);
````


## -parameters




### -param AndGate [in]

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure representing the AND gate to which to add a new ON input.


## -returns



None




## -remarks



This function should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

This call is an empty function. It should be used for code readability and clarity. 




## -see-also

<a href="..\ks\nf-ks-ksgateaddoffinputtoand.md">KsGateAddOffInputToAnd</a>



<a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>



<a href="..\ks\nf-ks-ksgateremoveoffinputfromand.md">KsGateRemoveOffInputFromAnd</a>



<a href="..\ks\nf-ks-ksgateremoveoninputfromand.md">KsGateRemoveOnInputFromAnd</a>



<a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateAddOnInputToAnd function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

