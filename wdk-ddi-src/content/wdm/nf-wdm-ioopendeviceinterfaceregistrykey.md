---
UID: NF:wdm.IoOpenDeviceInterfaceRegistryKey
title: IoOpenDeviceInterfaceRegistryKey function
author: windows-driver-content
description: The IoOpenDeviceInterfaceRegistryKey routine returns a handle to a registry key for storing information about a particular device interface instance.
old-location: kernel\ioopendeviceinterfaceregistrykey.htm
old-project: kernel
ms.assetid: d9ca4b9d-dacc-4164-9198-a71a771b145b
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: IoOpenDeviceInterfaceRegistryKey, IoOpenDeviceInterfaceRegistryKey routine [Kernel-Mode Driver Architecture], k104_39651647-aa61-4670-b09d-7aaabaae4603.xml, kernel.ioopendeviceinterfaceregistrykey, wdm/IoOpenDeviceInterfaceRegistryKey
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
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	IoOpenDeviceInterfaceRegistryKey
product: Windows
targetos: Windows
req.typenames: 
---

# IoOpenDeviceInterfaceRegistryKey function


## -description


The <b>IoOpenDeviceInterfaceRegistryKey</b> routine returns a handle to a registry key for storing information about a particular device interface instance.


## -parameters




### -param SymbolicLinkName [in]

Pointer to a string identifying the device interface instance. This string was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549186">IoGetDeviceInterfaces</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549180">IoGetDeviceInterfaceAlias</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549506">IoRegisterDeviceInterface</a>. 


### -param DesiredAccess [in]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that represents the access the caller requires to the key, such as KEY_READ, KEY_WRITE, or KEY_ALL_ACCESS. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a> for a description of each KEY_<i>XXX</i> access right. 


### -param DeviceInterfaceKey [out]

Pointer to a returned handle to the requested registry key if the call is successful. 


## -returns



<b>IoOpenDeviceInterfaceRegistryKey</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following.

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
The routine was not able to locate a registry key for the device interface instance, probably due to an error in the <i>SymbolicLinkName</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The routine was not able to locate a registry key for the device interface instance, probably due to an error in the <i>SymbolicLinkName</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Possibly indicates an error in the <i>SymbolicLinkName</i>.

</td>
</tr>
</table>
 




## -remarks



<b>IoOpenDeviceInterfaceRegistryKey</b> opens a nonvolatile subkey of the registry key for the device interface instance specified by <i>SymbolicLinkName</i>. Drivers can store information in this subkey that is specific to this instance of the device interface, such as the default resolution for a camera. User-mode applications can access this subkey using <b>SetupDi<i>Xxx</i></b> routines.

The driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> to close the handle returned from this routine when access is no longer required.

Callers of <b>IoOpenDeviceInterfaceRegistryKey</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549180">IoGetDeviceInterfaceAlias</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549186">IoGetDeviceInterfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549506">IoRegisterDeviceInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>
 

 

