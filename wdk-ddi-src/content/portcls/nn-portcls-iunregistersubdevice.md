---
UID: NN:portcls.IUnregisterSubdevice
title: IUnregisterSubdevice
author: windows-driver-content
description: The IUnregisterSubdevice interface implements a method to remove a registered subdevice.
old-location: audio\iunregistersubdevice.htm
old-project: audio
ms.assetid: 023b0a03-a572-459b-a1eb-b25fcde6ecc5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcUnregisterIoTimeout
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
req.alt-api: IUnregisterSubdevice
req.alt-loc: portcls.h
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
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IUnregisterSubdevice interface



## -description
The <code>IUnregisterSubdevice</code> interface implements a method to remove a registered subdevice. The port driver implements this interface. To determine whether a port driver supports the <code>IUnregisterSubdevice</code> interface, a miniport driver calls the port driver object's <b>QueryInterface</b> method with REFIID <b>IID_IUnregisterSubdevice</b>. The miniport driver is responsible for releasing the <code>IUnregisterSubdevice</code> object after it is no longer needed. The <code>IUnregisterSubdevice</code> interface inherits from <b>IUnknown</b>.

The following port drivers support the <code>IUnregisterSubdevice</code> interface:

WaveCyclic

WavePci

Topology

DMus

MIDI

The single method in this interface unregisters a subdevice that was previously registered by a call to the <a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a> routine. PortCls supports <b>PcRegisterSubdevice</b>.

The <code>IUnregisterSubdevice</code> object maintains its own internal reference to the subdevice to ensure that the corresponding device object is not deleted until all references to the <code>IUnregisterSubdevice</code> object are released.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IUnregisterSubdevice</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IUnregisterSubdevice</b> also has these types of members:

The <b>IUnregisterSubdevice</b> interface has these methods.

The <b>UnregisterSubdevice</b> method deletes the registration of a subdevice that was previously registered by a call to <a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a>.

 


## -members
The <b>IUnregisterSubdevice</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537032">IUnregisterSubdevice::UnregisterSubdevice</a>
</td>
<td align="left" width="63%">
The <b>UnregisterSubdevice</b> method deletes the registration of a subdevice that was previously registered by a call to <a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a>.

</td>
</tr>
</table>The <b>UnregisterSubdevice</b> method deletes the registration of a subdevice that was previously registered by a call to <a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a>.

 


## -remarks
