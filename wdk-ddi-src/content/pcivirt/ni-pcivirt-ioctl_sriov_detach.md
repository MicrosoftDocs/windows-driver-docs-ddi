---
UID: NI:pcivirt.IOCTL_SRIOV_DETACH
title: IOCTL_SRIOV_DETACH
author: windows-driver-content
description: The request indicates that the virtualization stack wants to unregister for Plug and Play events (previously registered through the IOCTL_SRIOV_ATTACH request).
old-location: pci\ioctl-sriov-detach.htm
tech.root: PCI
ms.assetid: 8ede4a48-317b-46be-834a-a67b638b28c0
ms.date: 02/24/2018
ms.keywords: IOCTL_SRIOV_DETACH, IOCTL_SRIOV_DETACH control code [Buses], PCI.ioctl-sriov-detach, pcivirt/IOCTL_SRIOV_DETACH
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Pcivirt.h
api_name:
-	IOCTL_SRIOV_DETACH
product:
- Windows
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# IOCTL_SRIOV_DETACH IOCTL


##  Major Code:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


The  request indicates that the virtualization stack wants to unregister for Plug and Play events (previously registered through the <a href="https://msdn.microsoft.com/c1129d60-eeb0-4c90-b181-365f3379d89e">IOCTL_SRIOV_ATTACH</a> request).


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.


## -remarks



This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

From here on, the PF should not expect to receive  <a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a> and <a href="https://msdn.microsoft.com/3f2d67e0-abab-40a1-b4a9-cb65e81884e9">IOCTL_SRIOV_NOTIFICATION</a> requests.


The driver that must stop waiting for <a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a>.
If the driver is currently waiting it should stop waiting and continue
 processing Plug and Play IRPs.

In this example handling of the IOCTL_SRIOV_DETACH request, the PF driver maintains PnP states in its device context. The deviceContext-&gt;PnpRebalancing is set to TRUE, when the driver receives <a href="https://msdn.microsoft.com/library/windows/hardware/ff551725">IRP_MN_QUERY_STOP_DEVICE</a> and set to FALSE when it receives IRP_MN_START_DEVICE.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>    case IOCTL_SRIOV_DETACH:

        WdfWaitLockAcquire(deviceContext-&gt;PnpStateLock, NULL);

        deviceContext-&gt;PnpVspAttached = FALSE;

        if (deviceContext-&gt;PnpRebalancing != FALSE)
        {
            //
            // Any new client (VSP state machine) will not know about
            // the current rebalance is it should block attach until
            // rebalance is over.
            //

    								deviceContext&gt;PnpSafeToAttach = FALSE;
    								KeClearEvent(&amp;deviceContext&gt;PnpSafeEvent);

        }

        //
        // Unblock the PnP thread if it waiting for an IO control from the
        // client as the client just detached.
        //
        deviceContext-&gt;PnpEventStatus = STATUS_SUCCESS;
        KeSetEvent(&amp;deviceContext-&gt;PnpUnblockEvent, IO_NO_INCREMENT, FALSE);

        WdfWaitLockRelease(deviceContext-&gt;PnpStateLock);

        status = STATUS_SUCCESS;
        break;


</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/c1129d60-eeb0-4c90-b181-365f3379d89e">IOCTL_SRIOV_ATTACH</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



 

 


