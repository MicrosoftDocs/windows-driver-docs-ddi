---
UID: NF:wdm.IoCreateUnprotectedSymbolicLink
title: IoCreateUnprotectedSymbolicLink function (wdm.h)
description: The IoCreateUnprotectedSymbolicLink routine sets up an unprotected symbolic link between a device object name and a corresponding Win32-visible name.
old-location: kernel\iocreateunprotectedsymboliclink.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoCreateUnprotectedSymbolicLink function"]
ms.keywords: IoCreateUnprotectedSymbolicLink, IoCreateUnprotectedSymbolicLink routine [Kernel-Mode Driver Architecture], k104_72bb6571-da2d-4027-bfcd-24438e3bd08a.xml, kernel.iocreateunprotectedsymboliclink, wdm/IoCreateUnprotectedSymbolicLink
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive4, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCreateUnprotectedSymbolicLink
 - wdm/IoCreateUnprotectedSymbolicLink
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCreateUnprotectedSymbolicLink
---

# IoCreateUnprotectedSymbolicLink function


## -description

The <b>IoCreateUnprotectedSymbolicLink</b> routine sets up an unprotected symbolic link between a device object name and a corresponding Win32-visible name.

## -parameters

### -param SymbolicLinkName [in]


Supplies the symbolic link name as a Unicode string.

### -param DeviceName [in]


Supplies the name of the device object to which the symbolic link name refers.

## -returns

<b>IoCreateUnprotectedSymbolicLink</b> returns the final status of the operation.

## -remarks

WDM drivers do not name device objects and therefore should not use this routine. Instead, a WDM driver should call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterdeviceinterface">IoRegisterDeviceInterface</a> to set up a symbolic link. 

<b>IoCreateUnprotectedSymbolicLink</b> can be used by drivers if the user needs to be able to manipulate the symbolic link. For example, the parallel and serial drivers create unprotected symbolic links for LPTx and COMx, so that users can manipulate and reassign them by using the MODE command.

In general, drivers should call this routine instead of <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatesymboliclink">IoCreateSymbolicLink</a> if a protected subsystem lets end users change what a named device references as, for example, when using LPT1 to access a network printer.

For more information about when to use <b>IoCreateSymbolicLink</b>, see <a href="/windows-hardware/drivers/kernel/named-device-objects">Named Device Objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioassignarcname">IoAssignArcName</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatesymboliclink">IoCreateSymbolicLink</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iodeletesymboliclink">IoDeleteSymbolicLink</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterdeviceinterface">IoRegisterDeviceInterface</a>
