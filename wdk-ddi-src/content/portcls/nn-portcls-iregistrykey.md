---
UID: NN:portcls.IRegistryKey
title: IRegistryKey (portcls.h)
description: The IRegistryKey interface provides an abstraction of a registry key that a miniport driver can use to access the key and its subkeys.
old-location: audio\iregistrykey.htm
tech.root: audio
ms.assetid: 41601234-7b8e-4d53-9455-626a5a3c4ff3
ms.date: 05/08/2018
ms.keywords: IRegistryKey, IRegistryKey interface [Audio Devices], IRegistryKey interface [Audio Devices],described, audio.iregistrykey, audmp-routines_40bea095-17f2-4b5f-96e8-ab2fed6d82d4.xml, portcls/IRegistryKey
ms.topic: interface
f1_keywords:
 - "portcls/IRegistryKey"
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
- IRegistryKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# IRegistryKey interface


## -description


The <code>IRegistryKey</code> interface provides an abstraction of a registry key that a miniport driver can use to access the key and its subkeys. The PortCls system driver implements this interface and exposes it to miniport drivers. A miniport driver obtains a reference to an <code>IRegistryKey</code> object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewregistrykey">PcNewRegistryKey</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-newregistrykey">IPort::NewRegistryKey</a>. 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/registry-key-objects">Registry Key Objects</a>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IRegistryKey</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IRegistryKey</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

