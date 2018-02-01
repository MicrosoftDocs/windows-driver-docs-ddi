---
UID: NS:iscsimgt._ISCSI_RedirectSessionInfo
title: "_ISCSI_RedirectSessionInfo"
author: windows-driver-content
description: This ISCSI_RedirectSessionInfo structure contains information about an iSCSI session and its portal information resulted from iSCSI target redirection.
old-location: storage\iscsi_redirectsessioninfo.htm
old-project: storage
ms.assetid: e3980ac7-b539-4a8f-9869-14d418ebe1e7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: iscsimgt/PISCSI_RedirectSessionInfo, storage.iscsi_redirectsessioninfo, PISCSI_RedirectSessionInfo structure pointer [Storage Devices], PISCSI_RedirectSessionInfo, *PISCSI_RedirectSessionInfo, structs-iSCSI_41ab8376-0e0e-40af-8cab-1be2f63edeed.xml, iscsimgt/ISCSI_RedirectSessionInfo, ISCSI_RedirectSessionInfo, _ISCSI_RedirectSessionInfo, ISCSI_RedirectSessionInfo structure [Storage Devices]
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
-	ISCSI_RedirectSessionInfo
product: Windows
targetos: Windows
req.typenames: ISCSI_RedirectSessionInfo, *PISCSI_RedirectSessionInfo
---

# _ISCSI_RedirectSessionInfo structure


## -description


This ISCSI_RedirectSessionInfo structure contains information about an iSCSI session and its portal information resulted from iSCSI target redirection.


## -syntax


````
typedef struct _ISCSI_RedirectSessionInfo {
  ULONGLONG                UniqueSessionId;
  ULONG                    TargetPortalGroupTag;
  ULONG                    ConnectionCount;
  ISCSI_RedirectPortalInfo RedirectPortalList[1];
} ISCSI_RedirectSessionInfo, *PISCSI_RedirectSessionInfo;
````


## -struct-fields




### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in their UniqueSessionId parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field TargetPortalGroupTag

Target portal group tag for this session Id.


### -field ConnectionCount

Number of connections for each session.


### -field RedirectPortalList

This provides the redirection information, and it has as many entries as the number of connections for each session.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_RedirectSessionInfo structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

