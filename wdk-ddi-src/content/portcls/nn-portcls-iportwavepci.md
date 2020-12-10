---
UID: NN:portcls.IPortWavePci
title: IPortWavePci (portcls.h)
description: The IPortWavePci interface is the WavePci port driver's primary interface.
old-location: audio\iportwavepci.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IPortWavePci interface"]
ms.keywords: IPortWavePci, IPortWavePci interface [Audio Devices], IPortWavePci interface [Audio Devices],described, audio.iportwavepci, audmp-routines_4948783a-44c9-42c3-ba67-c3c66a0a2951.xml, portcls/IPortWavePci
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
 - IPortWavePci
 - portcls/IPortWavePci
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IPortWavePci
---

# IPortWavePci interface


## -description

The <code>IPortWavePci</code> interface is the WavePci port driver's primary interface. The PortCls system driver implements this interface and exposes it to the adapter driver that implements the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavepci">IMiniportWavePci</a> object. The <code>IPortWavePci</code> interface provides notification and DMA services to the miniport object. An adapter driver creates an <code>IPortWavePci</code> object by calling <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewport">PcNewPort</a> and specifying REFIID <b>IID_IPortWavePci</b>. <code>IPortWavePci</code> inherits from the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <b>IMiniportWavePci</b> object to an <code>IPortWavePci</code> object. The PortCls system driver registers this pair with the system as a <a href="/windows-hardware/drivers/audio/wave-filters">wave filter</a>.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortWavePci</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPortWavePci</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>
