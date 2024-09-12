---
UID: NF:fwpmk.FwpmBfeStateSubscribeChanges0
title: FwpmBfeStateSubscribeChanges0 function (fwpmk.h)
description: The FwpmBfeStateSubscribeChanges0 function registers a callback function that is called whenever there is a change to the state of the filter engine.Note  FwpmBfeStateSubscribeChanges0 is a specific version of FwpmBfeStateSubscribeChanges.
old-location: netvista\fwpmbfestatesubscribechanges0.htm
tech.root: netvista
ms.date: 06/21/2024
keywords: ["FwpmBfeStateSubscribeChanges0 function"]
ms.keywords: FwpmBfeStateSubscribeChanges0, FwpmBfeStateSubscribeChanges0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmBfeStateSubscribeChanges0, netvista.fwpmbfestatesubscribechanges0, wfp_ref_2_funct_2_fwpm_79b78030-bb8c-462d-98fc-6f3818dead3d.xml
req.header: fwpmk.h
req.include-header: Fwpmk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpmBfeStateSubscribeChanges0
 - fwpmk/FwpmBfeStateSubscribeChanges0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpmBfeStateSubscribeChanges0
---

# FwpmBfeStateSubscribeChanges0 function

## -description

The **FwpmBfeStateSubscribeChanges0** function registers a callback function that is called whenever there is a change to the state of the filter engine.

> [!WARNING]
> Do not call [FwpmBfeStateUnsubscribeChanges0](nf-fwpmk-fwpmbfestateunsubscribechanges0.md) from the callback function that you passed in the *callback* parameter. Doing so can cause a deadlock.

## -parameters

### -param deviceObject [in, out]

A pointer to a device object that was previously created by the callout driver. For more information about how a callout driver creates a device object, see [Creating a Device Object](/windows-hardware/drivers/kernel/creating-a-device-object).

### -param callback [in]

A pointer to a callout driver-provided service state change callback function. The filter engine calls this function whenever there is a change in the state of the filter engine.

A service-state-change callback function is declared as follows.

```cpp
VOID NTAPI
callback(
    IN OUT void  *context,
    IN FWPM_SERVICE_STATE  newState
    );
```

#### Context

The pointer that was passed in the *Context* parameter when the callout driver called the **FwpmBfeStateSubscribeChanges0** function.

#### newState

The new state of the filter engine. This parameter contains one of the following values:

##### FWPM_SERVICE_STOPPED

The filter engine is not running.

##### FWPM_SERVICE_START_PENDING

The filter engine is starting.

##### FWPM_SERVICE_STOP_PENDING

The filter engine is stopping.

##### FWPM_SERVICE_RUNNING

The filter engine is running.

### -param context [in, optional]

A pointer to a callout driver-provided context that is passed to the callback function specified in the *Callback* parameter.

### -param changeHandle [out]

A pointer to a variable that receives a handle that is associated with the registration of the callback function. A callout driver passes this handle to the [FwpmBfeStateUnsubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestateunsubscribechanges0) function to deregister the callback function.

## -returns

The **FwpmBfeStateSubscribeChanges0** function returns one of the following NTSTATUS codes:

| Return code | Description |
| --- | --- |
| **STATUS_SUCCESS** | The callback function was successfully registered. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

A callout driver calls the **FwpmBfeStateSubscribeChanges0** function to register a callback function that is called whenever there is a change to the state of the filter engine.

For example, a callout driver cannot open a session to the filter engine by calling the [FwpmEngineOpen0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0) function unless the filter engine is currently running. A callout driver can use the **FWPM_SERVICE_RUNNING** notification to open a session to the filter engine so that it can make calls to the other [Windows Filtering Platform management functions](/windows/win32/fwp/fwp-mgmt-functions). Similarly, a callout driver can use the **FWPM_SERVICE_STOP_PENDING** notification to perform any cleanup before the filter engine is stopped.

A callout driver must call **FwpmBfeStateSubscribeChanges0** before calling the [FwpmBfeStateGet0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestateget0) function to retrieve the current state of the filter engine. After the call to **FwpmBfeStateSubscribeChanges0** returns, the callout driver can call **FwpmBfeStateGet0** at any time.

A callout driver must deregister the callback function by calling the [FwpmBfeStateUnsubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestateunsubscribechanges0) function before the callout driver can be unloaded.

**FwpmBfeStateSubscribeChanges0** is a specific version of **FwpmBfeStateSubscribeChanges**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- [FwpmBfeStateGet0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestateget0)
- [FwpmBfeStateUnsubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestateunsubscribechanges0)
- [FwpmEngineOpen0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0)
