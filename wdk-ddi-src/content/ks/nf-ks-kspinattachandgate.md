---
UID: NF:ks.KsPinAttachAndGate
title: KsPinAttachAndGate function
author: windows-driver-content
description: The KsPinAttachAndGate function connects Pin as an input to a previously initialized AND gate, and connects AndGate as an input to the relevant filter's AND gate.
old-location: stream\kspinattachandgate.htm
old-project: stream
ms.assetid: 63081b07-add8-49fc-b12d-6aa5c43356ce
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avfunc_395e0cf9-ba21-4b20-a37b-7758d1bfeca0.xml, ks/KsPinAttachAndGate, KsPinAttachAndGate, KsPinAttachAndGate function [Streaming Media Devices], stream.kspinattachandgate
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
req.irql: PASSIVE_LEVEL (See Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsPinAttachAndGate
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinAttachAndGate function


## -description


The<b> KsPinAttachAndGate</b> function connects <i>Pin</i> as an input to a previously initialized AND gate, and connects <i>AndGate</i> as an input to the relevant filter's AND gate.


## -syntax


````
void KsPinAttachAndGate(
  _In_     PKSPIN  Pin,
  _In_opt_ PKSGATE AndGate
);
````


## -parameters




### -param Pin [in]

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure to use an input to the AND gate.


### -param AndGate [in, optional]

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure that is the previously initialized AND gate to connect to the relevant filter's AND gate. If this optional parameter is <b>NULL</b>, any <b>KSGATE</b> currently attached to the pin is detached.


## -returns



None




## -remarks



To insert the gate, first call <a href="..\ks\nf-ks-ksgateinitializeand.md">KsGateInitializeAnd</a>. Then call <b>KsPinAttachAndGate</b>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

<b>KsPinAttachAndGate </b>must be called at IRQL = PASSIVE_LEVEL before the pin in question leaves KSSTATE_STOP.




## -see-also

<a href="..\ks\nf-ks-kspinattachorgate.md">KsPinAttachOrGate</a>



<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>



<a href="..\ks\nf-ks-ksgateinitializeand.md">KsGateInitializeAnd</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinAttachAndGate function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

