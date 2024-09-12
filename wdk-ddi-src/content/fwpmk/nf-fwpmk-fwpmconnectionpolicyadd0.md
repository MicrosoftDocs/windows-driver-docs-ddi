---
UID: NF:fwpmk.FwpmConnectionPolicyAdd0
tech.root: netvista
title: FwpmConnectionPolicyAdd0
ms.date: 06/04/2024
targetos: Windows
description: The FwpmConnectionPolicyAdd0API function configures routing policies for outbound connections.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fwpmk.h
req.idl: 
req.include-header: 
req.irql: <= PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: fwpkclnt.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fwpmk.h
api_name:
 - FwpmConnectionPolicyAdd0
f1_keywords:
 - FwpmConnectionPolicyAdd0
 - fwpmk/FwpmConnectionPolicyAdd0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmConnectionPolicyAdd0
---

## -description

The **FwpmConnectionPolicyAdd0API** function configures routing policies for outbound connections.

## -parameters

### -param engineHandle [in]

A handle to an open session with the filter engine. To open a session with the filter engine, call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**.

### -param connectionPolicy [in]

The state associated with a provider context.

### -param ipVersion [in]

IP version of the traffic.

### -param weight [in]

Specifies the weight that this Trusted Intermediary Agent (TIA) should be given compared to any peers.

### -param numFilterConditions [in]

The number of elements in *filterConditions*.

### -param filterConditions [in, reads(numFilterConditions)]

A filter condition that must be true for the action to be taken.

Of the possible match conditions (see [Filtering condition identifiers](/windows/win32/fwp/filtering-condition-identifiers-)), the ones in the following list are supported by **FwpmConnectionPolicyAdd0**. Set these values in **FWPM_FILTER_CONDITION0::fieldKey**.

- **FWPM_CONDITION_ALE_APP_ID**
- **FWPM_CONDITION_ALE_USER_ID**
- **FWPM_CONDITION_IP_LOCAL_ADDRESS**
- **FWPM_CONDITION_IP_LOCAL_ADDRESS_TYPE**
- **FWPM_CONDITION_IP_LOCAL_PORT**
- **FWPM_CONDITION_IP_PROTOCOL**
- **FWPM_CONDITION_IP_REMOTE_ADDRESS**
- **FWPM_CONDITION_IP_DESTINATION_ADDRESS_TYPE**
- **FWPM_CONDITION_IP_REMOTE_PORT**
- **FWPM_CONDITION_FLAGS**
- **FWPM_CONDITION_ALE_ORIGINAL_APP_ID**
- **FWPM_CONDITION_ALE_PACKAGE_ID**
- **FWPM_CONDITION_COMPARTMENT_ID**

### -param sd [in, optional]

The security information.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The routing policy was successfully configured. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

The TCP/IP stack supports destination address-based routing for outbound connections. FwpmConnectionPolicyAdd0API allows you to configure more expressive routing policies for outbound connections, and thereby to enable more complex scenarios such as source address-based routing, process-based routing, port-based routing, and others. A connection policy consists of an array of match conditions, an array of route settings, and an associated weight. You can configure multiple policies, and they are evaluated based on their configured weights for an outbound connection (a higher weight takes precedence). The route setting of the first policy whose conditions (ANDed) matches the outbound connection is applied.

These are the supported route settings (see [FWP_NETWORK_CONNECTION_POLICY_SETTING_TYPE](/windows/win32/api/fwptypes/ne-fwptypes-fwp_network_connection_policy_setting_type)):

**FWP_NETWORK_CONNECTION_POLICY_SOURCE_ADDRESS**. The source address to use for the connection. The value should be a **FWP_UINT32** for an IPv4 address, and a **FWP_BYTE_ARRAY16_TYPE** for an IPv6 address.

**FWP_NETWORK_CONNECTION_POLICY_NEXT_HOP_INTERFACE**. The LUID of the outgoing interface to use for the connection. The value should be a **FWP_UINT64**.

**FWP_NETWORK_CONNECTION_POLICY_NEXT_HOP**. The nexthop address (or gateway) to use for the connection. The value should be a **FWP_UINT32** for an IPv4 address, and a **FWP_BYTE_ARRAY16_TYPE** for an IPv6 address.

## -see-also

- [FWP_NETWORK_CONNECTION_POLICY_SETTING_TYPE](/windows/win32/api/fwptypes/ne-fwptypes-fwp_network_connection_policy_setting_type)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
