---
UID: NN:dmusicks.ISynthSinkDMus
title: ISynthSinkDMus (dmusicks.h)
description: The ISynthSinkDMus interface handles wave output for a DirectMusic synthesizer device.
old-location: audio\isynthsinkdmus.htm
tech.root: audio
ms.assetid: 3bff4242-3e7b-424e-ac86-121267a2c32a
ms.date: 05/08/2018
keywords: ["ISynthSinkDMus interface"]
ms.keywords: ISynthSinkDMus, ISynthSinkDMus interface [Audio Devices], ISynthSinkDMus interface [Audio Devices],described, audio.isynthsinkdmus, audmp-routines_744ae6c7-7f7e-4a66-9624-5a5d82e2eb86.xml, dmusicks/ISynthSinkDMus
req.header: dmusicks.h
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
 - ISynthSinkDMus
 - dmusicks/ISynthSinkDMus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dmusicks.h
api_name:
 - ISynthSinkDMus
---

# ISynthSinkDMus interface


## -description

The <code>ISynthSinkDMus</code> interface handles wave output for a DirectMusic synthesizer device. The DMus miniport driver provides this interface for use by the wave sink, which calls the methods in the interface to render wave output and to synchronize its sample clock to the master clock. As explained in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/synthesizer-miniport-driver-overview">Synthesizer Miniport Driver Overview</a>, the wave sink is implemented in the DMus port driver. To determine whether a DMus miniport driver supports the <code>ISynthSinkDMus</code> interface, the DMus port driver calls the miniport driver stream object's <b>IMXF::QueryInterface</b> method with REFIID <b>IID_ISynthSinkDMus</b>. <code>ISynthSinkDMus</code> inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nn-dmusicks-imxf">IMXF</a> interface.

The <code>ISynthSinkDMus</code> interface provides methods to render, convert sample to reference time, convert reference to sample time, and synchronize to the master clock. For information about the use of the <code>ISynthSinkDMus</code> interface, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/a-wave-sink-for-kernel-mode-software-synthesizers">A Wave Sink for Kernel-Mode Software Synthesizers</a>.

