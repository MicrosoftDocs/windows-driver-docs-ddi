---
UID: NN:portcls.IPortClsVersion
title: IPortClsVersion
author: windows-driver-content
description: The IPortClsVersion interface is used by a miniport driver to identify the version of the Windows operating system that the driver is running on. The port driver implements this interface and exposes it to the miniport driver.
old-location: audio\iportclsversion.htm
old-project: audio
ms.assetid: 8a367bcb-680b-41be-975f-1a1f4bec3b60
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.iportclsversion, IPortClsVersion interface [Audio Devices], IPortClsVersion interface [Audio Devices], described, IPortClsVersion, portcls/IPortClsVersion, audmp-routines_47212df8-c1b8-4e77-bd5f-90b74a6ae08c.xml
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
-	IPortClsVersion
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsVersion interface


## -description


The <code>IPortClsVersion</code> interface is used by a miniport driver to identify the version of the Windows operating system that the driver is running on. The port driver implements this interface and exposes it to the miniport driver. 

To determine whether a port driver supports the <code>IPortClsVersion</code> interface, the miniport driver calls the port object's <b>QueryInterface</b> method with REFIID <b>IID_IPortClsVersion</b>. The following port types support <code>IPortClsVersion</code>:
<dl>
<dd>

<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a>


</dd>
<dd>

<a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a>


</dd>
<dd>

<a href="..\portcls\nn-portcls-iporttopology.md">IPortTopology</a>


</dd>
</dl>
