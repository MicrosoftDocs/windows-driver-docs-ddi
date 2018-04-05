---
UID: NF:wdm.MmIsDriverVerifyingByAddress
title: MmIsDriverVerifyingByAddress function
author: windows-driver-content
description: The MmIsDriverVerifyingByAddress routine checks whether the kernel-mode driver that is identified by the specified image address is being verified or calls a driver that is being verified by Driver Verifier.
old-location: kernel\mmisdriververifyingbyaddress.htm
old-project: kernel
ms.assetid: ccc20b5b-0f16-422d-8900-03b57f08b1bc
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: MmIsDriverVerifyingByAddress, MmIsDriverVerifyingByAddress routine [Kernel-Mode Driver Architecture], k106_37d22f13-de6a-4423-b148-9a7481570aaf.xml, kernel.mmisdriververifyingbyaddress, wdm/MmIsDriverVerifyingByAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmIsDriverVerifyingByAddress
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmIsDriverVerifyingByAddress function


## -description


The <b>MmIsDriverVerifyingByAddress</b> routine checks whether the kernel-mode  driver that is identified by the specified image address is being verified or calls a driver that is being verified by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a>.


## -parameters




### -param AddressWithinSection [in]

A pointer to the virtual address within the driver image. <b>MmIsDriverVerifyingByAddress</b> uses this address to determine which driver to check.


## -returns



<b>MmIsDriverVerifyingByAddress</b> returns <b>TRUE</b> if the specified driver either is in the driver verification list or imports calls to entry points in a driver that is in the driver verification list. Otherwise, this routine returns <b>FALSE</b>.




## -remarks



A kernel-mode driver can call this routine to determine whether it or another driver is being monitored by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a>. Driver Verifier monitors kernel-mode drivers to detect illegal function calls or actions that might corrupt the system. To select drivers to be verified, you can use the <a href="https://msdn.microsoft.com/7cdf5277-7187-4e90-b22a-6f828f06e2fb">Verifier Command Line</a> or <a href="https://msdn.microsoft.com/37a7d348-8b55-44f7-86d6-6b195704b9fd">Driver Verifier Manager</a>. For more information about adding drivers to the driver verification list, see <a href="https://msdn.microsoft.com/a752dea1-f49c-4e58-9e56-6b54701c760e">Selecting Drivers to be Verified</a>.

A similar routine, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554578">MmIsDriverVerifying</a>, indicates whether a driver identified by a <a href="https://msdn.microsoft.com/497ee2dc-671d-408e-b228-16dc24532375">driver object</a> is being verified or calls a driver that is being verified.

Another related routine, <a href="https://msdn.microsoft.com/library/windows/hardware/jj552960">MmIsDriverSuspectForVerifier</a>, indicates whether a driver represented by a driver object is in the list of drivers that are selected to be verified.

For example, if driver A has an import table through which it calls one or more entry points in driver B, and driver B is in the driver verification list, then <code>MmIsDriverVerifyingByAddress(Aobj)</code> returns <b>TRUE</b> and <code>MmIsDriverSuspectForVerifier(Badr)</code> returns <b>TRUE</b>, where <code>Aobj</code> is a pointer to the driver object for A and <code>Badr</code> is an address in driver B. If driver A is not in the driver verification list, <code>MmIsDriverSuspectForVerifier(Aobj)</code> returns <b>FALSE</b>. Even if driver B does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifyingByAddress(Badr)</code> returns <b>TRUE</b> because driver B is in the driver verification list. If a driver C is not in the driver verification list and does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifyingByAddress(Cadr)</code> and <code>MmIsDriverSuspectForVerifier(Cobj)</code> both return <b>FALSE</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj552960">MmIsDriverSuspectForVerifier</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554578">MmIsDriverVerifying</a>
 

 

