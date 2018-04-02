---
UID: NF:wdm.MmIsDriverSuspectForVerifier
title: MmIsDriverSuspectForVerifier function
author: windows-driver-content
description: The MmIsDriverSuspectForVerifier routine indicates whether the driver represented by the specified driver object is in the list of drivers that are selected to be verified by Driver Verifier.
old-location: kernel\mmisdriversuspectforverifier.htm
old-project: kernel
ms.assetid: 049BDC6E-2FB2-421F-9229-320F2ED98663
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: MmIsDriverSuspectForVerifier, MmIsDriverSuspectForVerifier routine [Kernel-Mode Driver Architecture], kernel.mmisdriversuspectforverifier, wdm/MmIsDriverSuspectForVerifier
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmIsDriverSuspectForVerifier
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmIsDriverSuspectForVerifier function


## -description


The <b>MmIsDriverSuspectForVerifier</b> routine indicates whether the driver represented by the specified <a href="https://msdn.microsoft.com/497ee2dc-671d-408e-b228-16dc24532375">driver object</a> is in the list of drivers that are selected to be verified by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a>.


## -parameters




### -param DriverObject [in]

A pointer to the driver object. This object is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a> structure that represents a loaded driver image. The driver receives this pointer as an input parameter to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine.


## -returns



<b>MmIsDriverSuspectForVerifier</b> returns <b>TRUE</b> if the driver is selected for verification. Otherwise, the routine returns <b>FALSE</b>.




## -remarks



A kernel-mode driver can call this routine to determine whether it is being monitored by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a>. Driver Verifier monitors kernel-mode drivers to detect illegal function calls or actions that might corrupt the system. To select drivers to be verified, you can use the <a href="https://msdn.microsoft.com/7cdf5277-7187-4e90-b22a-6f828f06e2fb">Verifier Command Line</a> or <a href="https://msdn.microsoft.com/37a7d348-8b55-44f7-86d6-6b195704b9fd">Driver Verifier Manager</a>. For more information about adding drivers to the driver verification list, see <a href="https://msdn.microsoft.com/a752dea1-f49c-4e58-9e56-6b54701c760e">Selecting Drivers to be Verified</a>.

A related routine, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554578">MmIsDriverVerifying</a>, returns <b>TRUE</b> if the specified driver either is in the driver verification list or imports calls to entry points in a driver that is in the driver verification list. Otherwise, <b>MmIsDriverVerifying</b> returns <b>FALSE</b>.

For example, if driver A has an import table through which it calls one or more entry points in driver B, and driver B is in the driver verification list, then <code>MmIsDriverVerifying(A)</code> returns <b>TRUE</b> and <code>MmIsDriverSuspectForVerifier(B)</code> returns <b>TRUE</b>. If driver A is not in the driver verification list, <code>MmIsDriverSuspectForVerifier(A)</code> returns <b>FALSE</b>. Even if driver B does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifying(B)</code> returns <b>TRUE</b> because driver B is in the driver verification list. If a driver C is not in the driver verification list and does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifying(C)</code> and <code>MmIsDriverSuspectForVerifier(C)</code> both return <b>FALSE</b>.

Another related routine, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554583">MmIsDriverVerifyingByAddress</a>, indicates whether a driver identified by a driver image address is being verified or calls a driver that is being verified. <b>MmIsDriverVerifyingByAddress</b> is available starting with Windows Vista.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554578">MmIsDriverVerifying</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554583">MmIsDriverVerifyingByAddress</a>
 

 

