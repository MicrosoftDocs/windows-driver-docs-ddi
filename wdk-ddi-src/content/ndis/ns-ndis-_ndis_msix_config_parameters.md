---
UID: NS:ndis._NDIS_MSIX_CONFIG_PARAMETERS
title: "_NDIS_MSIX_CONFIG_PARAMETERS"
author: windows-driver-content
description: The NDIS_MSIX_CONFIG_PARAMETERS structure defines a requested configuration operation and specifies the parameters that are required for that particular operation.
old-location: netvista\ndis_msix_config_parameters.htm
old-project: netvista
ms.assetid: 52c3238f-4d3a-4241-95bf-630e57e8a6e1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/PNDIS_MSIX_CONFIG_PARAMETERS, ndis_msix_ref_01a237b1-bb32-4aad-8552-b36b66141061.xml, ndis/NDIS_MSIX_CONFIG_PARAMETERS, PNDIS_MSIX_CONFIG_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], NDIS_MSIX_CONFIG_PARAMETERS, *PNDIS_MSIX_CONFIG_PARAMETERS, PNDIS_MSIX_CONFIG_PARAMETERS, netvista.ndis_msix_config_parameters, _NDIS_MSIX_CONFIG_PARAMETERS, NDIS_MSIX_CONFIG_PARAMETERS structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_MSIX_CONFIG_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_MSIX_CONFIG_PARAMETERS, *PNDIS_MSIX_CONFIG_PARAMETERS
---

# _NDIS_MSIX_CONFIG_PARAMETERS structure


## -description


The NDIS_MSIX_CONFIG_PARAMETERS structure defines a requested configuration operation and specifies
  the parameters that are required for that particular operation.


## -syntax


````
typedef struct _NDIS_MSIX_CONFIG_PARAMETERS {
  NDIS_OBJECT_HEADER        Header;
  NDIS_MSIX_TABLE_OPERATION ConfigOperation;
  ULONG                     TableEntry;
  ULONG                     MessageNumber;
} NDIS_MSIX_CONFIG_PARAMETERS, *PNDIS_MSIX_CONFIG_PARAMETERS;
````


## -struct-fields




#### - Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MSIX_CONFIG_PARAMETERS structure. The miniport driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_MSIX_CONFIG_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MSIX_CONFIG_PARAMETERS_REVISION_1.


#### - ConfigOperation

The requested configuration operation for a MSI-X table entry. This operation is specified as one
     of the values from the 
     <mshelp:link keywords="netvista.ndis_msix_table_operation" tabindex="0"><b>
     NDIS_MSIX_TABLE_OPERATION</b></mshelp:link> enumeration.


#### - TableEntry

The MSI-X table entry index.


#### - MessageNumber

The MSI-X message number that is assigned to the device. This value is required for the 
     <b>NdisMSIXTableConfigSetTableEntry</b> operation. This parameter is not used for the 
     <b>NdisMSIXTableConfigMaskTableEntry</b> or 
     <b>NdisMSIXTableConfigUnmaskTableEntry</b> operations.


## -remarks


To mask, unmask, or map MSI-X table entries, an NDIS driver passes the NDIS_MSIX_CONFIG_PARAMETERS
    structure to the 
    <mshelp:link keywords="netvista.ndismconfigmsixtableentry" tabindex="0"><b>
    NdisMConfigMSIXTableEntry</b></mshelp:link> function. NDIS_MSIX_CONFIG_PARAMETERS defines a requested configuration
    operation and specifies the parameters that are required for that operation.



## -see-also

<a href="..\ndis\nf-ndis-ndismconfigmsixtableentry.md">NdisMConfigMSIXTableEntry</a>

<a href="..\ndis\ne-ndis-_ndis_msix_table_config.md">NDIS_MSIX_TABLE_OPERATION</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MSIX_CONFIG_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

