---
UID: NS:fwpsk.FWPS_CALLOUT3_
tech.root: netvista
title: FWPS_CALLOUT3
ms.date: 07/12/2024
targetos: Windows
description: The FWPS_CALLOUT3 structure defines the data that is required for a callout driver to register a callout with the filter engine.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: fwpsk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.target-type: Universal
req.typenames: FWPS_CALLOUT3
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_CALLOUT3_
 - FWPS_CALLOUT3
f1_keywords:
 - FWPS_CALLOUT3_
 - fwpsk/FWPS_CALLOUT3_
 - FWPS_CALLOUT3
 - fwpsk/FWPS_CALLOUT3
dev_langs:
 - c++
helpviewer_keywords:
 - FWPS_CALLOUT3_
---

## -description

The **FWPS_CALLOUT3** structure defines the data that is required for a callout driver to register a callout with the filter engine.

## -struct-fields

### -field calloutKey

A callout driver-defined **GUID** that uniquely identifies the callout.

### -field flags

Flags that specify callout-specific parameters. Possible flags are:

| Value | Meaning |
|-------|---------|
| **FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW**<br>0x00000001 | A callout driver can specify this flag when registering a callout that will be added at a layer that supports data flows. If this flag is specified, the filter engine calls the callout driver's [classifyFn3](nc-fwpsk-fwps_callout_classify_fn3.md) callout function only if there is a context associated with the data flow. A callout driver associates a context with a data flow by calling the [FwpsFlowAssociateContext0](nf-fwpsk-fwpsflowassociatecontext0.md) function. |
| **FWP_CALLOUT_FLAG_ALLOW_OFFLOAD**<br>0x00000002 | A callout driver specifies this flag to indicate that the callout driver's [classifyFn3](nc-fwpsk-fwps_callout_classify_fn3.md) callout function is unaffected by offloading network data processing to offload-capable network interface cards (NICs). If this flag is not specified, then offloading of network data processing is disabled for all traffic that is processed by any filters that specify the callout for the filter's action. |
| **FWP_CALLOUT_FLAG_ENABLE_COMMIT_ADD_NOTIFY**<br>0x00000004 | A callout driver specifies this flag to indicate that it can receive notifications about objects and filters that are added inside a transaction. The filter engine sends the notification after the transaction is committed. |
| **FWP_CALLOUT_FLAG_ALLOW_MID_STREAM_INSPECTION**<br>0x00000008 | A callout driver specifies this flag to indicate that it can perform dynamic stream inspection of data flows at stream level. See [Stream Inspection](/windows-hardware/drivers/network/stream-inspection). |
| **FWP_CALLOUT_FLAG_ALLOW_RECLASSIFY**<br>0x00000010 | A callout driver specifies this flag to register itself to be called when an existing socket operation is reclassified. |
| **FWP_CALLOUT_FLAG_RESERVED1**<br>0x00000020 | Reserved for system use. Callout drivers should ignore this flag. |
| **FWP_CALLOUT_FLAG_ALLOW_RSC**<br>0x00000040 | A callout driver specifies this flag to indicate that the callout supports TCP receive segment coalescing (RSC) with large packets of up to 64K. If this flag is not specified, and a callout is registered, then RSC is disabled for all traffic that is processed by any filters that specify the callout for the filter's action. |
| **FWP_CALLOUT_FLAG_ALLOW_L2_BATCH_CLASSIFY**<br>0x00000080 | A callout driver specifies this flag when registering a callout that will be added at layer 2, to indicate that its [classifyFn3](nc-fwpsk-fwps_callout_classify_fn3.md) callout function can classify multiple chained [NET_BUFFER_LIST](/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list) structures. For more info, see [Using Layer 2 Filtering](/windows-hardware/drivers/network/using-layer-2-filtering).<br><br>**Caution:**<br>If a callout driver sets this flag, it cannot use the following functions to modify NET_BUFFER_LISTs.<br><br>&bull; [FwpsReferenceNetBufferList0](nf-fwpsk-fwpsreferencenetbufferlist0.md)<br>&bull; [FwpsDereferenceNetBufferList0](nf-fwpsk-fwpsdereferencenetbufferlist0.md)<br>&bull; [FwpsAllocateCloneNetBufferList0](nf-fwpsk-fwpsallocateclonenetbufferlist0.md)<br>&bull; [FwpsFreeCloneNetBufferList0](nf-fwpsk-fwpsfreeclonenetbufferlist0.md)<br><br>With this flag set, **FwpsAllocateCloneNetBufferList0** will always return an **INVALID_PARAMETER** error. This may unexpectedly cause a 3rd party callout driver to fail to manage the reference count of NET_BUFFER_LISTs, causing send and receive operations to stop. |
| **FWP_CALLOUT_FLAG_ALLOW_USO**<br>0x00000100 | A callout driver specifies this flag to indicate that the callout supports UDP segmentation offload (USO) with packets larger than the MTU of the network medium. If this flag is not specified, and a callout is registered, then USO is disabled for all traffic that is processed by any filters that specify the callout for the filter's action. **Note:** The earliest version in which this flag is supported is Windows Insider Preview, version 10.0.25876. |
| **FWP_CALLOUT_FLAG_ALLOW_URO**<br>0x00000200 | A callout driver specifies this flag to indicate that the callout supports UDP receive offload (URO) with large packets of up to 64K. If this flag is not specified, and a callout is registered, then URO is disabled for all traffic that is processed by any filters that specify the callout for the filter's action. **Note:** If this flag is specified then callouts must not clone and reinject inbound URO packets. |

### -field classifyFn

A pointer to the callout driver's [classifyFn3](nc-fwpsk-fwps_callout_classify_fn3.md) callout function. The filter engine calls this function whenever there is network data to be processed by the callout.

### -field notifyFn

A pointer to the callout driver's [notifyFn3](nc-fwpsk-fwps_callout_notify_fn3.md) function. The filter engine calls this function to notify the callout driver about events that are associated with the callout.

### -field flowDeleteFn

A pointer to the callout driver's [flowDeleteFn](nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md) callout function. The filter engine calls this function whenever a data flow that is being processed by the callout is terminated.

If a callout driver does not associate a context with the data flows that the callout processes, then this member should be set to NULL.

## -remarks

A callout driver passes a pointer to an initialized **FWPS_CALLOUT3** structure to the [FwpsCalloutRegister3](nf-fwpsk-fwpscalloutregister3.md) function when it registers a callout with the filter engine.

A callout can set the **FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW** flag only for connections on which the driver is interested in performing stream inspections. This callout will be ignored on all other connections. Performance will be improved and the driver will not have to maintain unnecessary state data.

**FWPS_CALLOUT3** is the specific version of **FWPS_CALLOUT**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FWPS_CALLOUT0](ns-fwpsk-fwps_callout0_.md)**
- **[FWPS_CALLOUT1](ns-fwpsk-fwps_callout1_.md)**
- **[FWPS_CALLOUT2](ns-fwpsk-fwps_callout2_.md)**
- **[FwpsCalloutRegister3](nf-fwpsk-fwpscalloutregister3.md)**
- **[classifyFn3](nc-fwpsk-fwps_callout_classify_fn3.md)**
- **[flowDeleteFn](nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md)**
- **[notifyFn3](nc-fwpsk-fwps_callout_notify_fn3.md)**
- [Using Layer 2 Filtering](/windows-hardware/drivers/network/using-layer-2-filtering)
