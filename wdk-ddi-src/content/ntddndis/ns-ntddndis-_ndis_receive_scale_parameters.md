---
UID: NS:ntddndis._NDIS_RECEIVE_SCALE_PARAMETERS
title: _NDIS_RECEIVE_SCALE_PARAMETERS (ntddndis.h)
description: The NDIS_RECEIVE_SCALE_PARAMETERS structure specifies the receive side scaling (RSS) parameters for a miniport adapter.
old-location: netvista\ndis_receive_scale_parameters.htm
tech.root: netvista
ms.assetid: 0d51042e-06b4-4105-889f-84a368e5735a
ms.date: 09/08/2020
keywords: ["NDIS_RECEIVE_SCALE_PARAMETERS structure"]
ms.keywords: "*PNDIS_RECEIVE_SCALE_PARAMETERS, NDIS_RECEIVE_SCALE_PARAMETERS, NDIS_RECEIVE_SCALE_PARAMETERS structure [Network Drivers Starting with Windows Vista], NDIS_RSS_PARAM_FLAG_BASE_CPU_UNCHANGED, NDIS_RSS_PARAM_FLAG_DISABLE_RSS, NDIS_RSS_PARAM_FLAG_HASH_INFO_UNCHANGED, NDIS_RSS_PARAM_FLAG_HASH_KEY_UNCHANGED, NDIS_RSS_PARAM_FLAG_ITABLE_UNCHANGED, PNDIS_RECEIVE_SCALE_PARAMETERS, PNDIS_RECEIVE_SCALE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_SCALE_PARAMETERS, netvista.ndis_receive_scale_parameters, ntddndis/NDIS_RECEIVE_SCALE_PARAMETERS, ntddndis/PNDIS_RECEIVE_SCALE_PARAMETERS, receive_scaling_structures_ref_1055bbcb-da8b-4ee1-bd03-55abfa79b5ab.xml"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.typenames: NDIS_RECEIVE_SCALE_PARAMETERS, *PNDIS_RECEIVE_SCALE_PARAMETERS
f1_keywords:
 - _NDIS_RECEIVE_SCALE_PARAMETERS
 - ntddndis/_NDIS_RECEIVE_SCALE_PARAMETERS
 - PNDIS_RECEIVE_SCALE_PARAMETERS
 - ntddndis/PNDIS_RECEIVE_SCALE_PARAMETERS
 - NDIS_RECEIVE_SCALE_PARAMETERS
 - ntddndis/NDIS_RECEIVE_SCALE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_RECEIVE_SCALE_PARAMETERS
---

# _NDIS_RECEIVE_SCALE_PARAMETERS structure

## -description

The **NDIS_RECEIVE_SCALE_PARAMETERS** structure specifies the [Receive Side Scaling (RSS)](https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-) parameters for a miniport adapter.
  
### Version Information

## -struct-fields

### -field Header

The [NDIS_OBJECT_HEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header) structure for the **NDIS_RECEIVE_SCALE_PARAMETERS** structure. Set the **Type** member of the structure that **Header** specifies to **NDIS_OBJECT_TYPE_RSS_PARAMETERS**.

* For NDIS  6.60 and later drivers, set the **Revision** member to **NDIS_RECEIVE_SCALE_PARAMETERS_REVISION_3** and the **Size** member to **NDIS_SIZEOF_RECEIVE_SCALE_PARAMETERS_REVISION_3**.

* For NDIS  6.20 and pre-NDIS 6.60 drivers, set the **Revision** member to **NDIS_RECEIVE_SCALE_PARAMETERS_REVISION_2** and the **Size** member to **NDIS_SIZEOF_RECEIVE_SCALE_PARAMETERS_REVISION_2**.

* For NDIS  6.0 drivers, set the **Revision** member to **NDIS_RECEIVE_SCALE_PARAMETERS_REVISION_1** and the **Size** member to **NDIS_SIZEOF_RECEIVE_SCALE_PARAMETERS_REVISION_1**.

### -field Flags

A **USHORT** value that indicates what the miniport driver should do with the receive-scale parameters. The driver can use these flags to quickly determine which parameters have changed and update the RSS settings accordingly.

> [!NOTE]
> The flags which refer to unchanged RSS parameter information are for optimization purposes. If a flag is set,
> no change has been made to the corresponding parameter. If a flag is clear, the corresponding parameter may or
> may not have changed and miniport drivers must compare the new value of the parameter with the current value in
> order to determine a potential change in the parameter.

* In a query request, set this member to zero.

* In a set request, the flags are defined as follows:

| Value | Meaning |
| --- | --- |
| NDIS_RSS_PARAM_FLAG_BASE_CPU_UNCHANGED | The **BaseCpuNumber** member has not changed. |
| NDIS_RSS_PARAM_FLAG_HASH_INFO_UNCHANGED | The **HashInformation** member has not changed. The hash information includes the hash types and hash function. |
| NDIS_RSS_PARAM_FLAG_ITABLE_UNCHANGED | The indirection table and associated data members have not changed. |
| NDIS_RSS_PARAM_FLAG_HASH_KEY_UNCHANGED | The secret key and associated data members have not changed. |
| NDIS_RSS_PARAM_FLAG_DISABLE_RSS | If this flag is set, the miniport driver should ignore all of the other flags and settings and disable RSS on the NIC. |
| NDIS_RSS_PARAM_FLAG_DEFAULT_PROCESSOR_UNCHANGED | If this flag is set, the **DefaultProcessorNumber** has not changed. |

