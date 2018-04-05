---
UID: NF:portcls.PcNewResourceSublist
title: PcNewResourceSublist function
author: windows-driver-content
description: The PcNewResourceSublist function creates and initializes an empty resource list that is derived from another resource list.
old-location: audio\pcnewresourcesublist.htm
old-project: audio
ms.assetid: a7e1a7cf-60ea-4489-a1c2-eac5b218af8c
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: PcNewResourceSublist, PcNewResourceSublist function [Audio Devices], audio.pcnewresourcesublist, audpc-routines_3354ba13-6737-4862-b8b4-2afa64dc8eab.xml, portcls/PcNewResourceSublist
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcNewResourceSublist
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcNewResourceSublist function


## -description


The <b>PcNewResourceSublist</b> function creates and initializes an empty resource list that is derived from another resource list.


## -parameters




### -param OutResourceList [out]

Output pointer to the resource-list object that this function creates. This parameter points to the caller-allocated pointer variable into which the function outputs the pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.


### -param PoolType [in]

Specifies the type of pool from which the object is to be allocated. This is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a> enumeration value.


### -param ParentList [in]

Pointer to the resource list from which the child list will be created. The resource list has an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a> interface.


### -param MaximumEntries [in]

Specifies the maximum number of entries that will be added to the resource list.


## -returns



<b>PcNewResourceSublist</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



This function creates an empty resource sublist.

An adapter driver typically uses the <b>PcNewResourceSublist</b> function in combination with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536981">IResourceList::AddEntryFromParent</a> method to take the original list of resources that it received from the system and divide them up into sublists that it assigns to its various subdevices.

The <i>OutResourceList</i>, <i>OuterUnknown</i>, and <i>ParentList</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536981">IResourceList::AddEntryFromParent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>
 

 

