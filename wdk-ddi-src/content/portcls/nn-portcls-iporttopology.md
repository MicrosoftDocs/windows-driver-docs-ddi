---
UID: NN:portcls.IPortTopology
title: IPortTopology
author: windows-driver-content
description: The IPortTopology interface provides generic port driver support to a topology miniport driver.
old-location: audio\iporttopology.htm
old-project: audio
ms.assetid: 820b00e8-a917-4bef-ac36-e8103f59d998
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.iporttopology, IPortTopology interface [Audio Devices], IPortTopology interface [Audio Devices], described, IPortTopology, portcls/IPortTopology, audmp-routines_88974b5c-4520-41ed-b0c7-75cceff72e0f.xml
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
-	IPortTopology
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortTopology interface


## -description


The <code>IPortTopology</code> interface provides generic port driver support to a topology miniport driver. The PortCls system driver implements this interface and exposes it to the adapter driver that implements the <a href="..\portcls\nn-portcls-iminiporttopology.md">IMiniportTopology</a> object. An adapter driver creates an <code>IPortTopology</code> object by calling <a href="..\portcls\nf-portcls-pcnewport.md">PcNewPort</a> and specifying REFIID <b>IID_IPortTopology</b>. <code>IPortTopology</code> inherits from the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <b>IMiniportTopology</b> object to an <code>IPortTopology</code> object. The PortCls system driver registers this pair with the system as a <a href="https://msdn.microsoft.com/1b3d35e9-5858-407c-9cd0-06307d82ce58">topology filter</a>.

The <code>IPortTopology</code> interface supports only the methods that it inherits from the <b>IPort</b> interface.

