---
UID: NF:portcls.IResourceList.AddEntryFromParent
title: IResourceList::AddEntryFromParent method
author: windows-driver-content
description: The AddEntryFromParent method adds to a resource list an entry found in the resource list's parent list.
old-location: audio\iresourcelist_addentryfromparent.htm
old-project: audio
ms.assetid: 83733c17-1f1f-4be6-ae14-aa921e481a73
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: AddEntryFromParent method [Audio Devices], AddEntryFromParent method [Audio Devices], IResourceList interface, AddEntryFromParent,IResourceList.AddEntryFromParent, IResourceList, IResourceList interface [Audio Devices], AddEntryFromParent method, IResourceList::AddEntryFromParent, audio.iresourcelist_addentryfromparent, audmp-routines_428c97a0-498d-4732-a2cc-5be2af2aa64c.xml, portcls/IResourceList::AddEntryFromParent
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
-	IResourceList.AddEntryFromParent
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IResourceList::AddEntryFromParent method


## -description


The <code>AddEntryFromParent</code> method adds to a resource list an entry found in the resource list's parent list.


## -parameters




### -param Parent [in]

Pointer to parent <b>IResourceList</b> object from which the entry is to be taken.


### -param Type [in]

Identifies the resource type of the entry that is to be added. For a list of valid resource-type values, see the description of the <b>Type</b> member of the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.


### -param Index [in]

Specifies the index in the parent list of the entry to add. If the parent's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a> method returns a value <i>n</i> for the number of entries of type <i>Type</i>, valid indices range from 0 to <i>n</i>-1. If <i>Index</i> is zero, for example, the method adds the first occurrence of an entry of the specified type from the parent list.


## -returns



<code>AddEntryFromParent</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates the entry was not found in the parent list.

</td>
</tr>
</table>
 




## -remarks



For each resource type, a macro is defined to call this method. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>.

The <i>Parent</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a>
 

 

