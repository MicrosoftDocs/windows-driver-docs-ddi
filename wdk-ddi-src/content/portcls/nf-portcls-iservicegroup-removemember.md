---
UID: NF:portcls.IServiceGroup.RemoveMember
title: IServiceGroup::RemoveMember (portcls.h)
description: The RemoveMember method removes the specified member from the service group.
old-location: audio\iservicegroup_removemember.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IServiceGroup::RemoveMember"]
ms.keywords: IServiceGroup interface [Audio Devices],RemoveMember method, IServiceGroup.RemoveMember, IServiceGroup::RemoveMember, RemoveMember, RemoveMember method [Audio Devices], RemoveMember method [Audio Devices],IServiceGroup interface, audio.iservicegroup_removemember, audmp-routines_0b3fd59f-9233-4344-aa0c-f58505eee693.xml, portcls/IServiceGroup::RemoveMember
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IServiceGroup::RemoveMember
 - portcls/IServiceGroup::RemoveMember
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IServiceGroup::RemoveMember
---

# IServiceGroup::RemoveMember


## -description

The <code>RemoveMember</code> method removes the specified member from the service group.

## -parameters

### -param pServiceSink [in]


Pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicesink">IServiceSink</a> interface of the member that is to be removed

## -remarks

The <code>RemoveMember</code> method removes a service sink that was previously added to the service group by an <b>AddMember</b> call. The <b>AddMember</b> method called <b>AddRef</b> on the service sink object, and the <code>RemoveMember</code> method calls <b>Release</b> on the service sink object. This behavior is in accordance with the <a href="/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicesink">IServiceSink</a>

