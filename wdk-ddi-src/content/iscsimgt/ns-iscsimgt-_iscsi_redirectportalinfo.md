---
UID: NS:iscsimgt._ISCSI_RedirectPortalInfo
title: _ISCSI_RedirectPortalInfo (iscsimgt.h)
description: This ISCSI_RedirectPortalInfo structure contains information about a collection of iSCSI portals that can be used during portal hopping or portal redirect operations.
old-location: storage\iscsi_redirectportalinfo.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ISCSI_RedirectPortalInfo structure"]
ms.keywords: "*PISCSI_RedirectPortalInfo, ISCSI_RedirectPortalInfo, ISCSI_RedirectPortalInfo structure [Storage Devices], PISCSI_RedirectPortalInfo, PISCSI_RedirectPortalInfo structure pointer [Storage Devices], _ISCSI_RedirectPortalInfo, iscsimgt/ISCSI_RedirectPortalInfo, iscsimgt/PISCSI_RedirectPortalInfo, storage.iscsi_redirectportalinfo, structs-iSCSI_6b7dc6ac-b421-4454-aa8f-48f52c9b4350.xml"
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
targetos: Windows
req.typenames: ISCSI_RedirectPortalInfo, *PISCSI_RedirectPortalInfo
f1_keywords:
 - _ISCSI_RedirectPortalInfo
 - iscsimgt/_ISCSI_RedirectPortalInfo
 - PISCSI_RedirectPortalInfo
 - iscsimgt/PISCSI_RedirectPortalInfo
 - ISCSI_RedirectPortalInfo
 - iscsimgt/ISCSI_RedirectPortalInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsimgt.h
api_name:
 - ISCSI_RedirectPortalInfo
---

# _ISCSI_RedirectPortalInfo structure


## -description

This ISCSI_RedirectPortalInfo structure contains information about a collection of iSCSI portals that can be used during portal hopping or portal redirect operations. If a target portal is not available for login, the initiator can "hop" through the list of target portals that it discovered and that can be used for login operations. That is, the initiator will continue to try the list of portals that are available until it finds one that can be used for login, so it can then log in to the available target portal.

## -struct-fields

### -field UniqueConnectionId

The connection identifier (ID) that the operating system and application software use to uniquely identify the connection. The <a href="/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods both return this value in the UniqueConnectionId parameter. This value is not to be confused with the connection ID (CID).

### -field OriginalIPAddr

This is the original IP address given during login from which redirection is to be set, and the IP address is provided via the ISCSI_IP_Address structure.

### -field OriginalPort

This is the original portals socket number given during login.

### -field RedirectedIPAddr

This is the IP address to which traffic needs to be redirected. The IP address is provided via the ISCSI_IP_Address structure.

### -field RedirectedPort

This is the socket number for the redirected target portal.

### -field Redirected

This indicates whether the login is redirected. If this value is <b>TRUE</b>, RedirectedIPAddr and RedirectedPort are valid.

### -field TemporaryRedirect

This value is <b>true</b> if redirection is temporary.

## -see-also

<a href="/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>
