---
UID: NF:portcls.IResourceList.UntranslatedList
title: IResourceList::UntranslatedList (portcls.h)
description: The UntranslatedList method returns the list of untranslated resources.
old-location: audio\iresourcelist_untranslatedlist.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IResourceList::UntranslatedList"]
ms.keywords: IResourceList interface [Audio Devices],UntranslatedList method, IResourceList.UntranslatedList, IResourceList::UntranslatedList, UntranslatedList, UntranslatedList method [Audio Devices], UntranslatedList method [Audio Devices],IResourceList interface, audio.iresourcelist_untranslatedlist, audmp-routines_b367743a-b341-49cc-a300-da84b91ec7a5.xml, portcls/IResourceList::UntranslatedList
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
 - IResourceList::UntranslatedList
 - portcls/IResourceList::UntranslatedList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IResourceList::UntranslatedList
---

# IResourceList::UntranslatedList


## -description

The <code>UntranslatedList</code> method returns the list of untranslated resources.

## -returns

<code>UntranslatedList</code> returns a pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a> structure that specifies all of the system hardware resources that are assigned to the device. The resources in the list are in untranslated form. This pointer remains valid until the resource list object is deleted.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>

