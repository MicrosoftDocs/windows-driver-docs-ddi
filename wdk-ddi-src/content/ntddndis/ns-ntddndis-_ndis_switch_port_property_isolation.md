---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_ISOLATION
title: "_NDIS_SWITCH_PORT_PROPERTY_ISOLATION"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_ISOLATION structure is used to specify the isolation properties for a VM network adapter's port.
old-location: netvista\ndis_switch_port_property_isolation.htm
old-project: netvista
ms.assetid: 142AF97B-601E-44FB-8548-90CB152B8760
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_SWITCH_PORT_PROPERTY_ISOLATION, NDIS_SWITCH_PORT_PROPERTY_ISOLATION, NDIS_SWITCH_PORT_PROPERTY_ISOLATION structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PROPERTY_ISOLATION, PNDIS_SWITCH_PORT_PROPERTY_ISOLATION structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PROPERTY_ISOLATION, netvista.ndis_switch_port_property_isolation, ntddndis/NDIS_SWITCH_PORT_PROPERTY_ISOLATION, ntddndis/PNDIS_SWITCH_PORT_PROPERTY_ISOLATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.40 and later.
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
-	Ntddndis.h
api_name:
-	NDIS_SWITCH_PORT_PROPERTY_ISOLATION
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PROPERTY_ISOLATION, *PNDIS_SWITCH_PORT_PROPERTY_ISOLATION
---

# _NDIS_SWITCH_PORT_PROPERTY_ISOLATION structure


## -description


The <b>NDIS_SWITCH_PORT_PROPERTY_ISOLATION</b> structure is used to specify the isolation properties for a VM network adapter's port.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_ISOLATION</b>  structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_ISOLATION</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_PORT_PROPERTY_ISOLATION_REVISION_1

Original version for NDIS 6.40 and later.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_ISOLATION_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field IsolationMode

An <a href="https://msdn.microsoft.com/library/windows/hardware/dn383677">NDIS_ISOLATION_MODE</a> enumeration value that specifies the isolation mode.


### -field AllowUntaggedTraffic

Specifies whether the VM network adapter port is allowed to send or receive untagged packets. If untagged packets are allowed, the VM network adapter miniport driver tags untagged packets with the default isolation ID specified by the <b>DefaultIsolationId</b> member. Otherwise, the miniport driver drops them.


### -field DefaultIsolationId

The default isolation ID that is applied to tagged packets if the <b>AllowUntaggedTraffic</b> member is <b>TRUE</b>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn383677">NDIS_ISOLATION_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn383679">NDIS_ISOLATION_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
 

 

