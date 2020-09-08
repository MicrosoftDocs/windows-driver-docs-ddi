---
UID: NF:portcls.IResourceList.FindUntranslatedEntry
title: IResourceList::FindUntranslatedEntry (portcls.h)
description: The FindUntranslatedEntry method returns a pointer to an untranslated entry of the specified type, or NULL if no such pointer is found.
old-location: audio\iresourcelist_finduntranslatedentry.htm
tech.root: audio
ms.assetid: 3578eb3a-e9c8-4de3-b959-daff9ac7f1a2
ms.date: 05/08/2018
keywords: ["IResourceList::FindUntranslatedEntry"]
ms.keywords: FindUntranslatedEntry, FindUntranslatedEntry method [Audio Devices], FindUntranslatedEntry method [Audio Devices],IResourceList interface, IResourceList interface [Audio Devices],FindUntranslatedEntry method, IResourceList.FindUntranslatedEntry, IResourceList::FindUntranslatedEntry, audio.iresourcelist_finduntranslatedentry, audmp-routines_d9b98845-63dd-454d-b1de-dd7db8825e27.xml, portcls/IResourceList::FindUntranslatedEntry
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
 - IResourceList::FindUntranslatedEntry
 - portcls/IResourceList::FindUntranslatedEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IResourceList.FindUntranslatedEntry
---

# IResourceList::FindUntranslatedEntry


## -description

The <code>FindUntranslatedEntry</code> method returns a pointer to an untranslated entry of the specified type, or <b>NULL</b> if no such pointer is found.

## -parameters

### -param Type 

[in]
Identifies the resource type of the entries that are to be counted. For a list of valid values, see the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.

### -param Index 

[in]
Specifies the index of the entry to find. If the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iresourcelist-numberofentriesoftype">IResourceList::NumberOfEntriesOfType</a> method returns a value <i>n</i> for the number of entries of type <i>Type</i>, valid indices range from 0 to <i>n</i>-1. If <i>Index</i> is zero, for example, the method returns a pointer to the untranslated version of the first occurrence of an entry of the specified type from the resource list.

## -returns

<code>FindUntranslatedEntry</code> returns a pointer to the specified entry or is <b>NULL</b> if the entry does not exist. This pointer remains valid until the resource object is deleted.

## -remarks

For each resource type, a macro is defined to call this method. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>.

The <i>Index</i> parameter indicates which occurrence of an entry of the specified type to find in the list of translated resource entries. The first occurrence in the list has an index of zero.

For each resource type, a macro is defined to call this method. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>.

For more information about translated and untranslated (or "raw") resources, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iresourcelist-findtranslatedentry">IResourceList::FindTranslatedEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iresourcelist-numberofentriesoftype">IResourceList::NumberOfEntriesOfType</a>

