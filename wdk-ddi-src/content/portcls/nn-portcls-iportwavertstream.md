---
UID: NN:portcls.IPortWaveRTStream
title: IPortWaveRTStream (portcls.h)
description: The IPortWaveRTStream interface is supported in Windows Vista and later operating systems, and it is a stream-specific interface that provides helper methods for use by the WaveRT miniport driver.
old-location: audio\iportwavertstream.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IPortWaveRTStream interface"]
ms.keywords: IPortWaveRTStream, IPortWaveRTStream interface [Audio Devices], IPortWaveRTStream interface [Audio Devices],described, audio.iportwavertstream, audmp-routines_485f04fa-bdd1-4b92-bb3b-4f8653393811.xml, portcls/IPortWaveRTStream
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
 - IPortWaveRTStream
 - portcls/IPortWaveRTStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IPortWaveRTStream
---

# IPortWaveRTStream interface


## -description

The <code>IPortWaveRTStream</code> interface is supported in Windows Vista and later operating systems, and it is a stream-specific interface that provides helper methods for use by the <a href="/windows-hardware/drivers/audio/wavert-miniport-driver">WaveRT miniport driver</a>. The miniport driver calls the methods to perform allocation and mapping of cyclic buffers for audio data. The WaveRT port driver implements this interface. The port driver gives an <code>IPortWaveRTStream</code> object reference to each miniport driver stream object that it creates. <code>IPortWaveRTStream</code> inherits from the <b>IUnknown</b> interface.

An audio stream is associated with each pin instance on a WaveRT filter. The adapter driver forms the filter by binding the WaveRT port and miniport drivers. When the port driver calls the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavert-newstream">IMiniportWaveRT::NewStream </a> method to create the miniport driver stream object, the port driver passes an <code>IPortWaveRTStream</code> reference as one of the method's call parameters.

To allocate the memory needed for the cyclic buffer, the miniport driver must call the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatepagesformdl">AllocatePagesForMdl</a> method or the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavertstream-allocatecontiguouspagesformdl">AllocateContiguousPagesForMdl</a> method of the <code>IPortWaveRTStream</code> interface. The interface provides additional methods that can map the allocated pages, unmap them, and can also free them.

The methods in the <code>IPortWaveRTStream</code> interface are based on, and are similar to, the MmXxx kernel functions that perform allocation and mapping of memory descriptor lists (<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDLs</a>). However, the MmXxx functions cannot be used in place of the <code>IPortWaveRTStream</code> methods.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortWaveRTStream</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPortWaveRTStream</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>
