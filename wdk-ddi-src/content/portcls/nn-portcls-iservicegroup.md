---
UID: NN:portcls.IServiceGroup
title: IServiceGroup (portcls.h)
description: The IServiceGroup interface encapsulates a group of objects that all require notification of the same service request.
old-location: audio\iservicegroup.htm
tech.root: audio
ms.assetid: eef2741e-e1a3-471b-a756-d89990929738
ms.date: 09/17/2018
ms.keywords: IServiceGroup, IServiceGroup interface [Audio Devices], IServiceGroup interface [Audio Devices],described, audio.iservicegroup, audmp-routines_10cfd005-be11-47a2-a929-f338f40e6f79.xml, portcls/IServiceGroup
ms.topic: interface
f1_keywords:
 - "portcls/IServiceGroup"
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
- IServiceGroup
product:
- Windows
targetos: Windows
req.typenames: 
---

# IServiceGroup interface


## -description


The <code>IServiceGroup</code> interface encapsulates a group of objects that all require notification of the same service request. When the service group object receives notification of the request, it forwards the notification to each of the objects in the group. The PortCls system driver implements the <code>IServiceGroup</code> interface and exposes it to miniport drivers. A miniport driver creates an <code>IServiceGroup</code> object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewservicegroup">PcNewServiceGroup</a>. <code>IServiceGroup</code> inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicesink">IServiceSink</a> interface.

Port drivers typically use service group objects to demultiplex requests for interrupt service, although the functionality of a service group is general enough to make it potentially useful for other purposes as well. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/service-sink-and-service-group-objects">Service Sink and Service Group Objects</a>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IServiceGroup</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IServiceGroup</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

