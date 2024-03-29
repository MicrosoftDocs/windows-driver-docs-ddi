---
UID: NE:iscsicfg.ISCSI_NIC_LINKSTATE
title: ISCSI_NIC_LINKSTATE (iscsicfg.h)
description: The ISCSI_NIC_LINKSTATE enumeration indicates whether a port is connected to the network or not.
old-location: storage\iscsi_nic_linkstate.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ISCSI_NIC_LINKSTATE enumeration"]
ms.keywords: "*PISCSI_NIC_LINKSTATE, ISCSI_NIC_LINKSTATE, ISCSI_NIC_LINKSTATE enumeration [Storage Devices], ISCSI_NIC_LINKSTATE_CONNECTED, ISCSI_NIC_LINKSTATE_DISCONNECTED, PISCSI_NIC_LINKSTATE, PISCSI_NIC_LINKSTATE enumeration pointer [Storage Devices], iscsicfg/ISCSI_NIC_LINKSTATE, iscsicfg/ISCSI_NIC_LINKSTATE_CONNECTED, iscsicfg/ISCSI_NIC_LINKSTATE_DISCONNECTED, iscsicfg/PISCSI_NIC_LINKSTATE, storage.iscsi_nic_linkstate, structs-iSCSI_23ddbeb6-19d4-49f2-b61f-00ea2e5ef0a8.xml"
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
targetos: Windows
req.typenames: ISCSI_NIC_LINKSTATE, *PISCSI_NIC_LINKSTATE
f1_keywords:
 - PISCSI_NIC_LINKSTATE
 - iscsicfg/PISCSI_NIC_LINKSTATE
 - ISCSI_NIC_LINKSTATE
 - iscsicfg/ISCSI_NIC_LINKSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsicfg.h
api_name:
 - PISCSI_NIC_LINKSTATE
 - ISCSI_NIC_LINKSTATE
---

# ISCSI_NIC_LINKSTATE enumeration


## -description

The ISCSI_NIC_LINKSTATE enumeration indicates whether a port is connected to the network or not.

## -enum-fields

### -field ISCSI_NIC_LINKSTATE_DISCONNECTED

A network port is disconnected from the network.

### -field ISCSI_NIC_LINKSTATE_CONNECTED

A network port is connected to the network.

## -remarks

The ISCSI_NIC_LINKSTATE enumeration is used with the <a href="/windows-hardware/drivers/storage/msiscsi-nicconfig-wmi-class">MSiSCSI_NICConfig WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/iscsicfg/ns-iscsicfg-_msiscsi_nicconfig">MSiSCSI_NICConfig</a>



<a href="/windows-hardware/drivers/storage/msiscsi-nicconfig-wmi-class">MSiSCSI_NICConfig WMI Class</a>

