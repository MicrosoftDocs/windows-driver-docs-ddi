---
UID: NS:iscsimgt._MSiSCSI_RedirectPortalInfoClass
title: _MSiSCSI_RedirectPortalInfoClass (iscsimgt.h)
description: The MSiSCSI_RedirectPortalInfoClass structure contains information about a collection of sessions for an adapter ID. It also contains the portal redirection information for each of the sessions.
old-location: storage\msiscsi_redirectportalinfoclass.htm
tech.root: storage
ms.assetid: fcddf029-748b-4300-9f87-a103d961918a
ms.date: 03/29/2018
ms.keywords: "*PMSiSCSI_RedirectPortalInfoClass, MSiSCSI_RedirectPortalInfoClass, MSiSCSI_RedirectPortalInfoClass structure [Storage Devices], PMSiSCSI_RedirectPortalInfoClass, PMSiSCSI_RedirectPortalInfoClass structure pointer [Storage Devices], _MSiSCSI_RedirectPortalInfoClass, iscsimgt/MSiSCSI_RedirectPortalInfoClass, iscsimgt/PMSiSCSI_RedirectPortalInfoClass, storage.msiscsi_redirectportalinfoclass, structs-iSCSI_211386cb-7e73-40d9-8284-560555fe8201.xml"
ms.topic: struct
f1_keywords:
 - "iscsimgt/MSiSCSI_RedirectPortalInfoClass"
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
- MSiSCSI_RedirectPortalInfoClass
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_RedirectPortalInfoClass, *PMSiSCSI_RedirectPortalInfoClass
---

# _MSiSCSI_RedirectPortalInfoClass structure


## -description


The MSiSCSI_RedirectPortalInfoClass structure contains information about a collection of sessions for an adapter ID. It also contains the portal redirection information for each of the sessions.


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID).


### -field SessionCount

The number of sessions for which this structure contains information.


### -field RedirectSessionList

An array of structures that contains as many ISCSI_RedirectSessionInfo structures as specified in the connection count.


## -remarks



You must implement this class if the adapter supports target portal hopping. Otherwise, it is optional.



