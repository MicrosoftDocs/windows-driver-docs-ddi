---
UID: NF:fwpsk.FwpsCalloutRegister3
tech.root: netvista
title: FwpsCalloutRegister3
ms.date: 06/28/2024
targetos: Windows
description: The FwpsCalloutRegister3 function registers the function pointers for a version 3 of the FWPS_CALLOUT3 structure.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fwpsk.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: Fwpkclnt.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Available starting with Windows 8.
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
 - fwpsk.h
api_name:
 - FwpsCalloutRegister3
f1_keywords:
 - FwpsCalloutRegister3
 - fwpsk/FwpsCalloutRegister3
dev_langs:
 - c++
helpviewer_keywords:
 - FwpsCalloutRegister3
---

## -description

The **FwpsCalloutRegister3** function registers the function pointers for a version 3 of the **[FWPS_CALLOUT3](ns-fwpsk-fwps_callout3.md)** structure.

## -parameters

### -param deviceObject [in, out]

A pointer to a device object that was previously created by the callout driver. For more information about how a callout driver creates a device object, see [Creating a Device Object](/windows-hardware/drivers/kernel/creating-a-device-object).

### -param callout [in]

A pointer to a constant **[FWPS_CALLOUT3](ns-fwpsk-fwps_callout3.md)** structure that contains the data that is required to register the callout with the filter engine.

### -param calloutId [out, optional]

A pointer to a UINT32-typed variable that receives a run-time identifier that identifies the callout in the filter engine. The callout driver passes this identifier to the **[FwpsCalloutUnregisterById0](nf-fwpsk-fwpscalloutunregisterbyid0.md)** function when unregistering the callout from the filter engine. If a callout driver is filtering a data flow, it also passes this identifier to the **[FwpsFlowAssociateContext0](nf-fwpsk-fwpsflowassociatecontext0.md)** and **[FwpsFlowRemoveContext0](nf-fwpsk-fwpsflowremovecontext0.md)** functions. If a callout driver injects data into data streams, it also passes this identifier to the **[FwpsStreamInjectAsync0](nf-fwpsk-fwpsstreaminjectasync0.md)** function. The filter engine also passes this identifier to the callout driver's **[FwpsCalloutFlowDeleteNotifyFn0](nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md)** callout function. This parameter is optional and can be **NULL**.

## -returns

The **FwpsCalloutRegister3** function returns one of the following **NTSTATUS** codes.

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The callout was successfully registered with the filter engine. |
| **STATUS_FWP_ALREADY_EXISTS** | The callout could not be registered with the filter engine. A callout is already registered in the filter engine with an identifier identical to the GUID specified in the **calloutKey** member of the **[FWPS_CALLOUT3](ns-fwpsk-fwps_callout3.md)** structure pointed to by the *callout* parameter. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

The callout driver must call **[FwpsCalloutUnregisterById0](nf-fwpsk-fwpscalloutunregisterbyid0.md)** before unloading.

A callout driver calls the **FwpsCalloutRegister3** function to register a callout with the filter engine. A callout driver can register a callout with the filter engine at any time, even if the filter engine is not currently running.

A callout and filters that specify the callout for the filter's action can be added to the filter engine before a callout driver registers the callout with the filter engine. In this situation, filters with an action type of **FWP_ACTION_CALLOUT_TERMINATING** or **FWP_ACTION_CALLOUT_UNKNOWN** are treated as **FWP_ACTION_BLOCK**, and filters with an action type of **FWP_ACTION_CALLOUT_INSPECTION** are ignored until the callout is registered with the filter engine.

A callout driver unregisters a callout from the filter engine by calling either the **[FwpsCalloutUnregisterById0](nf-fwpsk-fwpscalloutunregisterbyid0.md)** function or the **[FwpsCalloutUnregisterByKey0](nf-fwpsk-fwpscalloutunregisterbykey0.md)** function. A callout driver cannot be unloaded until all of the callouts that were previously registered with the filter engine have been successfully unregistered.

This function is essentially identical to the previous version, **[FwpsCalloutRegister2](nf-fwpsk-fwpscalloutregister2.md)**. The only difference is the updated **[FWPS_CALLOUT3](ns-fwpsk-fwps_callout3.md)** structure pointed to by the callout parameter.

## -see-also

- [Creating a Device Object](/windows-hardware/drivers/kernel/creating-a-device-object)
- **[FwpsCalloutUnregisterById0](nf-fwpsk-fwpscalloutunregisterbyid0.md)**
- **[FwpsFlowAssociateContext0](nf-fwpsk-fwpsflowassociatecontext0.md)**
- **[FwpsFlowRemoveContext0](nf-fwpsk-fwpsflowremovecontext0.md)**
- **[FwpsStreamInjectAsync0](nf-fwpsk-fwpsstreaminjectasync0.md)**
- **[FwpsCalloutFlowDeleteNotifyFn0](nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md)**
- **[FWPS_CALLOUT3](ns-fwpsk-fwps_callout3.md)**
- **[FwpsCalloutUnregisterById0](nf-fwpsk-fwpscalloutunregisterbyid0.md)**
- **[FwpsCalloutUnregisterByKey0](nf-fwpsk-fwpscalloutunregisterbykey0.md)**
- **[FwpsCalloutRegister2](nf-fwpsk-fwpscalloutregister2.md)**
