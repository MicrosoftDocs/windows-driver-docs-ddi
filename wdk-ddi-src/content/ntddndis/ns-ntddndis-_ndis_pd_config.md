---
UID: NS:ntddndis._NDIS_PD_CONFIG
title: "_NDIS_PD_CONFIG"
author: windows-driver-content
description: This structure holds configuration data for the PD provider.
old-location: netvista\ndis_pd_config.htm
old-project: netvista
ms.assetid: 2B010641-4CFA-40B6-AB77-BE9F85347134
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_PD_CONFIG, NDIS_PD_CONFIG structure [Network Drivers Starting with Windows Vista], _NDIS_PD_CONFIG, netvista.ndis_pd_config, ntddndis/NDIS_PD_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	ntddndis.h
apiname:
-	NDIS_PD_CONFIG
product: Windows
targetos: Windows
req.typenames: NDIS_PD_CONFIG
---

# _NDIS_PD_CONFIG structure


## -description


This structure holds configuration data for the PD provider.


## -syntax


````
typedef struct _NDIS_PD_CONFIG {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  BOOLEAN            Enabled;
  ULONG              CapabilitiesOffset;
                     CapabilitiesSize;
} NDIS_PD_CONFIG;
````


## -struct-fields




### -field Header

The <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_CONFIG</b> structure. Set the members of this structure as follows:
<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_CONFIG_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_CONFIG_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0.


### -field Enabled

A <b>BOOLEAN</b> value that is set to <b>TRUE</b> if the PDPI provider's  PacketDirect capability is enabled. Otherwise, this member is <b>FALSE</b>.


### -field CapabilitiesOffset

If the <b>CapabilitiesSize</b> member is greater than zero, this is a <b>ULONG</b>-aligned pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_pd_capabilities.md">NDIS_PD_CAPABILITIES</a> structure.


### -field CapabilitiesSize

If this member is greater than zero, it contains the size of the <a href="..\ntddndis\ns-ntddndis-_ndis_pd_capabilities.md">NDIS_PD_CAPABILITIES</a> structure that the <b>CapabilitiesOffset</b> member points to.


## -remarks


This structure must be aligned on an 8-byte boundary.



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_CONFIG structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

