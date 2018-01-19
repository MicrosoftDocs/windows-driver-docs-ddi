---
UID: NF:ks.KsGateRemoveOffInputFromOr
title: KsGateRemoveOffInputFromOr function
author: windows-driver-content
description: The KsGateRemoveOffInputFromOr function removes an existing input that is in the OFF state from an OR gate.
old-location: stream\ksgateremoveoffinputfromor.htm
old-project: stream
ms.assetid: 191874ec-5d08-430e-ad14-520392e1a904
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsGateRemoveOffInputFromOr
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
req.alt-api: KsGateRemoveOffInputFromOr
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: 
---

# KsGateRemoveOffInputFromOr function



## -description
The<b> KsGateRemoveOffInputFromOr</b> function removes an existing input that is in the OFF state from an OR gate.



## -syntax

````
void __inline KsGateRemoveOffInputFromOr(
  _In_ PKSGATE OrGate
);
````


## -parameters

### -param OrGate [in]

A pointer to the <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure representing the OR gate from which to remove an OFF input.


## -returns
None


## -remarks
<b>KsGateRemoveOffInputFromOr</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is truly an AND gate.

For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

This call is an empty function. It should be used for code readability and clarity. 


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksgateaddoffinputtoor.md">KsGateAddOffInputToOr</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateaddoninputtoor.md">KsGateAddOnInputToOr</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateremoveoninputfromor.md">KsGateRemoveOnInputFromOr</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateRemoveOffInputFromOr function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

