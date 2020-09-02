---
UID: NN:portcls.IServiceSink
title: IServiceSink (portcls.h)
description: The IServiceSink interface encapsulates handling of a service request.
old-location: audio\iservicesink.htm
tech.root: audio
ms.assetid: 329ae226-02fb-438b-b461-da51e3afd6eb
ms.date: 05/08/2018
keywords: ["IServiceSink interface"]
ms.keywords: IServiceSink, IServiceSink interface [Audio Devices], IServiceSink interface [Audio Devices],described, audio.iservicesink, audmp-routines_68a03e77-6246-44e7-acad-6de0fbe10c41.xml, portcls/IServiceSink
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IServiceSink
 - portcls/IServiceSink
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IServiceSink
---

# IServiceSink interface


## -description

The <code>IServiceSink</code> interface encapsulates handling of a service request. The source of the service request is typically the miniport driver's interrupt service routine. PortCls supports the <code>IServiceSink</code> interface. An <code>IServiceSink</code> object is typically a member of a service group that is managed by an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a> object. <code>IServiceSink</code> inherits from the <b>IUnknown</b> interface.

<code>IServiceSink</code> is the base interface for <b>IServiceGroup</b>. This allows an <b>IServiceGroup</b> object to add itself (as an object with an <code>IServiceSink</code> interface) to another <b>IServiceGroup</b> object's service group.

Although the PortCls system driver provides a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewservicegroup">PcNewServiceGroup</a> function for creating a service group object, no similar function exists for creating a service sink object. Instead, a driver object that requires a service sink simply implements an <code>IServiceSink</code> interface in the driver object. For convenience, header file portcls.h includes an <b>IMP_IServiceSink</b> constant for adding the <code>IServiceSink</code> implementation to the object's class definition. The cost of adding an <code>IServiceSink</code> interface to an object is small because the interface supports only a single method. A port driver typically adds an <code>IServiceSink</code> interface to its port object and stream objects so that they can receive notification of interrupts from an audio device.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/service-sink-and-service-group-objects">Service Sink and Service Group Objects</a>.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IServiceSink</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IServiceSink</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

