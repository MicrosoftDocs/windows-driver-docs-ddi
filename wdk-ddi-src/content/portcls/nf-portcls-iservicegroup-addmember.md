---
UID: NF:portcls.IServiceGroup.AddMember
title: IServiceGroup::AddMember (portcls.h)
description: The AddMember method adds a member to the service group.
old-location: audio\iservicegroup_addmember.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IServiceGroup::AddMember"]
ms.keywords: AddMember, AddMember method [Audio Devices], AddMember method [Audio Devices],IServiceGroup interface, IServiceGroup interface [Audio Devices],AddMember method, IServiceGroup.AddMember, IServiceGroup::AddMember, audio.iservicegroup_addmember, audmp-routines_0d318d56-28e9-4e42-84b3-1d0eb4110f71.xml, portcls/IServiceGroup::AddMember
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
 - IServiceGroup::AddMember
 - portcls/IServiceGroup::AddMember
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IServiceGroup::AddMember
---

# IServiceGroup::AddMember


## -description

The <code>AddMember</code> method adds a member to the service group.

## -parameters

### -param pServiceSink 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicesink">IServiceSink</a> interface of the new member of the service group

## -returns

<code>AddMember</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

The <code>AddMember</code> method calls <b>AddRef</b> on the <i>pServiceSink</i> object. When the object is later removed, the <b>RemoveMember</b> method calls <b>Release</b> on the <i>pServiceSink</i> object. This behavior is in accordance with the <a href="/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicesink">IServiceSink</a>

