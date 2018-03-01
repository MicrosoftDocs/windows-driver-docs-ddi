---
UID: NF:wdm.MmIsDriverSuspectForVerifier
title: MmIsDriverSuspectForVerifier function
author: windows-driver-content
description: The MmIsDriverSuspectForVerifier routine indicates whether the driver represented by the specified driver object is in the list of drivers that are selected to be verified by Driver Verifier.
old-location: kernel\mmisdriversuspectforverifier.htm
old-project: kernel
ms.assetid: 049BDC6E-2FB2-421F-9229-320F2ED98663
ms.author: windowsdriverdev
ms.date: 2/24/2018
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


## -syntax


````
LOGICAL MmIsDriverSuspectForVerifier(
  _In_ struct _DRIVER_OBJECT *DriverObject
);
````


## -parameters




### -param DriverObject [in]

A pointer to the driver object. This object is a <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure that represents a loaded driver image. The driver receives this pointer as an input parameter to its <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine.


## -returns



<b>MmIsDriverSuspectForVerifier</b> returns <b>TRUE</b> if the driver is selected for verification. Otherwise, the routine returns <b>FALSE</b>.




## -remarks



A kernel-mode driver can call this routine to determine whether it is being monitored by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a>. Driver Verifier monitors kernel-mode drivers to detect illegal function calls or actions that might corrupt the system. To select drivers to be verified, you can use the <a href="https://msdn.microsoft.com/7cdf5277-7187-4e90-b22a-6f828f06e2fb">Verifier Command Line</a> or <a href="https://msdn.microsoft.com/37a7d348-8b55-44f7-86d6-6b195704b9fd">Driver Verifier Manager</a>. For more information about adding drivers to the driver verification list, see <a href="https://msdn.microsoft.com/a752dea1-f49c-4e58-9e56-6b54701c760e">Selecting Drivers to be Verified</a>.

A related routine, <a href="..\wdm\nf-wdm-mmisdriververifying.md">MmIsDriverVerifying</a>, returns <b>TRUE</b> if the specified driver either is in the driver verification list or imports calls to entry points in a driver that is in the driver verification list. Otherwise, <b>MmIsDriverVerifying</b> returns <b>FALSE</b>.

For example, if driver A has an import table through which it calls one or more entry points in driver B, and driver B is in the driver verification list, then <code>MmIsDriverVerifying(A)</code> returns <b>TRUE</b> and <code>MmIsDriverSuspectForVerifier(B)</code> returns <b>TRUE</b>. If driver A is not in the driver verification list, <code>MmIsDriverSuspectForVerifier(A)</code> returns <b>FALSE</b>. Even if driver B does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifying(B)</code> returns <b>TRUE</b> because driver B is in the driver verification list. If a driver C is not in the driver verification list and does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifying(C)</code> and <code>MmIsDriverSuspectForVerifier(C)</code> both return <b>FALSE</b>.

Another related routine, <a href="..\wdm\nf-wdm-mmisdriververifyingbyaddress.md">MmIsDriverVerifyingByAddress</a>, indicates whether a driver identified by a driver image address is being verified or calls a driver that is being verified. <b>MmIsDriverVerifyingByAddress</b> is available starting with Windows Vista.




## -see-also

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>



<a href="..\wdm\nf-wdm-mmisdriververifyingbyaddress.md">MmIsDriverVerifyingByAddress</a>



<a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a>



<a href="..\wdm\nf-wdm-mmisdriververifying.md">MmIsDriverVerifying</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmIsDriverSuspectForVerifier routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

