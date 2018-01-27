---
UID: NS:ntddndis._NDIS_PM_COUNTED_STRING
title: _NDIS_PM_COUNTED_STRING
author: windows-driver-content
description: The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in power management structures.
old-location: netvista\ndis_pm_counted_string.htm
old-project: netvista
ms.assetid: 070ee8e2-80ed-4380-89ac-bfb5db2bcf7e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_PM_COUNTED_STRING, NDIS_PM_COUNTED_STRING, ntddndis/NDIS_PM_COUNTED_STRING, miniport_power_management_ref_baaff596-1c2a-4cfc-865a-bb3f55988218.xml, _NDIS_PM_COUNTED_STRING, PNDIS_PM_COUNTED_STRING structure pointer [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_PM_COUNTED_STRING, *PNDIS_PM_COUNTED_STRING, netvista.ndis_pm_counted_string, NDIS_PM_COUNTED_STRING structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ntddndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
-	ntddndis.h
apiname: 
-	NDIS_PM_COUNTED_STRING
product: Windows
targetos: Windows
req.typenames: NDIS_PM_COUNTED_STRING, *PNDIS_PM_COUNTED_STRING
---

# _NDIS_PM_COUNTED_STRING structure


## -description


The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in power management
  structures.


## -syntax


````
typedef struct _NDIS_PM_COUNTED_STRING {
  USHORT Length;
  WCHAR  String[NDIS_PM_MAX_STRING_SIZE + 1];
} NDIS_PM_COUNTED_STRING, *PNDIS_PM_COUNTED_STRING;
````


## -struct-fields




### -field Length

The length, in bytes, of the string.


### -field String

A WCHAR array that contains a NULL-terminated string that is limited to a maximum size of
     NDIS_PM_MAX_STRING_SIZE.


## -remarks


The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_pm_protocol_offload.md">NDIS_PM_PROTOCOL_OFFLOAD</a> and 
    <a href="..\ntddndis\ns-ntddndis-_ndis_pm_wol_pattern.md">NDIS_PM_WOL_PATTERN</a> power management
    structures to define name strings.



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_pm_protocol_offload.md">NDIS_PM_PROTOCOL_OFFLOAD</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_pm_wol_pattern.md">NDIS_PM_WOL_PATTERN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PM_COUNTED_STRING structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

