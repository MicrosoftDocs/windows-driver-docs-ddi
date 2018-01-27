---
UID: NF:portcls.IResourceList.UntranslatedList
title: IResourceList::UntranslatedList method
author: windows-driver-content
description: The UntranslatedList method returns the list of untranslated resources.
old-location: audio\iresourcelist_untranslatedlist.htm
old-project: audio
ms.assetid: b5b0a540-2730-40ef-8f65-135a19b9a732
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IResourceList::UntranslatedList, UntranslatedList, portcls/IResourceList::UntranslatedList, audmp-routines_b367743a-b341-49cc-a300-da84b91ec7a5.xml, IResourceList interface [Audio Devices], UntranslatedList method, UntranslatedList method [Audio Devices], IResourceList interface, audio.iresourcelist_untranslatedlist, IResourceList, UntranslatedList method [Audio Devices]
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	portcls.h
apiname: 
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


<code>UntranslatedList</code> returns a pointer to a <a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a> structure that specifies all of the system hardware resources that are assigned to the device. The resources in the list are in untranslated form. This pointer remains valid until the resource list object is deleted.



## -see-also

<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>

<a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IResourceList::UntranslatedList method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

