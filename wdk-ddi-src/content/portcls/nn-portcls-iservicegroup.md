---
UID: NN:portcls.IServiceGroup
title: IServiceGroup
author: windows-driver-content
description: The IServiceGroup interface encapsulates a group of objects that all require notification of the same service request.
old-location: audio\iservicegroup.htm
old-project: audio
ms.assetid: eef2741e-e1a3-471b-a756-d89990929738
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.iservicegroup, IServiceGroup interface [Audio Devices], IServiceGroup interface [Audio Devices], described, IServiceGroup, portcls/IServiceGroup, audmp-routines_10cfd005-be11-47a2-a929-f338f40e6f79.xml
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
-	IServiceGroup
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IServiceGroup interface


## -description


The <code>IServiceGroup</code> interface encapsulates a group of objects that all require notification of the same service request. When the service group object receives notification of the request, it forwards the notification to each of the objects in the group. The PortCls system driver implements the <code>IServiceGroup</code> interface and exposes it to miniport drivers. A miniport driver creates an <code>IServiceGroup</code> object by calling <a href="..\portcls\nf-portcls-pcnewservicegroup.md">PcNewServiceGroup</a>. <code>IServiceGroup</code> inherits from the <a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a> interface.

Port drivers typically use service group objects to demultiplex requests for interrupt service, although the functionality of a service group is general enough to make it potentially useful for other purposes as well. For more information, see <a href="https://msdn.microsoft.com/00e17e01-8889-4fae-a0ff-e110d7a9b21e">Service Sink and Service Group Objects</a>.


## -members

The <b>IServiceGroup</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536996">IServiceGroup::AddMember</a>
</td>
<td align="left" width="63%">
The <code>AddMember</code> method adds a member to the service group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536997">IServiceGroup::CancelDelayedService</a>
</td>
<td align="left" width="63%">
The <code>CancelDelayedService</code> method cancels the previously requested delayed service.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537001">IServiceGroup::RemoveMember</a>
</td>
<td align="left" width="63%">
The <code>RemoveMember</code> method removes the specified member from the service group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537003">IServiceGroup::RequestDelayedService</a>
</td>
<td align="left" width="63%">
The <code>RequestDelayedService</code> method requests service after the specified delay.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537004">IServiceGroup::SupportDelayedService</a>
</td>
<td align="left" width="63%">
The <code>SupportDelayedService</code> method indicates that the service group should prepare to support delayed service.

</td>
</tr>
</table>The <code>AddMember</code> method adds a member to the service group.

The <code>CancelDelayedService</code> method cancels the previously requested delayed service.

The <code>RemoveMember</code> method removes the specified member from the service group.

The <code>RequestDelayedService</code> method requests service after the specified delay.

The <code>SupportDelayedService</code> method indicates that the service group should prepare to support delayed service.

 

