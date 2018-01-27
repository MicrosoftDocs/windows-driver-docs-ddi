---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_ISOLATION
title: _NDIS_SWITCH_PORT_PROPERTY_ISOLATION
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_ISOLATION structure is used to specify the isolation properties for a VM network adapter's port.
old-location: netvista\ndis_switch_port_property_isolation.htm
old-project: netvista
ms.assetid: 142AF97B-601E-44FB-8548-90CB152B8760
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: *PNDIS_SWITCH_PORT_PROPERTY_ISOLATION, NDIS_SWITCH_PORT_PROPERTY_ISOLATION, PNDIS_SWITCH_PORT_PROPERTY_ISOLATION structure pointer [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_SWITCH_PORT_PROPERTY_ISOLATION, NDIS_SWITCH_PORT_PROPERTY_ISOLATION structure [Network Drivers Starting with Windows Vista], netvista.ndis_switch_port_property_isolation, PNDIS_SWITCH_PORT_PROPERTY_ISOLATION, ntddndis/NDIS_SWITCH_PORT_PROPERTY_ISOLATION, _NDIS_SWITCH_PORT_PROPERTY_ISOLATION
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntddndis.h
apiname: 
-	NDIS_SWITCH_PORT_PROPERTY_ISOLATION
product: Windows
targetos: Windows
req.typenames: *PNDIS_SWITCH_PORT_PROPERTY_ISOLATION, NDIS_SWITCH_PORT_PROPERTY_ISOLATION
---

# _NDIS_SWITCH_PORT_PROPERTY_ISOLATION structure


## -description


The <b>NDIS_SWITCH_PORT_PROPERTY_ISOLATION</b> structure is used to specify the isolation properties for a VM network adapter's port.


## -syntax


````
typedef struct _NDIS_SWITCH_PORT_PROPERTY_ISOLATION {
  NDIS_OBJECT_HEADER  Header;
  ULONG               Flags;
  NDIS_ISOLATION_MODE IsolationMode;
  BOOLEAN             AllowUntaggedTraffic;
  UINT32              DefaultIsolationId;
} NDIS_SWITCH_PORT_PROPERTY_ISOLATION, *PNDIS_SWITCH_PORT_PROPERTY_ISOLATION;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_ISOLATION</b>  structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_ISOLATION</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 




### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field IsolationMode

An <a href="..\ntddndis\ne-ntddndis-_ndis_isolation_mode.md">NDIS_ISOLATION_MODE</a> enumeration value that specifies the isolation mode.


### -field AllowUntaggedTraffic

Specifies whether the VM network adapter port is allowed to send or receive untagged packets. If untagged packets are allowed, the VM network adapter miniport driver tags untagged packets with the default isolation ID specified by the <b>DefaultIsolationId</b> member. Otherwise, the miniport driver drops them.


### -field DefaultIsolationId

The default isolation ID that is applied to tagged packets if the <b>AllowUntaggedTraffic</b> member is <b>TRUE</b>.


##### - Header.NDIS_SWITCH_PORT_PROPERTY_ISOLATION_REVISION_1

Original version for NDIS 6.40 and later.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_ISOLATION_REVISION_1</b>.


## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_isolation_parameters.md">NDIS_ISOLATION_PARAMETERS</a>

<a href="..\ntddndis\ne-ntddndis-_ndis_isolation_mode.md">NDIS_ISOLATION_MODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_PROPERTY_ISOLATION structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

