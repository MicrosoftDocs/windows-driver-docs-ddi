---
UID: NN:portcls.IMiniportWavePci
title: IMiniportWavePci
author: windows-driver-content
description: The IMiniportWavePci interface is the primary interface that is exposed by the miniport driver for a WavePci audio device.
old-location: audio\iminiportwavepci.htm
old-project: audio
ms.assetid: 74619f9b-cd67-47f2-8c67-6fb42b794b9a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IMiniportWavePci, IMiniportWavePci interface [Audio Devices], IMiniportWavePci interface [Audio Devices],described, audio.iminiportwavepci, audmp-routines_bd4a9d9c-d3eb-40bc-93d9-277abe4ee258.xml, portcls/IMiniportWavePci
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWavePci
product: Windows
targetos: Windows
req.typenames: 
---

# IMiniportWavePci interface


## -description


The <code>IMiniportWavePci</code> interface is the primary interface that is exposed by the miniport driver for a WavePci audio device. The WavePci port driver communicates with the miniport driver through this interface. The adapter driver creates the WavePci miniport object and passes the object's <b>IMiniportPci</b> interface pointer to the WavePci port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> method (see code example in <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>). <code>IMiniportWavePci</code> inherits from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536698">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportWavePci</code> object to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a> object. The PortCls system driver registers this pair with the system as a <a href="https://msdn.microsoft.com/9e364c8f-55c3-4ec9-a9ce-9ee0f6a0746b">wave filter</a>.

The <code>IMiniportWavePci</code> interface provides a method for initializing the miniport object, a method for creating a miniport stream object, and a method for notifying the miniport driver of a service request. The stream object is associated with a pin on the WavePci filter, which the adapter driver forms by binding the miniport object with the port object.

