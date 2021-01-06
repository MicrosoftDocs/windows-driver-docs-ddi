---
UID: NN:portcls.IMiniportWaveRT
title: IMiniportWaveRT (portcls.h)
description: The IMiniportWaveRT interface is the primary interface that is exposed by the miniport driver for a WaveRT audio device.
old-location: audio\iminiportwavert.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportWaveRT interface"]
ms.keywords: IMiniportWaveRT, IMiniportWaveRT interface [Audio Devices], IMiniportWaveRT interface [Audio Devices],described, audio.iminiportwavert, audmp-routines_8d8d9bf9-09f1-4c1f-9113-c03e506e4edb.xml, portcls/IMiniportWaveRT
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
 - IMiniportWaveRT
 - portcls/IMiniportWaveRT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRT
---

# IMiniportWaveRT interface


## -description

The <code>IMiniportWaveRT</code> interface is the primary interface that is exposed by the miniport driver for a WaveRT audio device. The adapter driver creates the WaveRT miniport driver object. It then passes the <code>IMiniportWaveRT</code> interface pointer of the object to the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init </a> method of the WaveRT port driver. <code>IMiniportWaveRT</code> inherits from the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiport">IMiniport</a> interface.

An adapter driver forms a miniport-port driver pair by binding an <code>IMiniportWaveRT</code> object to an <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavert">IPortWaveRT</a> object. The PortCls system driver registers this pair with the system as a wave filter.

<code>IMiniportWaveRT</code> is supported in Windows Vista and later Windows operating systems.
