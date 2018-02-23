---
UID: NS:iscsifnd._ISCSI_DiscoveredTarget
title: "_ISCSI_DiscoveredTarget"
author: windows-driver-content
description: The ISCSI_DiscoveredTarget structure contains information that is related to a discovered target device.
old-location: storage\iscsi_discoveredtarget.htm
old-project: storage
ms.assetid: 0b4a7375-1ee2-4829-92bb-01ed610236de
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PISCSI_DiscoveredTarget, iscsifnd/ISCSI_DiscoveredTarget, _ISCSI_DiscoveredTarget, iscsifnd/PISCSI_DiscoveredTarget, storage.iscsi_discoveredtarget, ISCSI_DiscoveredTarget, structs-iSCSI_d53d59a0-bd96-4eb8-b874-5846302ddda2.xml, ISCSI_DiscoveredTarget structure [Storage Devices], PISCSI_DiscoveredTarget structure pointer [Storage Devices], *PISCSI_DiscoveredTarget
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsifnd.h
req.include-header: Iscsifnd.h
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
-	iscsifnd.h
apiname:
-	ISCSI_DiscoveredTarget
product: Windows
targetos: Windows
req.typenames: ISCSI_DiscoveredTarget, *PISCSI_DiscoveredTarget
---

# _ISCSI_DiscoveredTarget structure


## -description


The ISCSI_DiscoveredTarget structure contains information that is related to a discovered target device. 


## -syntax


````
typedef struct _ISCSI_DiscoveredTarget {
  ULONG                             TargetPortalGroupCount;
  WCHAR                             TargetName[223 + 1];
  WCHAR                             TargetAlias[255 + 1];
  ISCSI_DiscoveredTargetPortalGroup TargetDiscoveredPortalGroups[1];
} ISCSI_DiscoveredTarget, *PISCSI_DiscoveredTarget;
````


## -struct-fields




### -field TargetPortalGroupCount

The number of portal groups that are associated with the target.


### -field TargetName

A name for the target that uniquely identifies the target anywhere in the world. For information about how to specify this name, see the <i>iSCSI </i>specification that is published by the Internet Engineering Task Force (IETF) of the IP storage working group. 


### -field TargetAlias

The human-readable name or description that is assigned to the target device by its host operating system. You can use this name in user interfaces, but it is not unique, you should not use it in authentication decisions. 


### -field TargetDiscoveredPortalGroups

A variable-length array of <a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportalgroup.md">ISCSI_DiscoveredTargetPortalGroup</a> structures that contains information about the portal groups that the initiator can use to connect to the target.


## -remarks



The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTarget structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561527">ISCSI_DiscoveredTarget WMI Class</a> in <i>Discover.mof</i>. 




## -see-also

<a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportalgroup.md">ISCSI_DiscoveredTargetPortalGroup</a>



<a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtarget2.md">ISCSI_DiscoveredTarget2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561527">ISCSI_DiscoveredTarget WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_DiscoveredTarget structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

