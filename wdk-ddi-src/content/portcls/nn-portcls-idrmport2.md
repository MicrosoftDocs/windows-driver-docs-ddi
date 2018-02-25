---
UID: NN:portcls.IDrmPort2
title: IDrmPort2
author: windows-driver-content
description: The IDrmPort2 interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see Digital Rights Management).
old-location: audio\idrmport2.htm
old-project: audio
ms.assetid: c0fa64cf-bfc7-415c-a30d-50bf6182cc3d
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IDrmPort2, IDrmPort2 interface [Audio Devices], IDrmPort2 interface [Audio Devices], described, audio.idrmport2, audmp-routines_93a46344-36f2-49ea-9091-93b4e810f195.xml, portcls/IDrmPort2
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
-	IDrmPort2
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IDrmPort2 interface


## -description


The <code>IDrmPort2</code> interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see <a href="https://msdn.microsoft.com/7ce19196-5180-421f-b6be-ac4a235a8c16">Digital Rights Management</a>). The port driver implements this interface and exposes it to the miniport driver. The WaveCyclic and WavePci port drivers support this interface. To determine whether a port driver supports the <code>IDrmPort2</code> interface, a miniport driver calls the port (<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a> or <a href="..\portcls\nn-portcls-iportwavepci.md">IPortWavePci</a>) object's <b>QueryInterface</b> method with REFIID <b>IID_IDrmPort2</b>. <code>IDrmPort2</code> inherits from the <a href="..\portcls\nn-portcls-idrmport.md">IDrmPort</a> interface.

The methods in this interface serve as alternate entry points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536356">DRM functions</a> in the <a href="https://msdn.microsoft.com/827997e2-6f07-4635-ac35-4ad026b82eae">DRMK system driver</a>, drmk.sys.

For more information about <code>IDrmPort2</code>, see <a href="https://msdn.microsoft.com/aee123e4-bc1b-4ba8-9f8d-a9d207297c8d">Content IDs and Content Rights</a>.

