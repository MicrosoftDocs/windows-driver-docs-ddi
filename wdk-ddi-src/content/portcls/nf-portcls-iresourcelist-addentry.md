---
UID: NF:portcls.IResourceList.AddEntry
title: IResourceList::AddEntry method
author: windows-driver-content
description: The AddEntry method adds an entry to a resource list.
old-location: audio\iresourcelist_addentry.htm
old-project: audio
ms.assetid: 7f4ac419-a24e-4421-9891-9fea9479e781
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: AddEntry method [Audio Devices], AddEntry method [Audio Devices], IResourceList interface, AddEntry,IResourceList.AddEntry, IResourceList, IResourceList interface [Audio Devices], AddEntry method, IResourceList::AddEntry, audio.iresourcelist_addentry, audmp-routines_6a6091c9-4cb3-40ca-8bb9-39b239c322b7.xml, portcls/IResourceList::AddEntry
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
-	IResourceList.AddEntry
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IResourceList::AddEntry method


## -description


The <code>AddEntry</code> method adds an entry to a resource list.


## -syntax


````
NTSTATUS AddEntry(
  [in] PCM_PARTIAL_RESOURCE_DESCRIPTOR Translated,
  [in] PCM_PARTIAL_RESOURCE_DESCRIPTOR Untranslated
);
````


## -parameters




### -param Translated [in]

Pointer to a translated version of the entry. This parameter points to a <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure containing the translated version of the entry to be added.


### -param Untranslated [in]

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

<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>



<a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IResourceList::AddEntry method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

