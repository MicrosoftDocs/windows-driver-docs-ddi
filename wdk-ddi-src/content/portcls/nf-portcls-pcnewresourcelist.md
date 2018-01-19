---
UID: NF:portcls.PcNewResourceList
title: PcNewResourceList function
author: windows-driver-content
description: The PcNewResourceList function creates and initializes a resource list.
old-location: audio\pcnewresourcelist.htm
old-project: audio
ms.assetid: 80576db6-38de-46c6-89f1-a3dde613fed1
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcNewResourceList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcNewResourceList function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcNewResourceList
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

# PcNewResourceList function



## -description
The <b>PcNewResourceList</b> function creates and initializes a resource list.



## -syntax

````
NTSTATUS PcNewResourceList(
  _Out_    PRESOURCELIST     *OutResourceList,
  _In_opt_ PUNKNOWN          OuterUnknown,
  _In_     POOL_TYPE         PoolType,
  _In_     PCM_RESOURCE_LIST TranslatedResources,
  _In_     PCM_RESOURCE_LIST UntranslatedResources
);
````


## -parameters

### -param OutResourceList [out]

Output pointer for the resource-list object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs the pointer to the <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of an object that needs to aggregate the resource-list object. Unless aggregation is required, set this parameter to <b>NULL</b>.


### -param PoolType [in]

Specifies the type of pool from which the object is to be allocated. This is a <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a> enumeration value.


### -param TranslatedResources [in]

Pointer to a WDM-supplied resource list for translated resources. The list is a system structure of type <a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>.


### -param UntranslatedResources [in]

Pointer to a WDM-supplied resource list for untranslated resources. The list is a system structure of type <a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>.


## -returns
<b>PcNewResourceList</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.


## -remarks
For a discussion of translated and untranslated (or "raw") resource lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554399">Mapping Bus-Relative Addresses to Virtual Addresses</a>.

The <i>OutResourceList</i> and <i>OuterUnknown</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.


## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcNewResourceList function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

