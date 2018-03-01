---
UID: NF:portcls.IResourceList.TranslatedList
title: IResourceList::TranslatedList method
author: windows-driver-content
description: The TranslatedList method returns the list of translated resources.
old-location: audio\iresourcelist_translatedlist.htm
old-project: audio
ms.assetid: 6bc4f939-dbc8-4d9a-95f9-b5ec97a47a8a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IResourceList, IResourceList interface [Audio Devices], TranslatedList method, IResourceList::TranslatedList, TranslatedList method [Audio Devices], TranslatedList method [Audio Devices], IResourceList interface, TranslatedList,IResourceList.TranslatedList, audio.iresourcelist_translatedlist, audmp-routines_d74c0767-97d9-4488-82f1-51cde4dc8259.xml, portcls/IResourceList::TranslatedList
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IResourceList.TranslatedList
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IResourceList::TranslatedList method


## -description


The <code>TranslatedList</code> method returns the list of translated resources.


## -syntax


````
PCM_RESOURCE_LIST TranslatedList(
    None
);
````


## -parameters






#### - None


## -returns



<code>TranslatedList</code> returns a pointer to a <a href="..\wudfwdm\ns-wudfwdm-_cm_resource_list.md">CM_RESOURCE_LIST</a> structure that specifies all of the system hardware resources that are assigned to the device. This pointer remains valid until the resource list object is deleted.




## -see-also

<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>



<a href="..\wudfwdm\ns-wudfwdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IResourceList::TranslatedList method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

