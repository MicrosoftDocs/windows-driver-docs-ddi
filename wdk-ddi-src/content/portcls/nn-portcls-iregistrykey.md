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

## -members

The <b>IRegistryKey</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iregistrykey-deletekey">IRegistryKey::DeleteKey</a>
</td>
<td align="left" width="63%">
The <code>DeleteKey</code> method deletes the registry key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iregistrykey-enumeratekey">IRegistryKey::EnumerateKey</a>
</td>
<td align="left" width="63%">
The <code>EnumerateKey</code> method returns information about the subkeys of the open key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iregistrykey-enumeratevaluekey">IRegistryKey::EnumerateValueKey</a>
</td>
<td align="left" width="63%">
The <code>EnumerateValueKey</code> method returns information about a registry entry that contains a value key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iregistrykey-newsubkey">IRegistryKey::NewSubKey</a>
</td>
<td align="left" width="63%">
The <code>NewSubKey</code> method either creates a new registry subkey or opens an existing subkey under the key represented by the <b>IRegistryKey</b> object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iregistrykey-querykey">IRegistryKey::QueryKey</a>
</td>
<td align="left" width="63%">
The <code>QueryKey</code> method retrieves information about a registry key, including the key name, key class, and the number of subkeys and their sizes.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iregistrykey-queryregistryvalues">IRegistryKey::QueryRegistryValues</a>
</td>
<td align="left" width="63%">
The <code>QueryRegistryValues</code> method allows the caller to query several values from the registry with a single call.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iregistrykey-queryvaluekey">IRegistryKey::QueryValueKey</a>
</td>
<td align="left" width="63%">
The <code>QueryValueKey</code> method retrieves information about a registry key's value entries, including their names, types, data sizes, and values.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iregistrykey-setvaluekey">IRegistryKey::SetValueKey</a>
</td>
<td align="left" width="63%">
The <code>SetValueKey</code> method replaces or creates a value entry under the open key.

</td>
</tr>
</table> 

