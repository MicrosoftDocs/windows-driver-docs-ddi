---
UID: NN:portcls.IUnregisterSubdevice
title: IUnregisterSubdevice (portcls.h)
description: The IUnregisterSubdevice interface implements a method to remove a registered subdevice.
old-location: audio\iunregistersubdevice.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IUnregisterSubdevice interface"]
ms.keywords: IUnregisterSubdevice, IUnregisterSubdevice interface [Audio Devices], IUnregisterSubdevice interface [Audio Devices],described, audio.iunregistersubdevice, audmp-routines_1af8aada-2816-4e82-abe4-579ba672866b.xml, portcls/IUnregisterSubdevice
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IUnregisterSubdevice
 - portcls/IUnregisterSubdevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IUnregisterSubdevice
---

# IUnregisterSubdevice interface


## -description

The <code>IUnregisterSubdevice</code> interface implements a method to remove a registered subdevice. The port driver implements this interface. To determine whether a port driver supports the <code>IUnregisterSubdevice</code> interface, a miniport driver calls the port driver object's <b>QueryInterface</b> method with REFIID <b>IID_IUnregisterSubdevice</b>. The miniport driver is responsible for releasing the <code>IUnregisterSubdevice</code> object after it is no longer needed. The <code>IUnregisterSubdevice</code> interface inherits from <b>IUnknown</b>.

The following port drivers support the <code>IUnregisterSubdevice</code> interface:
<ul>
<li>
WaveCyclic

</li>
<li>
WavePci

</li>
<li>
Topology

</li>
<li>
DMus

</li>
<li>
MIDI

</li>
</ul>The single method in this interface unregisters a subdevice that was previously registered by a call to the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregistersubdevice">PcRegisterSubdevice</a> routine. PortCls supports <b>PcRegisterSubdevice</b>.

The <code>IUnregisterSubdevice</code> object maintains its own internal reference to the subdevice to ensure that the corresponding device object is not deleted until all references to the <code>IUnregisterSubdevice</code> object are released.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IUnregisterSubdevice</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IUnregisterSubdevice</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>
