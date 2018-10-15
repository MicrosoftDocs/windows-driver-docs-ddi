---
UID: NE:iscsicfg.PISCSI_NIC_LINKSTATE
title: "*PISCSI_NIC_LINKSTATE"
author: windows-driver-content
description: The ISCSI_NIC_LINKSTATE enumeration indicates whether a port is connected to the network or not.
old-location: storage\iscsi_nic_linkstate.htm
tech.root: storage
ms.assetid: e373b1dd-54bd-429c-a5b9-9f8df546c185
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PISCSI_NIC_LINKSTATE, ISCSI_NIC_LINKSTATE, ISCSI_NIC_LINKSTATE enumeration [Storage Devices], ISCSI_NIC_LINKSTATE_CONNECTED, ISCSI_NIC_LINKSTATE_DISCONNECTED, PISCSI_NIC_LINKSTATE, PISCSI_NIC_LINKSTATE enumeration pointer [Storage Devices], iscsicfg/ISCSI_NIC_LINKSTATE, iscsicfg/ISCSI_NIC_LINKSTATE_CONNECTED, iscsicfg/ISCSI_NIC_LINKSTATE_DISCONNECTED, iscsicfg/PISCSI_NIC_LINKSTATE, storage.iscsi_nic_linkstate, structs-iSCSI_23ddbeb6-19d4-49f2-b61f-00ea2e5ef0a8.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iscsicfg.h
req.include-header: Iscsicfg.h
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
-	iscsicfg.h
api_name:
-	ISCSI_NIC_LINKSTATE
product:
- Windows
targetos: Windows
req.typenames: ISCSI_NIC_LINKSTATE, *PISCSI_NIC_LINKSTATE
---

# *PISCSI_NIC_LINKSTATE enumeration


## -description


The ISCSI_NIC_LINKSTATE enumeration indicates whether a port is connected to the network or not.


## -syntax


```
typedef enum  {
  ISCSI_NIC_LINKSTATE_DISCONNECTED  = 0,
  ISCSI_NIC_LINKSTATE_CONNECTED     = 1
} ISCSI_NIC_LINKSTATE, *PISCSI_NIC_LINKSTATE;
```


## -enum-fields




### -field ISCSI_NIC_LINKSTATE_DISCONNECTED

A network port is disconnected from the network.


### -field ISCSI_NIC_LINKSTATE_CONNECTED

A network port is connected to the network.


## -remarks



The ISCSI_NIC_LINKSTATE enumeration is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563083">MSiSCSI_NICConfig WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563083">MSiSCSI_NICConfig WMI Class</a>



<a href="..\iscsicfg\ns-iscsicfg-_msiscsi_nicconfig.md">MSiSCSI_NICConfig</a>



 

 


