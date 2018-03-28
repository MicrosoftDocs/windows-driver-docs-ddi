---
UID: NA:mpiodisk
ms.assetid: b30b7e2a-2c2b-3296-ae03-7e4d3e36339d
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Mpiodisk.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Mpiodisk.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_DSM_Load_Balance_Policy structure](ns-mpiodisk-_dsm_load_balance_policy.md) | The DSM_Load_Balance_Policy structure is used to represent a load balance policy that is applied to a LUN. |
| [_DSM_Load_Balance_Policy_V2 structure](ns-mpiodisk-_dsm_load_balance_policy_v2.md) | The DSM_Load_Balance_Policy_V2 structure is used to represent a load balance policy that is applied to a LUN. |
| [_DSM_QueryLBPolicy structure](ns-mpiodisk-_dsm_querylbpolicy.md) | The DSM_QueryLBPolicy structure is used to query a LUN's current load balance policy. |
| [_DSM_QueryLBPolicy_V2 structure](ns-mpiodisk-_dsm_querylbpolicy_v2.md) | The DSM_QueryLBPolicy_V2 structure is used to query a LUN's current load balance policy. It is basically the same as the DSM_QueryLBPolicy structure except that it returns the load balance information by using the DSM_Load_Balance_Policy_V2 structure. |
| [_DSM_QuerySupportedLBPolicies structure](ns-mpiodisk-_dsm_querysupportedlbpolicies.md) | The DSM_QuerySupportedLBPolicies structure is used to query the list of load balance policies that are supported on the LUN. |
| [_DSM_QuerySupportedLBPolicies_V2 structure](ns-mpiodisk-_dsm_querysupportedlbpolicies_v2.md) | The DSM_QuerySupportedLBPolicies_V2 structure is used to query the list of load balance policies that are supported on the LUN. |
| [_DSM_QueryUniqueId structure](ns-mpiodisk-_dsm_queryuniqueid.md) | The DSM_QueryUniqueId structure is used to query the DSM for a unique identifier. |
| [_DsmSetLoadBalancePolicyALUA_IN structure](ns-mpiodisk-_dsmsetloadbalancepolicyalua_in.md) | The DsmSetLoadBalancePolicyALUA_IN structure provides the input parameter for the DsmSetLoadBalancePolicyALUA method. |
| [_DsmSetLoadBalancePolicyALUA_OUT structure](ns-mpiodisk-_dsmsetloadbalancepolicyalua_out.md) | The DsmSetLoadBalancePolicyALUA_OUT structure reports the output of the DsmSetLoadBalancePolicyALUA method. |
| [_DsmSetLoadBalancePolicy_IN structure](ns-mpiodisk-_dsmsetloadbalancepolicy_in.md) | The DsmSetLoadBalancePolicy_IN structure provides an input parameter to the DsmSetLoadBalancePolicy method. |
| [_DsmSetLoadBalancePolicy_OUT structure](ns-mpiodisk-_dsmsetloadbalancepolicy_out.md) | The DsmSetLoadBalancePolicy_OUT structure reports the output parameter of the DsmSetLoadBalancePolicy method. |
| [_MPIO_DEVINSTANCE_HEALTH_CLASS structure](ns-mpiodisk-_mpio_devinstance_health_class.md) | The MPIO_DEVINSTANCE_HEALTH_CLASS structure holds the health information for a instance of a device exposed through the specified path identifiers. |
| [_MPIO_DEVINSTANCE_HEALTH_INFO structure](ns-mpiodisk-_mpio_devinstance_health_info.md) | The MPIO_DEVINSTANCE_HEALTH_INFO structure is used to query the available health information for every instance of a multi-path disk on each of the paths through which it is exposed. |
| [_MPIO_DSM_Path structure](ns-mpiodisk-_mpio_dsm_path.md) | The MPIO_DSM_Path structure is used to represent the DSM's definition of a path. |
| [_MPIO_DSM_Path_V2 structure](ns-mpiodisk-_mpio_dsm_path_v2.md) | The MPIO_DSM_Path_V2 structure is used to represent the DSM's definition of a path. It is a superset of the previously existing MPIO_DSM_Path class. |
| [_MPIO_GET_DESCRIPTOR structure](ns-mpiodisk-_mpio_get_descriptor.md) | The MPIO_GET_DESCRIPTOR structure is used to query for LUN instances that correspond to various paths. |
| [_PDOSCSI_ADDR structure](ns-mpiodisk-_pdoscsi_addr.md) | The PDOSCSI_ADDR structure is used to represent a SCSI address. |
| [_PDO_INFORMATION structure](ns-mpiodisk-_pdo_information.md) | The PDO_INFORMATION structure represents a device-path pairing, which is an instance of a LUN through a particular path. |
