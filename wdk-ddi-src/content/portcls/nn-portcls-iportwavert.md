---
UID: NN:portcls.IPortWaveRT
title: IPortWaveRT
author: windows-driver-content
description: The IPortWaveRT interface is supported in Windows Vista and later operating systems and it is the main interface that the WaveRT port driver exposes to the adapter driver that implements the WaveRT miniport driver object.
old-location: audio\iportwavert.htm
old-project: audio
ms.assetid: ba54320e-42b3-489c-a192-dce794c3b3d4
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.iportwavert, IPortWaveRT interface [Audio Devices], IPortWaveRT interface [Audio Devices], described, IPortWaveRT, portcls/IPortWaveRT, audmp-routines_0c88b444-3414-49e0-a021-2bc4cd6f1fff.xml
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
-	IPortWaveRT
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IPortWaveRT interface


## -description


The <code>IPortWaveRT</code> interface is supported in Windows Vista and later operating systems and it is the main interface that the WaveRT port driver exposes to the adapter driver that implements the WaveRT miniport driver object.

 To create an <code>IPortWaveRT</code> object, the adapter driver calls <a href="..\portcls\nf-portcls-pcnewport.md">PcNewPort</a> and specifies <b>IID_IPortWaveRT</b> as the REFIID. The GUID constant <b>IID_IPortWaveRT</b> is defined in header file Portcls.h.

An adapter driver forms a port-miniport driver pair by binding an <code>IPortWaveRT</code> object to an <a href="..\portcls\nn-portcls-iminiportwavert.md">IMiniportWaveRT</a> object. The PortCls system driver registers the pair with the system as a wave filter.

<code>IPortWaveRT</code> inherits the methods in the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface; it provides no additional methods.

The <a href="..\portcls\nn-portcls-iportwavertstream.md">IPortWaveRTStream</a> interface is supported in Windows Vista and later operating systems, and it is a stream-specific interface that provides helper methods for use by the WaveRT miniport driver.

