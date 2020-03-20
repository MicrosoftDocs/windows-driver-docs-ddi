---
UID: NF:wdm.MmIsDriverSuspectForVerifier
title: MmIsDriverSuspectForVerifier function (wdm.h)
description: The MmIsDriverSuspectForVerifier routine indicates whether the driver represented by the specified driver object is in the list of drivers that are selected to be verified by Driver Verifier.
old-location: kernel\mmisdriversuspectforverifier.htm
tech.root: kernel
ms.assetid: 049BDC6E-2FB2-421F-9229-320F2ED98663
ms.date: 04/30/2018
keywords: ["MmIsDriverSuspectForVerifier function"]
ms.keywords: MmIsDriverSuspectForVerifier, MmIsDriverSuspectForVerifier routine [Kernel-Mode Driver Architecture], kernel.mmisdriversuspectforverifier, wdm/MmIsDriverSuspectForVerifier
f1_keywords:
 - "wdm/MmIsDriverSuspectForVerifier"
req.header: wdm.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
- MmIsDriverSuspectForVerifier
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmIsDriverSuspectForVerifier function


## -description


The <b>MmIsDriverSuspectForVerifier</b> routine indicates whether the driver represented by the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-driver-objects">driver object</a> is in the list of drivers that are selected to be verified by <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a>.


## -parameters




### -param DriverObject [in]

A pointer to the driver object. This object is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure that represents a loaded driver image. The driver receives this pointer as an input parameter to its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine.


## -returns



<b>MmIsDriverSuspectForVerifier</b> returns <b>TRUE</b> if the driver is selected for verification. Otherwise, the routine returns <b>FALSE</b>.




## -remarks



A kernel-mode driver can call this routine to determine whether it is being monitored by <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a>. Driver Verifier monitors kernel-mode drivers to detect illegal function calls or actions that might corrupt the system. To select drivers to be verified, you can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/verifier-command-line">Verifier Command Line</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/driver-verifier-manager--windows-xp-and-later-">Driver Verifier Manager</a>. For more information about adding drivers to the driver verification list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/selecting-drivers-to-be-verified">Selecting Drivers to be Verified</a>.

A related routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriververifying">MmIsDriverVerifying</a>, returns <b>TRUE</b> if the specified driver either is in the driver verification list or imports calls to entry points in a driver that is in the driver verification list. Otherwise, <b>MmIsDriverVerifying</b> returns <b>FALSE</b>.

For example, if driver A has an import table through which it calls one or more entry points in driver B, and driver B is in the driver verification list, then <code>MmIsDriverVerifying(A)</code> returns <b>TRUE</b> and <code>MmIsDriverSuspectForVerifier(B)</code> returns <b>TRUE</b>. If driver A is not in the driver verification list, <code>MmIsDriverSuspectForVerifier(A)</code> returns <b>FALSE</b>. Even if driver B does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifying(B)</code> returns <b>TRUE</b> because driver B is in the driver verification list. If a driver C is not in the driver verification list and does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifying(C)</code> and <code>MmIsDriverSuspectForVerifier(C)</code> both return <b>FALSE</b>.

Another related routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriververifyingbyaddress">MmIsDriverVerifyingByAddress</a>, indicates whether a driver identified by a driver image address is being verified or calls a driver that is being verified. <b>MmIsDriverVerifyingByAddress</b> is available starting with Windows Vista.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriververifying">MmIsDriverVerifying</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriververifyingbyaddress">MmIsDriverVerifyingByAddress</a>
 

 

