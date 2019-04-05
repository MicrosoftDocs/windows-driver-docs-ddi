---
UID: NF:wdm.PoFxIssueComponentPerfStateChange
title: PoFxIssueComponentPerfStateChange function (wdm.h)
description: The PoFxIssueComponentPerfStateChange routine submits a request to place a device component in a particular performance state.
old-location: kernel\pofxissuecomponentperfstatechange.htm
tech.root: kernel
ms.assetid: DBB4747B-F6CF-4842-988C-6FAA9C552EA9
ms.date: 04/30/2018
ms.keywords: PO_FX_FLAG_ASYNC_ONLY, PO_FX_FLAG_BLOCKING, PoFxIssueComponentPerfStateChange, PoFxIssueComponentPerfStateChange routine [Kernel-Mode Driver Architecture], kernel.pofxissuecomponentperfstatechange, wdm/PoFxIssueComponentPerfStateChange
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: "<= APC_LEVEL or <= DISPATCH_LEVEL (See Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Ntoskrnl.exe
api_name:
- PoFxIssueComponentPerfStateChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxIssueComponentPerfStateChange function


## -description


The <b>PoFxIssueComponentPerfStateChange</b> routine submits a request to place a device component in a 
    particular performance state. 


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a> routine.


### -param Flags [in]

The flags that modify the behavior of the performance state change operation. Set this member to zero or to one of the following flag <b>PO_FX_FLAG_<i>XXX</i></b> bits:

These two flag bits are mutually exclusive. For more information, see Remarks.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PO_FX_FLAG_BLOCKING"></a><a id="po_fx_flag_blocking"></a><dl>
<dt><b>PO_FX_FLAG_BLOCKING</b></dt>
<dt>0x1</dt>
</dl>
</td>
<td width="60%">
Make the condition change synchronous. If this flag is set, the routine that requests the condition change does not return control to the calling driver until the component hardware completes the transition to the new condition. This flag can be used only if the caller is running at IRQL &lt; DISPATCH_LEVEL.

</td>
</tr>
<tr>
<td width="40%"><a id="PO_FX_FLAG_ASYNC_ONLY"></a><a id="po_fx_flag_async_only"></a><dl>
<dt><b>PO_FX_FLAG_ASYNC_ONLY</b></dt>
<dt>0x2</dt>
</dl>
</td>
<td width="60%">
Make the condition change fully asynchronous. If this flag is set, the calling driver's callback routine is called from a thread other than the thread in which the routine that requests the condition change is called. Thus, the routine that requests the condition change always returns asynchronously without waiting for the callback to complete.

</td>
</tr>
</table>
 


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439585">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param PerfChange [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn939836">PO_FX_PERF_STATE_CHANGE</a> structure that represents the new performance state of the component.


### -param Context [in]

A pointer to the context for the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> callback routine. This parameter is optional. It is provided so that a driver or device context can be passed to the callback routine. If this parameter is not used, it must be set to NULL.


## -returns



None




## -remarks



When a driver calls <b>PoFxIssueComponentPerfStateChange</b>, the power management framework (PoFx) requests the platform extension plug-in (PEP) to place 
    the component's performance state set in the specified performance state. This routine may be used with both discrete and range-based types of performance state sets. For more information about discrete and range-based performance state sets, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn939837">PO_FX_PERF_STATE_TYPE</a>.

If <i>Flags</i> = <b>PO_FX_FLAG_BLOCKING</b>, the <b>PoFxIssueComponentPerfStateChange</b> call is synchronous. In this case, <b>PoFxIssueComponentPerfStateChange</b> waits to return until the component completes the performance state transition. The driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> routine is called to inform the driver that the component's performance state change is complete. This callback occurs in the same thread as the call to <b>PoFxIssueComponentPerfStateChange</b>, and <b>PoFxIssueComponentPerfStateChange</b> returns only after the <i>ComponentPerfStateCallback</i> callback returns. 

If <i>Flags</i> = <b>PO_FX_FLAG_ASYNC_ONLY</b>, the <b>PoFxIssueComponentPerfStateChange</b> call is asynchronous. In this case, <b>PoFxIssueComponentPerfStateChange</b> schedules the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> routine to occur in another thread, and then returns without waiting for the callback to occur. The callback can occur before or after <b>PoFxIssueComponentPerfStateChange</b> returns. The driver should rely on the <i>ComponentPerfStateCallback</i> routine to determine when the component completes the transition to the new performance state. 

The driver can set <i>Flags</i> = 0 to indicate that it does not care whether the <b>PoFxIssueComponentPerfStateChange</b> call is synchronous or asynchronous. In this case, PoFx decides the synchronicity of the call  based on whether the PEP uses a synchronous or asynchronous request to issue the performance state change to the component.

If <i>Flags</i> = <b>PO_FX_FLAG_ASYNC_ONLY</b> or no flags are passed, this routine requires an IRQL of &lt;= DISPATCH_LEVEL. If <i>Flags</i> = <b>PO_FX_FLAG_BLOCKING</b>, this routine requires an IRQL of &lt;= APC_LEVEL.

This function will always result in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> routine regardless of the synchronicity of the call. Because the PEP may choose to deny the request to change the performance state, the driver must wait until receiving the callback before committing the performance state to hardware.

Only a single call of the <b>PoFxIssueComponentPerfStateChange</b> routine  is allowed at a time per component, regardless of whether the call is synchronous or asynchronous. After issuing a performance state change request, the driver must wait until the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> is received before calling this routine again, even if the request involves a different performance state set. If this routine is called again before waiting until the <i>ComponentPerfStateCallback</i> is received, a bugcheck will occur.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a>



<a href="https://msdn.microsoft.com/D5341D6D-7C71-43CB-9C70-7E939B32C33F">Device Performance State Management</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939837">PO_FX_PERF_STATE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939772">PoFxIssueComponentPerfStateChangeMultiple</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939778">PoFxRegisterComponentPerfStates</a>
 

 

