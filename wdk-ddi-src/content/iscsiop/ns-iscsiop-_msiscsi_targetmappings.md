---
UID: NS:iscsiop._MSiSCSI_TargetMappings
title: _MSiSCSI_TargetMappings (iscsiop.h)
description: The MSiSCSI_TargetMappings structure contains a set of logical unit number (LUN) mappings that are associated with an initiator instance.
old-location: storage\msiscsi_targetmappings.htm
tech.root: storage
ms.assetid: 6bddeaeb-9913-4c90-b8ac-3a9f7b384b80
ms.date: 03/29/2018
keywords: ["_MSiSCSI_TargetMappings structure"]
ms.keywords: "*PMSiSCSI_TargetMappings, MSiSCSI_TargetMappings, MSiSCSI_TargetMappings structure [Storage Devices], PMSiSCSI_TargetMappings, PMSiSCSI_TargetMappings structure pointer [Storage Devices], _MSiSCSI_TargetMappings, iscsiop/MSiSCSI_TargetMappings, iscsiop/PMSiSCSI_TargetMappings, storage.msiscsi_targetmappings, structs-iSCSI_b8a3267a-8bab-4be6-9f3c-4086cc54f0f5.xml"
f1_keywords:
 - "iscsiop/MSiSCSI_TargetMappings"
 - "MSiSCSI_TargetMappings"
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiop.h
api_name:
- MSiSCSI_TargetMappings
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_TargetMappings, *PMSiSCSI_TargetMappings
---

# _MSiSCSI_TargetMappings structure


## -description


The MSiSCSI_TargetMappings structure contains a set of logical unit number (LUN) mappings that are associated with an initiator instance. 


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_msiscsi_hbainformation">MSiSCSI_HBAInformation</a> structure.


### -field TargetMappingCount

The number of mappings in the <b>TargetMappings</b> member.


### -field Reserved

Reserved for Microsoft use only.


### -field TargetMappings

A variable-length array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_targetmapping">ISCSI_TargetMapping</a> structures, each of which provides a list of LUN mappings that are associated with a particular iSCSI session that is associated with the adapter ID.


## -remarks



You must implement this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_targetmapping">ISCSI_TargetMapping</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_msiscsi_hbainformation">MSiSCSI_HBAInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-targetmappings-wmi-class">MSiSCSI_TargetMappings WMI Class</a>
 

 

