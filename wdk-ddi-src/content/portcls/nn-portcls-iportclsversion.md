---
UID: NN:portcls.IPortClsVersion
title: IPortClsVersion
author: windows-driver-content
description: The IPortClsVersion interface is used by a miniport driver to identify the version of the Windows operating system that the driver is running on. The port driver implements this interface and exposes it to the miniport driver.
old-location: audio\iportclsversion.htm
old-project: audio
ms.assetid: 8a367bcb-680b-41be-975f-1a1f4bec3b60
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IPortClsVersion, IPortClsVersion interface [Audio Devices], IPortClsVersion interface [Audio Devices],described, audio.iportclsversion, audmp-routines_47212df8-c1b8-4e77-bd5f-90b74a6ae08c.xml, portcls/IPortClsVersion
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortClsVersion
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsVersion interface


## -description


The <code>IPortClsVersion</code> interface is used by a miniport driver to identify the version of the Windows operating system that the driver is running on. The port driver implements this interface and exposes it to the miniport driver. 

To determine whether a port driver supports the <code>IPortClsVersion</code> interface, the miniport driver calls the port object's <b>QueryInterface</b> method with REFIID <b>IID_IPortClsVersion</b>. The following port types support <code>IPortClsVersion</code>:
<dl>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536899">IPortWaveCyclic</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536879">IPortDMus</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536891">IPortMidi</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536896">IPortTopology</a>


</dd>
</dl>
