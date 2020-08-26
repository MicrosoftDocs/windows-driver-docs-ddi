---
UID: NF:wdm.MmIsDriverVerifying
title: MmIsDriverVerifying function (wdm.h)
description: The MmIsDriverVerifying routine indicates whether the kernel-mode driver that is identified by the specified driver object is being verified or calls a driver that is being verified by Driver Verifier.
old-location: kernel\mmisdriververifying.htm
tech.root: kernel
ms.assetid: 74bfe9fb-f751-46a6-a95b-f715ebedd2ec
ms.date: 04/30/2018
keywords: ["MmIsDriverVerifying function"]
ms.keywords: MmIsDriverVerifying, MmIsDriverVerifying routine [Kernel-Mode Driver Architecture], k106_50d610e1-b3ae-41c5-a696-13ab0cf314b6.xml, kernel.mmisdriververifying, wdm/MmIsDriverVerifying
f1_keywords:
 - "wdm/MmIsDriverVerifying"
 - "MmIsDriverVerifying"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmIsDriverVerifying
targetos: Windows
req.typenames: 
---

# MmIsDriverVerifying function


## -description


The <b>MmIsDriverVerifying</b> routine indicates whether the kernel-mode driver that is identified by the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-driver-objects">driver object</a> is being verified or calls a driver that is being verified by <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a>.


## -parameters




### -param DriverObject 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure that represents a driver object. The driver receives this pointer as an input parameter to its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. 


## -returns



<b>MmIsDriverVerifying</b> returns <b>TRUE</b> if the specified driver either is in the driver verification list or imports calls to entry points in a driver that is in the driver verification list. Otherwise, this routine returns <b>FALSE</b>.




## -remarks



A kernel-mode driver can call this routine to determine whether it is being monitored by <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a>. Driver Verifier monitors kernel-mode drivers to detect illegal function calls or actions that might corrupt the system. To select drivers to be verified, you can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/verifier-command-line">Verifier Command Line</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/driver-verifier-manager--windows-xp-and-later-">Driver Verifier Manager</a>. For more information about adding drivers to the driver verification list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/selecting-drivers-to-be-verified">Selecting Drivers to be Verified</a>.

A similar routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriververifyingbyaddress">MmIsDriverVerifyingByAddress</a>, indicates whether a driver identified by a driver image address is being verified or calls a driver that is being verified. <b>MmIsDriverVerifyingByAddress</b> is available starting with Windows Vista.

Another related routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriversuspectforverifier">MmIsDriverSuspectForVerifier</a>, indicates whether a driver represented by a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-driver-objects">driver object</a> is in the list of drivers that are selected to be verified. <b>MmIsDriverSuspectForVerifier</b> is available starting with Windows 8.

For example, if driver A has an import table through which it calls one or more entry points in driver B, and driver B is in the driver verification list, then <code>MmIsDriverVerifying(A)</code> returns <b>TRUE</b> and <code>MmIsDriverSuspectForVerifier(B)</code> returns <b>TRUE</b>. If driver A is not in the driver verification list, <code>MmIsDriverSuspectForVerifier(A)</code> returns <b>FALSE</b>. Even if driver B does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifying(B)</code> returns <b>TRUE</b> because driver B is in the driver verification list. If a driver C is not in the driver verification list and does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifying(C)</code> and <code>MmIsDriverSuspectForVerifier(C)</code> both return <b>FALSE</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriververifyingbyaddress">MmIsDriverVerifyingByAddress</a>
 

 

