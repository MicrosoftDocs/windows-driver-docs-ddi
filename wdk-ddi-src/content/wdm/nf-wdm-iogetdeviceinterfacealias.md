---
UID: NF:wdm.IoGetDeviceInterfaceAlias
title: IoGetDeviceInterfaceAlias function (wdm.h)
description: The IoGetDeviceInterfaceAlias routine returns the alias device interface of the specified device interface instance, if the alias exists.
old-location: kernel\iogetdeviceinterfacealias.htm
tech.root: kernel
ms.assetid: 667c9524-be12-4f02-b921-6067abfb1dde
ms.date: 04/30/2018
ms.keywords: IoGetDeviceInterfaceAlias, IoGetDeviceInterfaceAlias routine [Kernel-Mode Driver Architecture], k104_e33a51e9-4576-4558-9967-9ea27467c326.xml, kernel.iogetdeviceinterfacealias, wdm/IoGetDeviceInterfaceAlias
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoGetDeviceInterfaceAlias
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetDeviceInterfaceAlias function


## -description


The <b>IoGetDeviceInterfaceAlias</b> routine returns the alias device interface of the specified device interface instance, if the alias exists.


## -parameters




### -param SymbolicLinkName [in]

Pointer to the name of the device interface instance for which to retrieve an alias. The caller typically received this string from a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdeviceinterfaces">IoGetDeviceInterfaces</a> or in a PnP notification structure.


### -param AliasInterfaceClassGuid [in]

Pointer to a GUID specifying the interface class of the alias to retrieve.


### -param AliasSymbolicLinkName [out]

Specifies a pointer to a <b>NULL</b> Unicode string. On successful return, <i>AliasSymbolicLinkName</i>.<b>Buffer</b> points to a string containing the name of the alias. The caller must free the Unicode string with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a> when it is no longer needed.


## -returns



<b>IoGetDeviceInterfaceAlias</b> returns STATUS_SUCCESS if the call was successful. Possible error return values are described following.

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
Possibly indicates that there is no alias of the specified interface class.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
Possibly indicates that there is no alias of the specified interface class.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Possibly indicates an invalid <i>SymbolicLinkName</i> or an invalid <i>AliasClassGuid</i>.

</td>
</tr>
</table>
 




## -remarks



Device interfaces are considered aliases if they are exposed by the same underlying device and have identical interface reference strings, but are of different interface classes.

The <i>SymbolicLinkName</i> parameter specifies a device interface instance for a particular device, belonging to a particular interface class, with a particular reference string. <b>IoGetDeviceInterfaceAlias</b> returns another device interface instance for the same device and reference string, but of a different interface class, if it exists.

For example, the function driver for a fault-tolerant volume could register and set two device interfaces, one of the fault-tolerant-volume interface class and one of the volume interface class. Another driver could call <b>IoGetDeviceInterfaceAlias</b> with the symbolic link for one of the interfaces and ask whether the other interface exists by specifying its interface class.

Two device interfaces with <b>NULL</b> reference strings are aliases if they are exposed by the same underlying device and have different interface class GUIDs.

Callers of <b>IoGetDeviceInterfaceAlias</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioregisterdeviceinterface">IoRegisterDeviceInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlfreeunicodestring">RtlFreeUnicodeString</a>
 

 

