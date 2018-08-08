---
UID: NF:portcls.IResourceList.UntranslatedList
title: IResourceList::UntranslatedList
author: windows-driver-content
description: The UntranslatedList method returns the list of untranslated resources.
old-location: audio\iresourcelist_untranslatedlist.htm
tech.root: audio
ms.assetid: b5b0a540-2730-40ef-8f65-135a19b9a732
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: IResourceList interface [Audio Devices],UntranslatedList method, IResourceList.UntranslatedList, IResourceList::UntranslatedList, UntranslatedList, UntranslatedList method [Audio Devices], UntranslatedList method [Audio Devices],IResourceList interface, audio.iresourcelist_untranslatedlist, audmp-routines_b367743a-b341-49cc-a300-da84b91ec7a5.xml, portcls/IResourceList::UntranslatedList
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# IResourceList::UntranslatedList


## -description


The <code>UntranslatedList</code> method returns the list of untranslated resources.


## -parameters






#### - None


## -returns



<code>UntranslatedList</code> returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541994">CM_RESOURCE_LIST</a> structure that specifies all of the system hardware resources that are assigned to the device. The resources in the list are in untranslated form. This pointer remains valid until the resource list object is deleted.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541994">CM_RESOURCE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>
 

 

