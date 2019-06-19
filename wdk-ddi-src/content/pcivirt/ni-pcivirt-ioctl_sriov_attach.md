---
UID: NI:pcivirt.IOCTL_SRIOV_ATTACH
title: IOCTL_SRIOV_ATTACH (pcivirt.h)
description: The request indicates that the virtualization stack wants to register for Plug and Play events received by the SR-IOV device.
old-location: pci\ioctl-sriov-attach.htm
tech.root: PCI
ms.assetid: c1129d60-eeb0-4c90-b181-365f3379d89e
ms.date: 02/24/2018
ms.keywords: IOCTL_SRIOV_ATTACH, IOCTL_SRIOV_ATTACH control code [Buses], PCI.ioctl-sriov-attach, pcivirt/IOCTL_SRIOV_ATTACH
ms.topic: ioctl
req.header: pcivirt.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Pcivirt.h
api_name:
- IOCTL_SRIOV_ATTACH
product:
- Windows
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# IOCTL_SRIOV_ATTACH IOCTL


##  Major Code:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


The  request indicates that the virtualization stack wants to register for Plug and Play events received by the SR-IOV device.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.


## -remarks



This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

This request is unsafe if the PF device is currently stopped or stopping for resource re-balance. A device is
considered to be stopped after it received  <a href="https://msdn.microsoft.com/library/windows/hardware/ff551725">IRP_MN_QUERY_STOP_DEVICE</a> and restarted when it receives  <a href="https://msdn.microsoft.com/library/windows/hardware/ff550826">IRP_MN_CANCEL_STOP_DEVICE</a> or when  <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>
is completed by the lower devices in the stack. In this case, the driver must delay the completion of this request until the device is restarted.

It is not necessary to keep  this IRP pending because the request always a sent as
        a synchronous kernel-mode IRP causing the caller to block the thread in any case.


Upon the completion of this request, the VSP can subsequently  send
<a href="https://msdn.microsoft.com/3f2d67e0-abab-40a1-b4a9-cb65e81884e9">IOCTL_SRIOV_NOTIFICATION</a> and <a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a> requests.

To unregister for Plug and Play events, the VSP sends the <a href="https://msdn.microsoft.com/8ede4a48-317b-46be-834a-a67b638b28c0">IOCTL_SRIOV_DETACH</a> request.

These events (defined in <a href="https://msdn.microsoft.com/e2b40a9d-57e6-49b1-839a-d34acb108807">SRIOV_PF_EVENT</a>) cause the completion of  <a href="https://msdn.microsoft.com/3f2d67e0-abab-40a1-b4a9-cb65e81884e9">IOCTL_SRIOV_NOTIFICATION</a> and a wait for  <a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a>:


<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551725">IRP_MN_QUERY_STOP_DEVICE</a> generates  <b>SriovEventPfQueryStopDevice</b>.</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> generates  <b>SriovEventPfRestart</b><i> if and only if</i> the device was stopped for rebalancing (see above).
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550826">IRP_MN_CANCEL_STOP_DEVICE</a> generates  <b>SriovEventPfRestart</b><i> if and only if</i> the device was stopped for rebalancing.</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551705">IRP_MN_QUERY_REMOVE_DEVICE</a> generates  <b>SriovEventPfQueryRemoveDevice</b>.</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a> generates <b>SriovEventPfSurpriseRemoveDevice</b>.
</li>
</ul>
In this example handling of the IOCTL_SRIOV_ATTACH request, the PF driver maintains PnP states in its device context. The deviceContext->PnpRebalancing is set to TRUE, when the driver receives IRP_MN_QUERY_STOP_DEVICE and set to FALSE when it receives IRP_MN_START_DEVICE.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>    case IOCTL_SRIOV_ATTACH:
        TraceEvents(TRACE_LEVEL_VERBOSE, DBG_IOCTL, "IOCTL_SRIOV_ATTACH:\n");

        WdfWaitLockAcquire(fdoContext->PnpStateLock, NULL);

        //
        // Block until it is safe for the VSP to attach.  Don't
        // bother with pending this IRP since this is always a sent as
        // a synchronous kernel-mode IRP and the caller would block
        // the thread anyway.  May need to repeat the wait since since
        // waiting for the safe-to-attach event must not be done while
        // holding the state lock.
        //
        while (fdoContext->PnpSafeToAttach == FALSE)
        {
            WdfWaitLockRelease(fdoContext->PnpStateLock);

            KeWaitForSingleObject(&fdoContext->PnpSafeEvent,
                                  Executive,
                                  KernelMode,
                                  FALSE,
                                  NULL);

            WdfWaitLockAcquire(fdoContext->PnpStateLock, NULL);
        }

        //
        // Allow only a single attach at any time.
        //
        if (fdoContext->PnpVspAttached == FALSE)
        {
            fdoContext->PnpVspAttached = TRUE;
            status = STATUS_SUCCESS;
        }
        else
        {
            status = STATUS_SHARING_VIOLATION;
        }
        WdfWaitLockRelease(fdoContext->PnpStateLock);

        break;
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/8ede4a48-317b-46be-834a-a67b638b28c0">IOCTL_SRIOV_DETACH</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



 

 


