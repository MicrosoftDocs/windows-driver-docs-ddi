---
UID: NN:portcls.IPortWMIRegistration
title: IPortWMIRegistration
author: windows-driver-content
description: The IPortWMIRegistration interface is provided in Windows 7 and later versions of Windows. This interface allows the miniport driver to coordinate Event Tracing for Windows (ETW) registration between PortCls and the miniport driver.
old-location: audio\iportwmiregistration.htm
old-project: audio
ms.assetid: 0fb18e82-4853-459f-b8d3-4841ca3d8301
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.iportwmiregistration, IPortWMIRegistration interface [Audio Devices], IPortWMIRegistration interface [Audio Devices], described, IPortWMIRegistration, portcls/IPortWMIRegistration, audmp-routines_c7591b25-80f3-4d0e-ac6b-bc1dea55adb1.xml
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
-	IPortWMIRegistration
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IPortWMIRegistration interface


## -description


The <code>IPortWMIRegistration</code> interface is provided in Windows 7 and later versions of Windows. This interface allows the miniport driver to coordinate Event Tracing for Windows (ETW) registration between PortCls and the miniport driver.

ETW provides a mechanism to trace and log events that are raised by user-mode applications and kernel-mode drivers. For more information about ETW, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=154129">Improve Debugging And Performance Tuning With ETW</a>.


## -members

The <b>IPortWMIRegistration</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536937">IPortWMIRegistration::RegisterWMIProvider</a>
</td>
<td align="left" width="63%">
The <code>RegisterWMIProvider</code> method registers the <a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a> (ETW) capability of the miniport driver with PortCls.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536940">IPortWMIRegistration::UnregisterWMIProvider</a>
</td>
<td align="left" width="63%">
The <code>UnregisterWMIProvider</code> method unregisters the <a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a> (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls.

</td>
</tr>
</table>The <code>RegisterWMIProvider</code> method registers the <a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a> (ETW) capability of the miniport driver with PortCls.

The <code>UnregisterWMIProvider</code> method unregisters the <a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a> (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls.

 

