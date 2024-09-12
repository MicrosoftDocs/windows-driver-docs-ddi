---
UID: NF:fwpmk.FwpmEngineSetOption0
tech.root: netvista
title: FwpmEngineSetOption0
ms.date: 06/05/2024
targetos: Windows
description: The FwpmEngineSetOption0 function changes the filter engine settings.
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
 - FwpmEngineSetOption0
f1_keywords:
 - FwpmEngineSetOption0
 - fwpmk/FwpmEngineSetOption0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmEngineSetOption0
---

## -description

The **FwpmEngineSetOption0** function changes the filter engine settings.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param option [in]

The option to be set.

### -param newValue [in]

The new option value. The data type contained in the *newValue* parameter should be **FWP_UINT32**.

When *option* is **FWPM_ENGINE_COLLECT_NET_EVENTS**, *newValue* should be one of the following.

| Value | Meaning |
| --- | --- |
| 0 | Do not collect network events. |
| 1 | Collect network events. This is the default setting. |

When *option* is **FWPM_ENGINE_NET_EVENT_MATCH_ANY_KEYWORDS**, *newValue* should be either 0 (zero) or a bitwise combination of the following values.

> [!NOTE]
> If *newValue* is 0 the collection of inbound multicast and broadcast events is disabled. This is the default setting.

| Value | Meaning |
| --- | --- |
| **FWPM_NET_EVENT_KEYWORD_INBOUND_MCAST**<br>1 | Collect inbound multicast network events. |
| **FWPM_NET_EVENT_KEYWORD_INBOUND_BCAST**<br>2 | Collect inbound broadcast network events. |

When *option* is **FWPM_ENGINE_PACKET_QUEUING** (available only in Windows 8 and Windows Server 2012), *newValue* should be one of the following.

| Value | Meaning |
| --- | --- |
| **FWPM_ENGINE_OPTION_PACKET_QUEUE_NONE**<br>0 | Do not enable packet queuing. |
| **FWPM_ENGINE_OPTION_PACKET_QUEUE_INBOUND**<br>1 | Enable inbound packet queuing. |
| **FWPM_ENGINE_OPTION_PACKET_QUEUE_OUTBOUND**<br>2 | Enable outbound packet queuing. |

When *option* is **FWPM_ENGINE_MONITOR_IPSEC_CONNECTIONS** (available only in Windows 8 and Windows Server 2012), *newValue* should be the following. (**FwpmEngineSetOption0** may be used to enable connections, but will fail with **FWP_E_STILL_ON ERROR** when attempting to disable it.)

| Value | Meaning |
| --- | --- |
| 1 | The IPsec Connection Monitoring feature will be enabled. New IPsec connection events will be logged as well as notifications sent. |

When *option* is **FWPM_ENGINE_TXN_WATCHDOG_TIMEOUT_IN_MSEC** (available only in Windows 8 and Windows Server 2012), *newValue* should be the time in milliseconds that specifies the maximum duration for a single WFP transaction.  Transactions taking longer than this duration will trigger a watchdog event.

The **FWPM_ENGINE_NAME_CACHE**  option is reserved for internal use.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | Success |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

This function cannot be called from within a transaction, it fails with FWP_E_TXN_IN_PROGRESS. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

This function cannot be called from within a dynamic session, it fails  with **FWP_E_DYNAMIC_SESSION_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about sessions.

The caller needs [FWPM_ACTRL_WRITE](/windows/desktop/FWP/access-right-identifiers) access to the filter engine. See [Access Control](/windows/desktop/FWP/access-control) for more information.

The default settings for network event collection are as follows:

- Outbound, all (unicast, multicast, and broadcast) events are collected.
- Inbound, only unicast events are collected.

Network event collection settings persist across reboots.

To collect inbound broadcast and/or multicast network events,

1. Call **FwpmEngineSetOption0** with *option* set to `FWPM_ENGINE_COLLECT_NET_EVENTS` and *newValue* set to 1.
1. Call **FwpmEngineSetOption0** with option set to `FWPM_ENGINE_NET_EVENT_MATCH_ANY_KEYWORDS` and *newValue* parameter set to `FWPM_NET_EVENT_KEYWORD_INBOUND_MCAST` and/or `FWPM_NET_EVENT_KEYWORD_INBOUND_BCAST`.

To stop collecting inbound broadcast and/or multicast network events,

- Call **FwpmEngineSetOption0** with option set to `FWPM_ENGINE_NET_EVENT_MATCH_ANY_KEYWORDS` and *newValue* parameter set to 0 (zero).

Disabling and re-enabling of network event collection (FWPM_ENGINE_COLLECT_NET_EVENTS) does not reset the collection of inbound broadcast and multicast events.

**FwpmEngineSetOption0** is a specific implementation of **FwpmEngineSetOption**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineGetOption0](nf-fwpmk-fwpmenginegetoption0.md)**
- **[FWPM_ENGINE_OPTION](/windows/desktop/api/fwpmtypes/ne-fwpmtypes-fwpm_engine_option)**
- **[FWP_VALUE0](/windows/desktop/api/fwptypes/ns-fwptypes-fwp_value0)**
- [FWPM_ACTRL_WRITE](/windows/desktop/FWP/access-right-identifiers)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
