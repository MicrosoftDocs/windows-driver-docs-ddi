---
UID: NS:iscsimgt._ISCSI_RedirectSessionInfo
title: "_ISCSI_RedirectSessionInfo"
author: windows-driver-content
description: This ISCSI_RedirectSessionInfo structure contains information about an iSCSI session and its portal information resulted from iSCSI target redirection.
old-location: storage\iscsi_redirectsessioninfo.htm
old-project: storage
ms.assetid: e3980ac7-b539-4a8f-9869-14d418ebe1e7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PISCSI_RedirectSessionInfo, ISCSI_RedirectSessionInfo, ISCSI_RedirectSessionInfo structure [Storage Devices], PISCSI_RedirectSessionInfo, PISCSI_RedirectSessionInfo structure pointer [Storage Devices], _ISCSI_RedirectSessionInfo, iscsimgt/ISCSI_RedirectSessionInfo, iscsimgt/PISCSI_RedirectSessionInfo, storage.iscsi_redirectsessioninfo, structs-iSCSI_41ab8376-0e0e-40af-8cab-1be2f63edeed.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsimgt.h
api_name:
-	ISCSI_RedirectSessionInfo
product: Windows
targetos: Windows
req.typenames: ISCSI_RedirectSessionInfo, *PISCSI_RedirectSessionInfo
---

# _ISCSI_RedirectSessionInfo structure


## -description


This ISCSI_RedirectSessionInfo structure contains information about an iSCSI session and its portal information resulted from iSCSI target redirection.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>
 

 

