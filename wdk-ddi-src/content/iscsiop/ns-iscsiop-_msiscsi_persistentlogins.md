---
UID: NS:iscsiop._MSiSCSI_PersistentLogins
title: _MSiSCSI_PersistentLogins (iscsiop.h)
description: The MSiSCSI_PersistentLogins structure contains the list of persistent target logon sessions.
old-location: storage\msiscsi_persistentlogins.htm
tech.root: storage
ms.assetid: c735d9c9-8e87-4a80-af1d-c97d457f78fa
ms.date: 03/29/2018
ms.keywords: "*PMSiSCSI_PersistentLogins, MSiSCSI_PersistentLogins, MSiSCSI_PersistentLogins structure [Storage Devices], PMSiSCSI_PersistentLogins, PMSiSCSI_PersistentLogins structure pointer [Storage Devices], _MSiSCSI_PersistentLogins, iscsiop/MSiSCSI_PersistentLogins, iscsiop/PMSiSCSI_PersistentLogins, storage.msiscsi_persistentlogins, structs-iSCSI_150a8086-8025-4140-9fdb-75d05bfcb0ac.xml"
ms.topic: struct
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
- MSiSCSI_PersistentLogins
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_PersistentLogins, *PMSiSCSI_PersistentLogins
---

# _MSiSCSI_PersistentLogins structure


## -description


The MSiSCSI_PersistentLogins structure contains the list of persistent target logon sessions. 


## -struct-fields




### -field PersistentLoginCount

The number of persistent target logon sessions that the initiator manages.


### -field Reserved

Reserved for Microsoft use only.


### -field PersistentLogins

A variable length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561553">ISCSI_Persistent_Login</a> structures, each of which contains information that is associated with a particular persistent logon session that the initiator maintains.


## -remarks



Miniport drivers that manage iSCSI initiators automatically establish persistent logon sessions as soon as they are loaded into the storage driver stack. This guarantees that targets for which the initiator maintains persistent logon sessions will be available to the system as early in the startup process as possible. You must implement this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561553">ISCSI_Persistent_Login</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561556">ISCSI_Persistent_Login WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563096">MSiSCSI_PersistentLogins WMI Class</a>
 

 

