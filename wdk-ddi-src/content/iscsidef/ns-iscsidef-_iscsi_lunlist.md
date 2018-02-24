---
UID: NS:iscsidef._ISCSI_LUNList
title: "_ISCSI_LUNList"
author: windows-driver-content
description: The ISCSI_LUNList structure defines a mapping between the LUN number that is used by the operating system and the LUN number that is configured in the iSCSI target.
old-location: storage\iscsi_lunlist.htm
old-project: storage
ms.assetid: 1c477f38-c24f-45df-ab02-62ee47c0957b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ISCSI_LUNList, structs-iSCSI_f6a29259-8905-438e-ba9f-1055026d7bf6.xml, PISCSI_LUNList, *PISCSI_LUNList, ISCSI_LUNList structure [Storage Devices], _ISCSI_LUNList, iscsidef/PISCSI_LUNList, storage.iscsi_lunlist, PISCSI_LUNList structure pointer [Storage Devices], iscsidef/ISCSI_LUNList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsidef.h
req.include-header: Iscsidef.h
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
-	iscsidef.h
apiname:
-	ISCSI_LUNList
product: Windows
targetos: Windows
req.typenames: ISCSI_LUNList, *PISCSI_LUNList
---

# _ISCSI_LUNList structure


## -description


The ISCSI_LUNList structure defines a mapping between the LUN number that is used by the operating system and the LUN number that is configured in the iSCSI target.


## -syntax


````
typedef struct _ISCSI_LUNList {
  ULONGLONG TargetLUN;
  ULONG     OSLUN;
  ULONG     Reserved;
} ISCSI_LUNList, *PISCSI_LUNList;
````


## -struct-fields




### -field TargetLUN

A LUN that is globally valid anywhere in the network.


### -field OSLUN

The SCSI LUN (which is valid in the local operating system) that the remote LUN is mapped to.


### -field Reserved

Reserved for Microsoft use only. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561547">ISCSI_LUNList WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_LUNList structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

