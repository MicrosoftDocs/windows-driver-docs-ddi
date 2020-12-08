---
UID: NF:portcls.PcNewResourceSublist
title: PcNewResourceSublist function (portcls.h)
description: The PcNewResourceSublist function creates and initializes an empty resource list that is derived from another resource list.
old-location: audio\pcnewresourcesublist.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PcNewResourceSublist function"]
ms.keywords: PcNewResourceSublist, PcNewResourceSublist function [Audio Devices], audio.pcnewresourcesublist, audpc-routines_3354ba13-6737-4862-b8b4-2afa64dc8eab.xml, portcls/PcNewResourceSublist
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PcNewResourceSublist
 - portcls/PcNewResourceSublist
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Portcls.lib
 - Portcls.dll
api_name:
 - PcNewResourceSublist
---

# PcNewResourceSublist function


## -description

The <b>PcNewResourceSublist</b> function creates and initializes an empty resource list that is derived from another resource list.

## -parameters

### -param OutResourceList 

[out]
Output pointer to the resource-list object that this function creates. This parameter points to the caller-allocated pointer variable into which the function outputs the pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.

### -param OuterUnknown 

[in, optional]
Pointer to the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.

### -param PoolType 

[in]
Specifies the type of pool from which the object is to be allocated. This is a <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a> enumeration value.

### -param ParentList 

[in]
Pointer to the resource list from which the child list will be created. The resource list has an <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a> interface.

### -param MaximumEntries 

[in]
Specifies the maximum number of entries that will be added to the resource list.

## -returns

<b>PcNewResourceSublist</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

This function creates an empty resource sublist.

An adapter driver typically uses the <b>PcNewResourceSublist</b> function in combination with the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iresourcelist-addentryfromparent">IResourceList::AddEntryFromParent</a> method to take the original list of resources that it received from the system and divide them up into sublists that it assigns to its various subdevices.

The <i>OutResourceList</i>, <i>OuterUnknown</i>, and <i>ParentList</i> parameters follow the <a href="/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iresourcelist-addentryfromparent">IResourceList::AddEntryFromParent</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>
