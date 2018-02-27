---
UID: NN:portcls.IMiniport
title: IMiniport
author: windows-driver-content
description: The IMiniport interface is the generic miniport interface that all miniport objects support. IMiniport inherits from the IUnknown interface.
old-location: audio\iminiport.htm
old-project: audio
ms.assetid: 981a3560-473a-40b2-a1dc-4ab9dc618e67
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IMiniport, IMiniport interface [Audio Devices], IMiniport interface [Audio Devices], described, audio.iminiport, audmp-routines_8ecaedd2-12d2-420f-a5e7-0f71451cf989.xml, portcls/IMiniport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IMiniport
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniport interface


## -description


The <code>IMiniport</code> interface is the generic miniport interface that all miniport objects support. <code>IMiniport</code> inherits from the <b>IUnknown</b> interface.

<code>IMiniport</code> is the base interface for the following miniport interfaces:
<dl>
<dd>

<a href="..\dmusicks\nn-dmusicks-iminiportdmus.md">IMiniportDMus</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iminiportmidi.md">IMiniportMidi</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iminiporttopology.md">IMiniportTopology</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iminiportwavecyclic.md">IMiniportWaveCyclic</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iminiportwavepci.md">IMiniportWavePci</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iminiportwavert.md">IMiniportWaveRT</a>


</dd>
</dl>
