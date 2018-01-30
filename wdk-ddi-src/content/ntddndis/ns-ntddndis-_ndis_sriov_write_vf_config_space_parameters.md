---
UID: NS:ntddndis._NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS
title: "_NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS"
author: windows-driver-content
description: The NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure specifies the parameters for a write operation on the PCI Express (PCIe) configuration space of a network adapter's Virtual Function (VF).
old-location: netvista\ndis_sriov_write_vf_config_space_parameters.htm
old-project: netvista
ms.assetid: f5f8959f-edde-4d45-b93c-8f5acb08ec98
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], netvista.ndis_sriov_write_vf_config_space_parameters, NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, ntddndis/PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure [Network Drivers Starting with Windows Vista], ntddndis/NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, *PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, _NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
-	NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS"
---

# _NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure


## -description


The <b>NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS</b> structure specifies the parameters for a write operation on the PCI Express (PCIe) configuration space  of a network adapter's Virtual Function (VF).


## -syntax


````
typedef struct _NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS {
  NDIS_OBJECT_HEADER     Header;
  NDIS_SRIOV_FUNCTION_ID VFId;
  ULONG                  Offset;
  ULONG                  Length;
  ULONG                  BufferOffset;
} NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, *PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 




#### NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS_REVISION_1.


### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.
<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div><div> </div>

### -field Offset

A ULONG value that specifies the offset within the PCI configuration space of the VF in which data will be written.


### -field Length

A ULONG value that specifies the length, in units of bytes, of the write operation.


### -field BufferOffset

A ULONG value that specifies the offset, in units of bytes, from the beginning of this structure to a buffer that contains the data to be written to the PCI configuration space of the VF.


## -remarks


 The <b>NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS</b> structure is used in an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451925">OID_SRIOV_WRITE_VF_CONFIG_SPACE</a>.



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451925">OID_SRIOV_WRITE_VF_CONFIG_SPACE</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

