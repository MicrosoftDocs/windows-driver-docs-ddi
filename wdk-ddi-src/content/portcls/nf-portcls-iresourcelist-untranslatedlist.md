---
UID: NF:portcls.IResourceList.UntranslatedList
title: IResourceList::UntranslatedList method
author: windows-driver-content
description: The UntranslatedList method returns the list of untranslated resources.
old-location: audio\iresourcelist_untranslatedlist.htm
old-project: audio
ms.assetid: b5b0a540-2730-40ef-8f65-135a19b9a732
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IResourceList, IResourceList interface [Audio Devices], UntranslatedList method, IResourceList::UntranslatedList, UntranslatedList method [Audio Devices], UntranslatedList method [Audio Devices], IResourceList interface, UntranslatedList,IResourceList.UntranslatedList, audio.iresourcelist_untranslatedlist, audmp-routines_b367743a-b341-49cc-a300-da84b91ec7a5.xml, portcls/IResourceList::UntranslatedList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IResourceList.UntranslatedList
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IResourceList::UntranslatedList method


## -description


The <code>UntranslatedList</code> method returns the list of untranslated resources.


## -syntax


````
PCM_RESOURCE_LIST UntranslatedList(
    None
);
````


## -parameters






#### - None


## -returns



<code>UntranslatedList</code> returns a pointer to a <a href="..\wudfwdm\ns-wudfwdm-_cm_resource_list.md">CM_RESOURCE_LIST</a> structure that specifies all of the system hardware resources that are assigned to the device. The resources in the list are in untranslated form. This pointer remains valid until the resource list object is deleted.




## -see-also

<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>



<a href="..\wudfwdm\ns-wudfwdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>



 

 


