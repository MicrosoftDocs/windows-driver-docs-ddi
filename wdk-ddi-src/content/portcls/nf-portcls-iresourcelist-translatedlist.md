---
UID: NF:portcls.IResourceList.TranslatedList
title: IResourceList::TranslatedList
author: windows-driver-content
description: The TranslatedList method returns the list of translated resources.
old-location: audio\iresourcelist_translatedlist.htm
old-project: audio
ms.assetid: 6bc4f939-dbc8-4d9a-95f9-b5ec97a47a8a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IResourceList interface [Audio Devices],TranslatedList method, IResourceList.TranslatedList, IResourceList::TranslatedList, TranslatedList, TranslatedList method [Audio Devices], TranslatedList method [Audio Devices],IResourceList interface, audio.iresourcelist_translatedlist, audmp-routines_d74c0767-97d9-4488-82f1-51cde4dc8259.xml, portcls/IResourceList::TranslatedList
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
-	IResourceList.TranslatedList
product:
- Windows
targetos: Windows
req.typenames: 
---

# IResourceList::TranslatedList


## -description


The <code>TranslatedList</code> method returns the list of translated resources.


## -parameters






#### - None


## -returns



<code>TranslatedList</code> returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541994">CM_RESOURCE_LIST</a> structure that specifies all of the system hardware resources that are assigned to the device. This pointer remains valid until the resource list object is deleted.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541994">CM_RESOURCE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>
 

 

