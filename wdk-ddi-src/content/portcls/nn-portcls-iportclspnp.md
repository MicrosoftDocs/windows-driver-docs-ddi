---
UID: NN:portcls.IPortClsPnp
title: IPortClsPnp
author: windows-driver-content
description: IPortClsPnp is the PnP management interface that the port class driver (PortCls) exposes to the adapter.
old-location: audio\iportclspnp.htm
old-project: audio
ms.assetid: AC04051E-8412-4B61-B452-C05A9D8D5CD9
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
req.alt-api: IPortClsPnp
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

# IPortClsPnp interface



## -description
<code>IPortClsPnp</code> is the PnP management interface that the port class driver (PortCls) exposes to the adapter.

For more information,  see <a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">Implement PnP Rebalance for PortCls Audio Drivers</a>.

The <code>IPortClsPnp</code> interface is available in Windows 10, version 1511 and later versions of Windows. 



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortClsPnp</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPortClsPnp</b> also has these types of members:

The <b>IPortClsPnp</b> interface has these methods.

The <code>RegisterAdapterPowerManagement</code> method registers the PnP management interface of the adapter with PortCls.

The <code>UnRegisterAdapterPowerManagement</code> method unregisters the PnP management interface of the adapter from PortCls.

 


## -members
The <b>IPortClsPnp</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/mt604860">IPortClsPnp::RegisterAdapterPnpManagement</a>
</td>
<td align="left" width="63%">
The <code>RegisterAdapterPowerManagement</code> method registers the PnP management interface of the adapter with PortCls.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/mt604861">IPortClsPnp::UnregisterAdapterPnpManagement</a>
</td>
<td align="left" width="63%">
The <code>UnRegisterAdapterPowerManagement</code> method unregisters the PnP management interface of the adapter from PortCls.

</td>
</tr>
</table>The <code>RegisterAdapterPowerManagement</code> method registers the PnP management interface of the adapter with PortCls.

The <code>UnRegisterAdapterPowerManagement</code> method unregisters the PnP management interface of the adapter from PortCls.

 


## -remarks
