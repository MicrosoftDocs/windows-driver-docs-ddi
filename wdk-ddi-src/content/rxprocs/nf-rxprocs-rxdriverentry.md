---
UID: NF:rxprocs.RxDriverEntry
title: RxDriverEntry function (rxprocs.h)
description: RxDriverEntry is called by a monolithic network mini-redirector driver from its DriverEntry routine to initialize the RDBSS static library.
old-location: ifsk\rxdriverentry.htm
tech.root: ifsk
ms.date: 12/16/2021
keywords: ["RxDriverEntry function"]
ms.keywords: RxDriverEntry, RxDriverEntry routine [Installable File System Drivers], ifsk.rxdriverentry, rxprocs/RxDriverEntry, rxref_a882d71c-b6c3-4454-a45b-37b312af2069.xml
req.header: rxprocs.h
req.include-header: Rxprocs.h
req.target-type: Desktop
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RxDriverEntry
 - rxprocs/RxDriverEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxprocs.h
api_name:
 - RxDriverEntry
---

# RxDriverEntry function

## -description

**RxDriverEntry** is called by a monolithic network mini-redirector driver from its [**DriverEntry**](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine to initialize the RDBSS static library.

For non-monolithic drivers, this initialization routine is equivalent to the [**DriverEntry**](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine of the RDBSS.SYS device driver.

## -parameters

### -param DriverObject [in]


A pointer to the driver object of the network mini-redirector driver. Each driver receives a pointer to its driver object in a parameter to its [**DriverEntry**](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine. This driver object will be used to create the device object for the network mini-redirector driver.

### -param RegistryPath [in]

A pointer to a Unicode string containing the registry path to where driver parameters and other configuration data are stored. This registry path is normally located under a services entry for the specific network mini-redirector located under the *HKLM\System\CurrentControlSet\Services* key.

## -returns

**RxDriverEntry** returns STATUS_SUCCESS on success or one of the following error values on failure:

| Return code | Description |
| ----------- | ----------- |
| RXINIT_START | The initialization of RDBSS was started, but an error occurred. This error code is an internal RDBSS enum with a value of 5. |

## -remarks

A monolithic network mini-redirector driver which is linked statically with RDBSSLIB.LIB must call **RxDriverEntry** from its [**DriverEntry**](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine to initialize the copy of the RDBSSLIB library linked with the driver. **RxDriverEntry** must be called by a monolithic network mini-redirector driver before any other RDBSS routines are called.

After calling **RxDriverEntry** to initialize the copy of the RDBSS library near the start of its [**DriverEntry**](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine, the network mini-redirector driver would usually call [**RxRegisterMinirdr**](../mrx/nf-mrx-rxregisterminirdr.md) later in its **DriverEntry** routine to register with RDBSS.

If the **RxDriverEntry** call is successful, internal global RDBBS data structures are initialized. Various spinlocks and mutexes are created to protect these data structures. One of these data structures is the RDBSS_DATA structure which is the top structure in the RDBSS-memory data structure. The **DriverObject** parameter is stored in the **DriverObject** member of the RDBSS_DATA structure. **RxDriverEntry** also initializes tracing, logging, and debugging if this is enabled (a checked build, for example).

**RxDriverEntry** will also try to open the registry path passed as the **RegistryPath** parameter, treating this object as a case-insensitive string. If this registry key can be successfully opened, then an attempt will be made to open a Parameters registry key below this entry.

**RxDriverEntry** will also attempt to open the *HKLM\System\CurrentControlSet\Services\LanmanWorkStation\Parameters* registry key.

If this key can be opened, then an attempt will be made to read some values under this key depending on the version of the operating system.

On Windows XP and later, **RxDriverEntry** will attempt to open the *DisableByteRangeLockingOnReadOnlyFiles* value under the *LanmanWorkStation\Parameters* key.

This value is a DWORD that is treated as a boolean and stored as the boolean value for DisableByteRangeLockingOnReadOnlyFiles, an RDBSS variable for handling byte range locking on read only files. This variable affects how RDBSS handles a new SRV_OPEN request by the network mini-redirector on an FCB and decides whether it can be collapsed onto an existing SRV_OPEN if the attributes are compatible. If a network mini-redirector driver wants to change this behavior, the driver should set the value of DisableByteRangeLockingOnReadOnlyFiles to the appropriate value after the **RxDriverEntry** routine has returned. The RDBSSLIB.LIB static library exposes DisableByteRangeLockingOnReadOnlyFiles as an external variable.

On Windows 2000 and Windows XP, **RxDriverEntry** will attempt to open the *ReadAheadGranularity* value under the *LanmanWorkStation\Parameters* key.

This value is a DWORD that is treated as a number and stored as the value for an internal RDBSS option on the number of PAGE_SIZE pages for read ahead used by the Cache Manager. Any registry value greater than 16 is treated as if this value were limited to 16 (the maximum value currently allowed). This internal option is stored as the number of pages times the PAGE_SIZE on the processor (a maximum of 0x10000 or 64K for a 4K PAGE_SIZE, for example). On Windows 2000 and Windows XP, RDBSS calls [**CcSetReadAheadGranularity**](../ntifs/nf-ntifs-ccsetreadaheadgranularity.md) with this option for various create, read, and write operations. If a network mini-redirector driver wants to change this behavior, the driver should set the value of ReadAheadGranularity to the appropriate value after the **RxDriverEntry** routine has returned. The RDBSSLIB.LIB static library exposes ReadAheadGranularity as an external variable.

On X86 systems, 64K is the largest write that will be issued by the Memory Manager when issuing a paging write (flushes of the cache will be paging writes through the Memory Manager). For remote file systems, 64K is not the best choice. The most data that can be transferred in a single TDI network request would be less than 64K because of overhead for protocol information.

On Windows Server 2003, a registry value to set ReadAheadGranularity is not exposed and RDBSS defaults to 32K (8 4K PAGE_SIZE pages). This is the same default value adopted for local files systems.

**RxDriverEntry** retrieves a pointer to the kernel process that is running by calling [PsGetCurrentProcess](/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess) and stores this value in an internal RDBSS data structure. This kernel process is sometimes called the file system process.

**RxDriverEntry** then copies a pointer to the [**RxFsdDispatch**](../mrx/nf-mrx-rxfsddispatch.md) routine over all of the entries in the driver dispatch table. So if a monolithic network mini-redirector driver needs to receive specific IRPs for special processing before the RDBSS library, then a copy of its original driver dispatch table should be saved before calling **RxDriverEntry** and any routine pointers restored after the call to **RxDriverEntry** has returned. Note that RDBSS will also copy **RxFsdDispatch** to all the driver dispatch table entries when [**RxRegisterMinirdr**](../mrx/nf-mrx-rxregisterminirdr.md) is called unless an option is set to prevent this behavior.

For a non-monolithic network mini-redirector driver (the Microsoft SMB redirector), the RDBSS.SYS device driver is initialized in its own [**DriverEntry**](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine when loaded which internally calls **RxDriverEntry**. On a monolithic driver, the **RxDriverEntry** routine is exported from the RDBSSLIB.LIB static library and must be called explicitly by the network mini-redirector.

## -see-also

[**CcSetReadAheadGranularity**](../ntifs/nf-ntifs-ccsetreadaheadgranularity.md)

[**PsGetCurrentProcess**](../ntddk/nf-ntddk-psgetcurrentprocessid.md)

[**RxRegisterMinirdr**](../mrx/nf-mrx-rxregisterminirdr.md)

[**RxSetDomainForMailslotBroadcast**](../mrx/nf-mrx-rxsetdomainformailslotbroadcast.md)

[**RxStartMinirdr**](../mrx/nf-mrx-rxstartminirdr.md)

[**RxStopMinirdr**](../mrx/nf-mrx-rxstopminirdr.md)

[**RxUnregisterMinirdr**](../rxstruc/nf-rxstruc-rxunregisterminirdr.md)

[**RxpUnregisterMinirdr**](../mrx/nf-mrx-rxpunregisterminirdr.md)

[**__RxFillAndInstallFastIoDispatch**](../mrx/nf-mrx-__rxfillandinstallfastiodispatch.md)
