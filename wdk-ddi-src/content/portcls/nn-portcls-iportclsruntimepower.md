---
UID: NN:portcls.IPortClsRuntimePower
title: IPortClsRuntimePower
author: windows-driver-content
description: IPortClsRuntimePower is the interface that the port class driver (PortCls) uses for accessing the runtime power management capabilities of the audio adapter.
old-location: audio\iportclsruntimepower.htm
tech.root: audio
ms.assetid: 8D03B2A0-6C8C-4EBE-86F4-70C8DE179947
ms.date: 05/08/2018
ms.keywords: IPortClsRuntimePower, IPortClsRuntimePower interface [Audio Devices], IPortClsRuntimePower interface [Audio Devices],described, audio.iportclsruntimepower, portcls/IPortClsRuntimePower
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
-	IPortClsRuntimePower
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsRuntimePower interface


## -description


IPortClsRuntimePower is the interface that the port class driver (PortCls)  uses for accessing the runtime power management capabilities of the audio adapter.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortClsRuntimePower</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPortClsRuntimePower</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPortClsRuntimePower</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265126">RegisterPowerControlCallback</a>
</td>
<td align="left" width="63%">
The port class driver (PortCls) uses the <code>RegisterPowerControlCallback</code>  method to register a power control callback.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265127">SendPowerControl</a>
</td>
<td align="left" width="63%">
The port class driver (PortCls) uses the <code>SendPowerControl</code>  method to send power control codes to the audio adapter.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265128">UnregisterPowerControlCallback</a>
</td>
<td align="left" width="63%">
The port class driver (PortCls) uses the <code>UnregisterPowerControlCallback</code>  method to unregister a power control callback.

</td>
</tr>
</table> 

