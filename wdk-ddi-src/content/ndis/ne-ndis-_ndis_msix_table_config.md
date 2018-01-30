---
UID: NE:ndis._NDIS_MSIX_TABLE_CONFIG
title: "_NDIS_MSIX_TABLE_CONFIG"
author: windows-driver-content
description: The NDIS_MSIX_TABLE_OPERATION enumeration identifies the type of MSI-X configuration operation.
old-location: netvista\ndis_msix_table_operation.htm
old-project: netvista
ms.assetid: 7d1a4bb6-5db8-48b0-9be3-7468360951a1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisMSIXTableConfigMaskTableEntry, ndis/NdisMSIXTableConfigSetTableEntry, NdisMSIXTableConfigMax, _NDIS_MSIX_TABLE_CONFIG, NdisMSIXTableConfigSetTableEntry, ndis/NdisMSIXTableConfigUnmaskTableEntry, NdisMSIXTableConfigUnmaskTableEntry, PNDIS_MSIX_TABLE_OPERATION enumeration pointer [Network Drivers Starting with Windows Vista], ndis_msix_ref_b315600c-7d23-4251-bcdb-560c46d5fa79.xml, PNDIS_MSIX_TABLE_OPERATION, netvista.ndis_msix_table_operation, ndis/PNDIS_MSIX_TABLE_OPERATION, ndis/NdisMSIXTableConfigMax, ndis/NDIS_MSIX_TABLE_OPERATION, NDIS_MSIX_TABLE_OPERATION enumeration [Network Drivers Starting with Windows Vista], NDIS_MSIX_TABLE_OPERATION, ndis/NdisMSIXTableConfigMaskTableEntry, *PNDIS_MSIX_TABLE_OPERATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
-	ndis.h
apiname:
-	NDIS_MSIX_TABLE_OPERATION
product: Windows
targetos: Windows
req.typenames: NDIS_MSIX_TABLE_OPERATION, *PNDIS_MSIX_TABLE_OPERATION
---

# _NDIS_MSIX_TABLE_CONFIG enumeration


## -description


The NDIS_MSIX_TABLE_OPERATION enumeration identifies the type of MSI-X configuration
  operation.


## -syntax


````
typedef enum _NDIS_MSIX_TABLE_CONFIG { 
  NdisMSIXTableConfigSetTableEntry,
  NdisMSIXTableConfigMaskTableEntry,
  NdisMSIXTableConfigUnmaskTableEntry,
  NdisMSIXTableConfigMax
} NDIS_MSIX_TABLE_OPERATION, *PNDIS_MSIX_TABLE_OPERATION;
````


## -enum-fields




### -field NdisMSIXTableConfigSetTableEntry

The MSI-X table entry should be mapped to an MSI-X message that the bus driver allocated to the
     device.


### -field NdisMSIXTableConfigMaskTableEntry

The interrupts from an MSI-X table entry source should be masked.


### -field NdisMSIXTableConfigUnmaskTableEntry

The interrupts from an MSI-X table entry source should be unmasked.


### -field NdisMSIXTableConfigMax

The number of enumeration values in NDIS_MSIX_TABLE_OPERATION.


## -remarks


The NDIS_MSIX_TABLE_OPERATION enumeration is used in the 
    <mshelp:link keywords="netvista.ndis_msix_config_parameters" tabindex="0"><b>
    NDIS_MSIX_CONFIG_PARAMETERS</b></mshelp:link> structure.



## -see-also

<a href="..\ndis\ns-ndis-_ndis_msix_config_parameters.md">NDIS_MSIX_CONFIG_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MSIX_TABLE_OPERATION enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

