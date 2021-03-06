---
UID: NF:portcls.IResourceList.TranslatedList
title: IResourceList::TranslatedList (portcls.h)
description: The TranslatedList method returns the list of translated resources.
old-location: audio\iresourcelist_translatedlist.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IResourceList::TranslatedList"]
ms.keywords: IResourceList interface [Audio Devices],TranslatedList method, IResourceList.TranslatedList, IResourceList::TranslatedList, TranslatedList, TranslatedList method [Audio Devices], TranslatedList method [Audio Devices],IResourceList interface, audio.iresourcelist_translatedlist, audmp-routines_d74c0767-97d9-4488-82f1-51cde4dc8259.xml, portcls/IResourceList::TranslatedList
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
 - IResourceList::TranslatedList
 - portcls/IResourceList::TranslatedList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IResourceList::TranslatedList
---

# IResourceList::TranslatedList


## -description

The <code>TranslatedList</code> method returns the list of translated resources.

## -parameters

## -returns

<code>TranslatedList</code> returns a pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a> structure that specifies all of the system hardware resources that are assigned to the device. This pointer remains valid until the resource list object is deleted.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>

