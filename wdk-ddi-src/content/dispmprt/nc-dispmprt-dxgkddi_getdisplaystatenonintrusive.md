---
UID: NC:dispmprt.DXGKDDI_GETDISPLAYSTATENONINTRUSIVE
title: DXGKDDI_GETDISPLAYSTATENONINTRUSIVE
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The operating system calls a display miniport driver's DxgkDdiGetDisplayStateNonIntrusive routine to nonintrusively collect display state information from the driver.
tech.root: display
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_GETDISPLAYSTATENONINTRUSIVE
f1_keywords:
 - dispmprt/DXGKDDI_GETDISPLAYSTATENONINTRUSIVE
dev_langs:
 - c++
---

# DXGKDDI_GETDISPLAYSTATENONINTRUSIVE callback function

## -description

The operating system calls a display miniport driver's **DxgkDdiGetDisplayStateNonIntrusive** routine to nonintrusively collect display state information from the driver.

## -parameters

### -param Context

[in] Pointer to a private context returned by [**DxgkDdiQueryInterface**](nc-dispmprt-dxgkddi_query_interface.md).

### -param pArgs

[in/out] Pointer to a [**DXGKARG_GETDISPLAYSTATENONINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystatenonintrusive.md) structure.

## -returns

**DxgkDdiGetDisplayStateNonIntrusive** returns STATUS_SUCCESS if it succeeds. Otherwise it returns an error code such as one of the following.

| Error Code | Meaning |
| ---------- | ------- |
| STATUS_DRIVER_INTERNAL_ERROR  | A generic software error occurred inside the driver. |
| STATUS_ACCESS_DENIED          | The hardware is being currently used by other threads and this DDI can't get access to it. |
| STATUS_DEVICE_HARDWARE_ERROR  | Generic HW error happened. |
| STATUS_DEVICE_POWERED_OFF     | The device is powered off. |

## -remarks

The OS calls **DxgkDdiGetDisplayStateNonIntrusive** to collect display state information from the driver. Unlike [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md), the driver's **DxgkDdiGetDisplayStateNonIntrusive** routine should not perform any operations that cause visible side effects to the user, and the collection process should be relatively fast (ideally within a few milliseconds). This routine's calling frequency will be relatively high. Apart from being called for diagnosing bad user state, the OS might also use this routine for recording historical state information from the driver for debugging purposes.

In rare cases where a platform-specific implementation requires the driver to carry out intrusive operations as part of a call to **DxgkDdiGetDisplayStateNonIntrusive**, the driver should carry out the operations but must set **pArgs->ReturnSubStatus** to DXGK_DIAG_GETDISPLAYSTATE_CAUSED_GLITCH or DXGK_DIAG_GETDISPLAYSTATE_CHANGED_DISPLAY_STATE accordingly. Based on the **ReturnSubStatus** value, the operating system (OS) might only call this routine for error scenarios on a given system.

The OS will call **DxgkDdiGetDisplayStateNonIntrusive** frequently (either periodically or on other commonly occurring events) to gather driver state data for debugging purposes and to look at the historical timeline. The OS will also call this routine in particular error scenarios (such as black screens) before gathering more detailed information by calling [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md). Given the possible frequency of this call, drivers should complete it as quickly as possible. The OS will call this DDI with **NumOfTargets** set to the maximum number of targets supported by the given graphics adapter and **VidPnTargetId** filled in. The miniport driver should only fill the display state information for targets on which there is actually a monitor connected. For a vidpntarget on which there is no monitor connected, the miniport should just fill in DXGK_DIAG_DISPLAY_CONNECTIVITY and the OS will ignore all other fields for that target.

> [!NOTE]
> Drivers should only use **ReturnSubStatus** to report error conditions and not use DXGK_DIAG_GETDISPLAYSTATE_MONITOR_NOT_CONNECTED for reporting monitor connectivity state. The main purpose of DXGK_DIAG_GETDISPLAYSTATE_MONITOR_NOT_CONNECTED is for intrusive calls where the OS doesn't ask about monitor connectivity.
>
> If driver hits a failure on a given vidpntarget while collecting information, it should use **ReturnSubStatus** to set the error state and proceed to the next vidpntarget and not fail the overall call unless all the paths hit failures. Drivers should ideally record errors hit during this call in some internal error log so that when the OS calls [**DxgkDdiCollectDiagnosticInfo**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_collectdiagnosticinfo) for collecting black box information, these errors are captured as part of an internal log collection to help IHVs during debug.

Synchronization level for this DDI is [zero level synchronization](https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-zero-level).

## -see-also

[**DXGKARG_GETDISPLAYSTATENONINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystatenonintrusive.md)

[**DxgkDdiCollectDiagnosticInfo**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_collectdiagnosticinfo)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)

[**DxgkDdiQueryInterface**](nc-dispmprt-dxgkddi_query_interface.md)
