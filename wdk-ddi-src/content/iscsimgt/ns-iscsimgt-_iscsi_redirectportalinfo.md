---
UID: NS:iscsimgt._ISCSI_RedirectPortalInfo
title: _ISCSI_RedirectPortalInfo
author: windows-driver-content
description: This ISCSI_RedirectPortalInfo structure contains information about a collection of iSCSI portals that can be used during portal hopping or portal redirect operations.
old-location: storage\iscsi_redirectportalinfo.htm
old-project: storage
ms.assetid: 90d9c5e9-4bdf-4c7a-b5ac-54e1f94818bf
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ISCSI_RedirectPortalInfo structure [Storage Devices], iscsimgt/PISCSI_RedirectPortalInfo, structs-iSCSI_6b7dc6ac-b421-4454-aa8f-48f52c9b4350.xml, _ISCSI_RedirectPortalInfo, PISCSI_RedirectPortalInfo structure pointer [Storage Devices], PISCSI_RedirectPortalInfo, iscsimgt/ISCSI_RedirectPortalInfo, storage.iscsi_redirectportalinfo, *PISCSI_RedirectPortalInfo, ISCSI_RedirectPortalInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	iscsimgt.h
apiname: 
-	ISCSI_RedirectPortalInfo
product: Windows
targetos: Windows
req.typenames: ISCSI_RedirectPortalInfo, *PISCSI_RedirectPortalInfo
---

# _ISCSI_RedirectPortalInfo structure


## -description


This ISCSI_RedirectPortalInfo structure contains information about a collection of iSCSI portals that can be used during portal hopping or portal redirect operations. If a target portal is not available for login, the initiator can "hop" through the list of target portals that it discovered and that can be used for login operations. That is, the initiator will continue to try the list of portals that are available until it finds one that can be used for login, so it can then log in to the available target portal.


## -syntax


````
typedef struct _ISCSI_RedirectPortalInfo {
  ULONGLONG        UniqueConnectionId;
  ISCSI_IP_Address OriginalIPAddr;
  ULONG            OriginalPort;
  ISCSI_IP_Address RedirectedIPAddr;
  ULONG            RedirectedPort;
  UCHAR            Redirected;
  UCHAR            TemporaryRedirect;
} ISCSI_RedirectPortalInfo, *PISCSI_RedirectPortalInfo;
````


## -struct-fields




### -field UniqueConnectionId

The connection identifier (ID) that the operating system and application software use to uniquely identify the connection. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in the UniqueConnectionId parameter. This value is not to be confused with the connection ID (CID).


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_RedirectPortalInfo structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

