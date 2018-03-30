---
UID: NF:wdm.IoSetDeviceInterfaceState
title: IoSetDeviceInterfaceState function
author: windows-driver-content
description: The IoSetDeviceInterfaceState routine enables or disables an instance of a previously registered device interface class.
old-location: kernel\iosetdeviceinterfacestate.htm
old-project: kernel
ms.assetid: 071b5f2a-7129-4de5-9577-f2aa22f23765
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoSetDeviceInterfaceState, IoSetDeviceInterfaceState routine [Kernel-Mode Driver Architecture], k104_da5493d0-6dd5-4404-a647-6c23825df29c.xml, kernel.iosetdeviceinterfacestate, wdm/IoSetDeviceInterfaceState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive1, LowerDriverReturn, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoSetDeviceInterfaceState
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoSetDeviceInterfaceState function


## -description


The <b>IoSetDeviceInterfaceState</b> routine enables or disables an instance of a previously registered device interface class. 


## -parameters




### -param SymbolicLinkName [in]

Pointer to a string that identifies the device interface instance that is being enabled or disabled. This string was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549506">IoRegisterDeviceInterface</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549186">IoGetDeviceInterfaces</a>. 


### -param Enable [in]

<b>TRUE</b> indicates that the device interface is being enabled. <b>FALSE</b> indicates that the device interface is being disabled. 


## -returns



<b>IoSetDeviceInterfaceState</b> returns STATUS_SUCCESS if the call was successful. This routine returns an informational status of STATUS_OBJECT_NAME_EXISTS if the caller requested to enable a device interface that was already enabled. Possible error return values are described following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The caller tried to disable a device interface that was not enabled.

</td>
</tr>
</table>
 




## -remarks



<b>IoSetDeviceInterfaceState</b> enables an instance of a registered device interface for use by applications and other system components. The interface class must have been previously registered with <a href="https://msdn.microsoft.com/library/windows/hardware/ff549506">IoRegisterDeviceInterface</a> or from user mode. 

Applications and other system components can open only interfaces that are enabled.

A function or a filter driver typically calls this routine with <i>Enable</i> set to <b>TRUE</b> after it successfully starts a device in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> IRP. Such a driver should disable the device interface instance (that is, call <b>IoSetDeviceInterfaceState</b> and set <i>Enable</i> to <b>FALSE</b>) when it removes the device in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> IRP or an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a> IRP. If a driver does not disable a device interface when it processes these removal IRPs, the driver should not subsequently attempt to do so because the PnP manager will disable the interface when the PnP manager removes the device. 

If a device is removed suddenly (for example, by a surprise removal) but still has a valid device interface instance, a problem will occur if the device is reattached. This problem occurs when the PnP manager enumerates the newly attached device and enables a device interface instance, which will exist at the same registry path as the existing device interface instance.

Note that if the driver calls <b>IoSetDeviceInterfaceState</b> to disable a device interface instance in response to an <b>IRP_MN_SURPRISE_REMOVAL</b> IRP, the driver must not attempt to disable the same device interface instance in response to an <b>IRP_MN_REMOVE_DEVICE</b> IRP.

If a call to <b>IoSetDeviceInterfaceState</b> successfully exposes a device interface instance, the system notifies any components that registered for PnP notification of a device class change. Similarly, if a call to this routine disables an existing device interface instance, the system sends appropriate notifications.

The PnP manager does not send notification of interface instance arrivals until the <b>IRP_MN_START_DEVICE</b> IRP completes, indicating that all the drivers for the device have completed their start operations. In addition, the PnP manager fails create requests for the device until the <b>IRP_MN_START_DEVICE</b> IRP completes.

Callers of <b>IoSetDeviceInterfaceState</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549186">IoGetDeviceInterfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549506">IoRegisterDeviceInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549526">IoRegisterPlugPlayNotification</a>
 

 

