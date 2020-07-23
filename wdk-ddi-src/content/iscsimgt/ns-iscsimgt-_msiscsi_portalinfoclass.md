---
UID: NS:iscsimgt._MSiSCSI_PortalInfoClass
title: _MSiSCSI_PortalInfoClass (iscsimgt.h)
description: The MSiSCSI_PortalInfoClass structure contains information about a collection of iSCSI portals.
old-location: storage\msiscsi_portalinfoclass.htm
tech.root: storage
ms.assetid: 400ff6fc-6eb7-4b3f-afec-7d0b69039ed1
ms.date: 03/29/2018
keywords: ["_MSiSCSI_PortalInfoClass structure"]
ms.keywords: "*PMSiSCSI_PortalInfoClass, MSiSCSI_PortalInfoClass, MSiSCSI_PortalInfoClass structure [Storage Devices], PMSiSCSI_PortalInfoClass, PMSiSCSI_PortalInfoClass structure pointer [Storage Devices], _MSiSCSI_PortalInfoClass, iscsimgt/MSiSCSI_PortalInfoClass, iscsimgt/PMSiSCSI_PortalInfoClass, storage.msiscsi_portalinfoclass, structs-iSCSI_dec2f67f-5b12-4432-8c64-eef6efeb7e6a.xml"
f1_keywords:
 - "iscsimgt/MSiSCSI_PortalInfoClass"
 - "MSiSCSI_PortalInfoClass"
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
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
- iscsimgt.h
api_name:
- MSiSCSI_PortalInfoClass
targetos: Windows
req.typenames: MSiSCSI_PortalInfoClass, *PMSiSCSI_PortalInfoClass
---

# _MSiSCSI_PortalInfoClass structure


## -description


The MSiSCSI_PortalInfoClass structure contains information about a collection of iSCSI portals.


## -struct-fields




### -field PortalInfoCount

The number of portals that the initiator discovered and for which portal information is available.


### -field PortalInformation

A variable length array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_iscsi_portalinfo">ISCSI_PortalInfo</a> structures. The number of elements in the array is specified by the <b>PortalInfoCount</b> field.


## -remarks



We recommend that you implement this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_iscsi_portalinfo">ISCSI_PortalInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-portalinfoclass-wmi-class">MSiSCSI_PortalInfoClass WMI Class</a>
 

 

