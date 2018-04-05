---
UID: NN:portcls.IRegistryKey
title: IRegistryKey
author: windows-driver-content
description: The IRegistryKey interface provides an abstraction of a registry key that a miniport driver can use to access the key and its subkeys.
old-location: audio\iregistrykey.htm
old-project: audio
ms.assetid: 41601234-7b8e-4d53-9455-626a5a3c4ff3
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IRegistryKey, IRegistryKey interface [Audio Devices], IRegistryKey interface [Audio Devices], described, audio.iregistrykey, audmp-routines_40bea095-17f2-4b5f-96e8-ab2fed6d82d4.xml, portcls/IRegistryKey
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IRegistryKey
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IRegistryKey interface


## -description


The <code>IRegistryKey</code> interface provides an abstraction of a registry key that a miniport driver can use to access the key and its subkeys. The PortCls system driver implements this interface and exposes it to miniport drivers. A miniport driver obtains a reference to an <code>IRegistryKey</code> object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff537716">PcNewRegistryKey</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536945">IPort::NewRegistryKey</a>. 

For more information, see <a href="https://msdn.microsoft.com/c666f0cc-5a8a-4df8-9c65-08e3b044a08f">Registry Key Objects</a>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IRegistryKey</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IRegistryKey</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536967">IRegistryKey::DeleteKey</a>
</td>
<td align="left" width="63%">
The <code>DeleteKey</code> method deletes the registry key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536968">IRegistryKey::EnumerateKey</a>
</td>
<td align="left" width="63%">
The <code>EnumerateKey</code> method returns information about the subkeys of the open key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536969">IRegistryKey::EnumerateValueKey</a>
</td>
<td align="left" width="63%">
The <code>EnumerateValueKey</code> method returns information about a registry entry that contains a value key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536970">IRegistryKey::NewSubKey</a>
</td>
<td align="left" width="63%">
The <code>NewSubKey</code> method either creates a new registry subkey or opens an existing subkey under the key represented by the <b>IRegistryKey</b> object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536971">IRegistryKey::QueryKey</a>
</td>
<td align="left" width="63%">
The <code>QueryKey</code> method retrieves information about a registry key, including the key name, key class, and the number of subkeys and their sizes.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536972">IRegistryKey::QueryRegistryValues</a>
</td>
<td align="left" width="63%">
The <code>QueryRegistryValues</code> method allows the caller to query several values from the registry with a single call.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536973">IRegistryKey::QueryValueKey</a>
</td>
<td align="left" width="63%">
The <code>QueryValueKey</code> method retrieves information about a registry key's value entries, including their names, types, data sizes, and values.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536975">IRegistryKey::SetValueKey</a>
</td>
<td align="left" width="63%">
The <code>SetValueKey</code> method replaces or creates a value entry under the open key.

</td>
</tr>
</table> 

