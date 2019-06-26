---
UID: NN:portcls.IDrmPort2
title: IDrmPort2 (portcls.h)
description: The IDrmPort2 interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see Digital Rights Management).
old-location: audio\idrmport2.htm
tech.root: audio
ms.assetid: c0fa64cf-bfc7-415c-a30d-50bf6182cc3d
ms.date: 05/08/2018
ms.keywords: IDrmPort2, IDrmPort2 interface [Audio Devices], IDrmPort2 interface [Audio Devices],described, audio.idrmport2, audmp-routines_93a46344-36f2-49ea-9091-93b4e810f195.xml, portcls/IDrmPort2
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IDrmPort2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDrmPort2 interface


## -description


The <code>IDrmPort2</code> interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/digital-rights-management">Digital Rights Management</a>). The port driver implements this interface and exposes it to the miniport driver. The WaveCyclic and WavePci port drivers support this interface. To determine whether a port driver supports the <code>IDrmPort2</code> interface, a miniport driver calls the port (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportwavecyclic">IPortWaveCyclic</a> or <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff536905(v=vs.85)">IPortWavePci</a>) object's <b>QueryInterface</b> method with REFIID <b>IID_IDrmPort2</b>. <code>IDrmPort2</code> inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-idrmport">IDrmPort</a> interface.

The methods in this interface serve as alternate entry points to the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/drm-functions">DRM functions</a> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/kernel-mode-wdm-audio-components">DRMK system driver</a>, drmk.sys.

For more information about <code>IDrmPort2</code>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/content-ids-and-content-rights">Content IDs and Content Rights</a>.

