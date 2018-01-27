---
UID: NS:iscsifnd._ISCSI_DiscoveredTarget2
title: _ISCSI_DiscoveredTarget2
author: windows-driver-content
description: The ISCSI_DiscoveredTarget2 structure contains information that is related to a discovered target device.
old-location: storage\iscsi_discoveredtarget2.htm
old-project: storage
ms.assetid: 77fb2942-5836-44cb-9a5e-e45f6a022264
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ISCSI_DiscoveredTarget2 structure [Storage Devices], storage.iscsi_discoveredtarget2, *PISCSI_DiscoveredTarget2, PISCSI_DiscoveredTarget2 structure pointer [Storage Devices], _ISCSI_DiscoveredTarget2, structs-iSCSI_5a9fcec3-8447-441c-a2d9-1416c1bbe07e.xml, PISCSI_DiscoveredTarget2, ISCSI_DiscoveredTarget2, iscsifnd/ISCSI_DiscoveredTarget2, iscsifnd/PISCSI_DiscoveredTarget2
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
-	ISCSI_DiscoveredTarget2
product: Windows
targetos: Windows
req.typenames: *PISCSI_DiscoveredTarget2, ISCSI_DiscoveredTarget2
---

# _ISCSI_DiscoveredTarget2 structure


## -description


The ISCSI_DiscoveredTarget2 structure contains information that is related to a discovered target device. 


## -syntax


````
typedef struct _ISCSI_DiscoveredTarget2 {
  ULONG                              TargetPortalGroupCount;
  WCHAR                              TargetName[223 + 1];
  WCHAR                              TargetAlias[255 + 1];
  ISCSI_DiscoveredTargetPortalGroup2 TargetDiscoveredPortalGroups[1];
} ISCSI_DiscoveredTarget2, *PISCSI_DiscoveredTarget2;
````


## -struct-fields




### -field TargetPortalGroupCount

The number of portal groups that are associated with the target.


### -field TargetName

A name for the target that uniquely identifies the target anywhere in the world. For more information about how to specify this name, see the <i>iSCSI </i>specification that is published by the Internet Engineering Task Force (IETF) of the IP storage working group. 


### -field TargetAlias

The human-readable name or description that is assigned to the target device by its host operating system. You can use this name in user interfaces, but it is not unique, so you should not use it in authentication decisions. 


### -field TargetDiscoveredPortalGroups

A variable-length array of <a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportalgroup2.md">ISCSI_DiscoveredTargetPortalGroup2</a> structures that contains information about the portal groups that the initiator can use to connect to the target.


## -remarks


The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTarget2 structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561505">ISCSI_DiscoveredTarget2 WMI Class</a> in <i>Discover.mof</i>.

The only difference between the ISCSI_DiscoveredTarget2 structure and the <a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtarget.md">ISCSI_DiscoveredTarget</a> structure is that the <b>TargetDiscoveredPortalGroups</b> member of ISCSI_DiscoveredTarget2 is a <a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportalgroup2.md">ISCSI_DiscoveredTargetPortalGroup2</a> structure instead of a <a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportalgroup.md">ISCSI_DiscoveredTargetPortalGroup</a> structure.  



## -see-also

<a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtarget.md">ISCSI_DiscoveredTarget</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561527">ISCSI_DiscoveredTarget WMI Class</a>

<a href="..\iscsifnd\ns-iscsifnd-_iscsi_discoveredtargetportalgroup.md">ISCSI_DiscoveredTargetPortalGroup</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561505">ISCSI_DiscoveredTarget2 WMI Class</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_DiscoveredTarget2 structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

