---
UID: NN:portcls.IUnregisterPhysicalConnection
title: IUnregisterPhysicalConnection
author: windows-driver-content
description: The IUnregisterPhysicalConnection interface implements three methods to remove a registered physical connection.
old-location: audio\iunregisterphysicalconnection.htm
old-project: audio
ms.assetid: 876a457e-8774-4c51-bd23-6451b3e3a7b7
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IUnregisterPhysicalConnection, IUnregisterPhysicalConnection interface [Audio Devices], IUnregisterPhysicalConnection interface [Audio Devices],described, audio.iunregisterphysicalconnection, audmp-routines_b26d005c-70d9-4df0-80ae-446907f22fd4.xml, portcls/IUnregisterPhysicalConnection
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IUnregisterPhysicalConnection
product: Windows
targetos: Windows
req.typenames: 
---

# IUnregisterPhysicalConnection interface


## -description


The <code>IUnregisterPhysicalConnection</code> interface implements three methods to remove a registered physical connection. The port driver implements this interface. To determine whether a port driver supports the <code>IUnregisterPhysicalConnection</code> interface, a miniport driver calls the port driver object's <b>QueryInterface</b> method with REFIID <b>IID_IUnregisterPhysicalConnection</b>. The miniport driver is responsible for releasing the <code>IUnregisterPhysicalConnection</code> object after it is no longer needed. The <code>IUnregisterPhysicalConnection</code> interface inherits from <b>IUnknown</b>.

The following port drivers support the <code>IUnregisterSubdevice</code> interface:
<ul>
<li>
WaveCyclic

</li>
<li>
WavePci

</li>
<li>
Topology

</li>
<li>
DMus

</li>
<li>
MIDI

</li>
</ul>The three methods in this interface "unregister" physical connections that were registered previously by calls to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537726">PcRegisterPhysicalConnection</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537728">PcRegisterPhysicalConnectionFromExternal</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff537729">PcRegisterPhysicalConnectionToExternal</a> routines. PortCls supports the three PcRegisterPhysicalConnection<i>Xxx</i> routines.

The port driver uses the information that it obtains from PcRegisterPhysicalConnection<i>Xxx</i> calls to respond to <a href="https://msdn.microsoft.com/library/windows/hardware/ff565205">KSPROPERTY_PIN_PHYSICALCONNECTION</a> property requests.

When deleting a subdevice from an adapter's topology, the driver must unregister the subdevice's physical connections to that portion of the topology. Failure to unregister the subdevice's physical connections can cause memory leaks.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IUnregisterPhysicalConnection</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IUnregisterPhysicalConnection</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IUnregisterPhysicalConnection</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537024">IUnregisterPhysicalConnection::UnregisterPhysicalConnection</a>
</td>
<td align="left" width="63%">
The <code>UnregisterPhysicalConnection</code> method deletes the registration of a physical connection that was registered by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537726">PcRegisterPhysicalConnection</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537027">IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal</a>
</td>
<td align="left" width="63%">
The <b>UnregisterPhysicalConnectionFromExternal</b> method deletes the registration of a physical connection that was registered by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537728">PcRegisterPhysicalConnectionFromExternal</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537029">IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal</a>
</td>
<td align="left" width="63%">
The <code>UnregisterPhysicalConnectionToExternal</code> method deletes the registration of a physical connection that was registered by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537729">PcRegisterPhysicalConnectionToExternal</a>.

</td>
</tr>
</table> 

