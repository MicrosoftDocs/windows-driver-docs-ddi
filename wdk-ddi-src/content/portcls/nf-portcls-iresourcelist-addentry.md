---
UID: NF:portcls.IResourceList.AddEntry
title: IResourceList::AddEntry (portcls.h)
description: The AddEntry method adds an entry to a resource list.
old-location: audio\iresourcelist_addentry.htm
tech.root: audio
ms.assetid: 7f4ac419-a24e-4421-9891-9fea9479e781
ms.date: 05/08/2018
keywords: ["IResourceList::AddEntry"]
ms.keywords: AddEntry, AddEntry method [Audio Devices], AddEntry method [Audio Devices],IResourceList interface, IResourceList interface [Audio Devices],AddEntry method, IResourceList.AddEntry, IResourceList::AddEntry, audio.iresourcelist_addentry, audmp-routines_6a6091c9-4cb3-40ca-8bb9-39b239c322b7.xml, portcls/IResourceList::AddEntry
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
 - IResourceList::AddEntry
 - portcls/IResourceList::AddEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IResourceList.AddEntry
---

# IResourceList::AddEntry


## -description

The <code>AddEntry</code> method adds an entry to a resource list.

## -parameters

### -param Translated 

[in]
Pointer to a translated version of the entry. This parameter points to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure containing the translated version of the entry to be added.

### -param Untranslated 

[in]
Pointer to an untranslated version of the entry. This parameter points to a CM_PARTIAL_RESOURCE_DESCRIPTOR structure containing the untranslated (or "raw") version of the entry to be added.

## -returns

<code>AddEntry</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates there are no free entries in the list.

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>