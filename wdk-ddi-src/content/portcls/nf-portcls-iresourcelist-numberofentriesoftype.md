---
UID: NF:portcls.IResourceList.NumberOfEntriesOfType
title: IResourceList::NumberOfEntriesOfType (portcls.h)
description: The NumberOfEntriesOfType method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described.
old-location: audio\iresourcelist_numberofentriesoftype.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IResourceList::NumberOfEntriesOfType"]
ms.keywords: IResourceList interface [Audio Devices],NumberOfEntriesOfType method, IResourceList.NumberOfEntriesOfType, IResourceList::NumberOfEntriesOfType, NumberOfEntriesOfType, NumberOfEntriesOfType method [Audio Devices], NumberOfEntriesOfType method [Audio Devices],IResourceList interface, audio.iresourcelist_numberofentriesoftype, audmp-routines_eb0c6999-a901-4087-b7bc-12057f91be90.xml, portcls/IResourceList::NumberOfEntriesOfType
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
 - IResourceList::NumberOfEntriesOfType
 - portcls/IResourceList::NumberOfEntriesOfType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IResourceList::NumberOfEntriesOfType
---

# IResourceList::NumberOfEntriesOfType


## -description

The <code>NumberOfEntriesOfType</code> method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described.

## -parameters

### -param Type 

[in]
Identifies the resource type of the entries that are to be counted. For a list of valid resource-type values, see the <b>Type</b> member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.

## -returns

<code>NumberOfEntriesOfType</code> returns the number of items of the indicated type in the resource list.

## -remarks

For each resource type, a macro is defined to call this method. See <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>