### -field BaseCpuNumber

The lowest number CPU to use for RSS. Because this value is incorporated into the indirection table, set **BaseCpuNumber** to zero.

### -field HashInformation

In a set request, this member is the hash type and hash function that the NIC should use to compute the hash   values for the incoming packets. If the hash function that is specified within the **HashInformation** member is zero, RSS is disabled.

In a query request, this member is the hash type and hash function that the NIC is using.

Overlying drivers and NDIS can use the [NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-rss-hash-info-from-type-and-func) macro to combine the hash type and hash function into hash information and set the **HashInformation** member.

Miniport drivers can use the [NDIS_RSS_HASH_TYPE_FROM_HASH_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-rss-hash-info-from-type-and-func) macro to get the hash type from **HashInformation** and the [NDIS_RSS_HASH_FUNC_FROM_HASH_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-rss-hash-info-from-type-and-func) macro to get the hash function.

### -field IndirectionTableSize

The size of the indirection table, in bytes. The upper layer driver that sets the RSS parameters, must ensure that the number of entries in the indirection table is a power of 2.

### -field IndirectionTableOffset

The offset of the indirection table from the beginning of the **NDIS_RECEIVE_SCALE_PARAMETERS** structure. Use this offset to get the indirection table.

### -field HashSecretKeySize

The size of the secret key array of the hash function, in bytes. The size of the array is 40 bytes for NdisHashFunctionToeplitz.

### -field HashSecretKeyOffset

The offset of the secret key array of the hash function from the beginning of the   **NDIS_RECEIVE_SCALE_PARAMETERS** structure. Use this offset to get the 320-bit (40 bytes) secret key.

* In a set request, the secret key can contain any data that the overlying driver chooses.

* In a query request, the secret key contains the data that the NIC is using.

### -field ProcessorMasksOffset

The offset of an array of processor masks from the beginning of the **NDIS_RECEIVE_SCALE_PARAMETERS**
     structure.

### -field NumberOfProcessorMasks

The number of elements in an array of type [GROUP_AFFINITY](https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity) representing the processors used in the indirection table

### -field ProcessorMasksEntrySize

The size, in bytes, of a processor mask array entry.

### -field DefaultProcessorNumber

When RSS is enabled, specifies the processor that will receive packets where the hash cannot be calculated.

## -remarks

The **NDIS_RECEIVE_SCALE_PARAMETERS** structure defines the [Receive Side Scaling (RSS)](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-receive-side-scaling2) parameters for the [OID_GEN_RECEIVE_SCALE_PARAMETERS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-parameters) OID.

> [!NOTE]
> The indirection table and secret key are appended after the **NDIS_RECEIVE_SCALE_PARAMETERS**
> structure members.

The indirection table has the following version-specific format:

| NDIS Version | Format |
|---|---|
|NDIS 6.20 and later versions | ```PROCESSOR_NUMBER IndirectionTable[IndirectionTableSize/sizeof(PROCESSOR_NUMBER)];```|
|Pre-NDIS 6.20 | ```CCHAR     IndirectionTable[IndirectionTableSize]``` |

NDIS automatically translates the indirection table if there are older and newer drivers in a driver stack.

The miniport driver must examine the indirection table to determine the CPU numbers to associate with hardware queues. If the total number of different CPU numbers that appear in the indirection table is more than the number of hardware queues that the NIC supports, the miniport driver must pick a subset of the CPU numbers from the indirection table. The subset is equal in number to the number of hardware queues.

The miniport driver specified the number of receive queues value in response to   [OID_GEN_RECEIVE_SCALE_CAPABILITIES](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities).

To clear the RSS parameters and disable RSS, NDIS sets the hash function that is specified within the **HashInformation** member is zero. NDIS can also disable RSS by setting the **NDIS_RSS_PARAM_FLAG_DISABLE_RSS** flag in the **NDIS_RECEIVE_SCALE_PARAMETERS** structure.

If RSS is disabled, the miniport driver should handle receive operations without performing RSS operations.

## -see-also

[Receive Side Scaling (RSS)](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-receive-side-scaling2)

[NDIS_OBJECT_HEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header)

[NDIS_RSS_HASH_FUNC_FROM_HASH_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-rss-hash-info-from-type-and-func)

[NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-rss-hash-info-from-type-and-func)

[NDIS_RSS_HASH_TYPE_FROM_HASH_INFO](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-rss-hash-info-from-type-and-func)

[OID_GEN_RECEIVE_SCALE_CAPABILITIES](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities)

[OID_GEN_RECEIVE_SCALE_PARAMETERS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-parameters)
