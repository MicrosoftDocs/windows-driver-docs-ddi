---
UID: NF:wdm.IoWMIRegistrationControl
title: IoWMIRegistrationControl function
author: windows-driver-content
description: The IoWMIRegistrationControl routine registers or unregisters the caller as a WMI data provider for a specified device object.
old-location: kernel\iowmiregistrationcontrol.htm
old-project: kernel
ms.assetid: fe135118-1992-43c7-8492-81f9febd79b9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, I, IoWMIRegistrationControl, IoWMIRegistrationControl routine [Kernel-Mode Driver Architecture], M, R, W, a, e, g, i, k104_69efd10b-fb1a-4d66-939d-6ade4185605d.xml, kernel.iowmiregistrationcontrol, l, n, o, r, s, t, wdm/IoWMIRegistrationControl"
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
req.ddi-compliance: IrqlIoPassive5, LowerDriverReturn, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoWMIRegistrationControl
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoWMIRegistrationControl function


## -description


The <b>IoWMIRegistrationControl</b> routine registers or unregisters the caller as a WMI data provider for a specified device object.


## -syntax


````
NTSTATUS IoWMIRegistrationControl(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ ULONG          Action
);
````


## -parameters




### -param DeviceObject [in]

A pointer to a device object. This object is a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> system structure.


### -param Action [in]

The action that WMI should take. The requested action is indicated by one of the following values.

<table>
<tr>
<th>Action value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WMIREG_ACTION_REGISTER

</td>
<td>
Specifies that WMI should register the caller as a WMI provider for <i>DeviceObject</i>. This will result in WMI sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a> request to the driver.

</td>
</tr>
<tr>
<td>
WMIREG_ACTION_DEREGISTER

</td>
<td>
Specifies that WMI should remove the caller from its list of WMI providers for <i>DeviceObject</i>.

</td>
</tr>
<tr>
<td>
WMIREG_ACTION_REREGISTER

</td>
<td>
Specifies that WMI should unregister the driver and then register (reregister) the driver. Reregistering the driver results in WMI sending an <b>IRP_MN_REGINFO</b> or <b>IRP_MN_REGINFO_EX</b> request to the driver.

</td>
</tr>
<tr>
<td>
WMIREG_ACTION_UPDATE_GUIDS

</td>
<td>
Specifies that WMI should re-query the driver for a new list of GUID identifiers that it provides data for. This will result in WMI sending an <b>IRP_MN_REGINFO</b> or <b>IRP_MN_REGINFO_EX</b> request to the driver.

</td>
</tr>
</table>
 


## -returns



<b>IoWMIRegistrationControl</b> returns a status code from the following list:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that WMI completed the action requested without error.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the action, specified in <i>Action</i>, was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
Indicates that the request failed for the reason specified by the NTSTATUS value. See Ntstatus.h for detailed information for the actual status return code.

</td>
</tr>
</table>
 




## -remarks



After a driver calls <b>IoWMIRegistrationControl</b>, WMI sends the driver an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a> request so the driver can provide information to WMI. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560870">Registering as a WMI Data Provider</a>.

If the caller specifies WMIREG_ACTION_DEREGISTER for <i>Action</i>, <b>IoWMIRegistrationControl</b> causes the calling thread to block until all <b>IRP_MJ_SYSTEM_CONTROL</b> requests that were previously sent to the specified device object have completed. In such a case, if a driver calls <b>IoWMIRegistrationControl</b> within a dispatch routine for an <b>IRP_MJ_SYSTEM_CONTROL</b> request, the calling thread will deadlock.

If a device is removed suddenly (for example, in a surprise removal), causing the PnP manager to send an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a> IRP, the driver must call <b>IoWMIRegistrationControl</b> and specify WMIREG_ACTION_DEREGISTER in <i>Action</i> in the call. Note that if the driver calls <b>IoWMIRegistrationControl</b> with <i>Action</i> set to WMIREG_ACTION_DEREGISTER in response to an <b>IRP_MN_SURPRISE_REMOVAL</b> IRP, the driver must not make the same call to <b>IoWMIRegistrationControl</b> in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> IRP.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIRegistrationControl routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

