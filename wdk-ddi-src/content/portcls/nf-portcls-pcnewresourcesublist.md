---
UID: NF:portcls.PcNewResourceSublist
title: PcNewResourceSublist function
author: windows-driver-content
description: The PcNewResourceSublist function creates and initializes an empty resource list that is derived from another resource list.
old-location: audio\pcnewresourcesublist.htm
old-project: audio
ms.assetid: a7e1a7cf-60ea-4489-a1c2-eac5b218af8c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcNewResourceSublist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcNewResourceSublist function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcNewResourceSublist
req.alt-loc: Portcls.lib,Portcls.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcNewResourceSublist function



## -description
The <b>PcNewResourceSublist</b> function creates and initializes an empty resource list that is derived from another resource list.



## -syntax

````
NTSTATUS PcNewResourceSublist(
  _Out_    PRESOURCELIST *OutResourceList,
  _In_opt_ PUNKNOWN      OuterUnknown,
  _In_     POOL_TYPE     PoolType,
  _In_     PRESOURCELIST ParentList,
  _In_     ULONG         MaximumEntries
);
````


## -parameters

### -param OutResourceList [out]

Output pointer to the resource-list object that this function creates. This parameter points to the caller-allocated pointer variable into which the function outputs the pointer to the <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.


### -param PoolType [in]

Specifies the type of pool from which the object is to be allocated. This is a <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a> enumeration value.


### -param ParentList [in]

Pointer to the resource list from which the child list will be created. The resource list has an <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a> interface.


### -param MaximumEntries [in]

Specifies the maximum number of entries that will be added to the resource list.


## -returns
<b>PcNewResourceSublist</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.


## -remarks
This function creates an empty resource sublist.

An adapter driver typically uses the <b>PcNewResourceSublist</b> function in combination with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536981">IResourceList::AddEntryFromParent</a> method to take the original list of resources that it received from the system and divide them up into sublists that it assigns to its various subdevices.

The <i>OutResourceList</i>, <i>OuterUnknown</i>, and <i>ParentList</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.


## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536981">IResourceList::AddEntryFromParent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcNewResourceSublist function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

