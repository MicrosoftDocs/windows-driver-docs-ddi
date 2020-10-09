---
UID: NF:wdm.MmIsDriverVerifyingByAddress
title: MmIsDriverVerifyingByAddress function (wdm.h)
description: The MmIsDriverVerifyingByAddress routine checks whether the kernel-mode driver that is identified by the specified image address is being verified or calls a driver that is being verified by Driver Verifier.
old-location: kernel\mmisdriververifyingbyaddress.htm
tech.root: kernel
ms.assetid: ccc20b5b-0f16-422d-8900-03b57f08b1bc
ms.date: 04/30/2018
keywords: ["MmIsDriverVerifyingByAddress function"]
ms.keywords: MmIsDriverVerifyingByAddress, MmIsDriverVerifyingByAddress routine [Kernel-Mode Driver Architecture], k106_37d22f13-de6a-4423-b148-9a7481570aaf.xml, kernel.mmisdriververifyingbyaddress, wdm/MmIsDriverVerifyingByAddress
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
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmIsDriverVerifyingByAddress
 - wdm/MmIsDriverVerifyingByAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmIsDriverVerifyingByAddress
---

# MmIsDriverVerifyingByAddress function


## -description

The <b>MmIsDriverVerifyingByAddress</b> routine checks whether the kernel-mode  driver that is identified by the specified image address is being verified or calls a driver that is being verified by <a href="/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a>.

## -parameters

### -param AddressWithinSection 

[in]
A pointer to the virtual address within the driver image. <b>MmIsDriverVerifyingByAddress</b> uses this address to determine which driver to check.

## -returns

<b>MmIsDriverVerifyingByAddress</b> returns <b>TRUE</b> if the specified driver either is in the driver verification list or imports calls to entry points in a driver that is in the driver verification list. Otherwise, this routine returns <b>FALSE</b>.

## -remarks

A kernel-mode driver can call this routine to determine whether it or another driver is being monitored by <a href="/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a>. Driver Verifier monitors kernel-mode drivers to detect illegal function calls or actions that might corrupt the system. To select drivers to be verified, you can use the <a href="/windows-hardware/drivers/devtest/verifier-command-line">Verifier Command Line</a> or <a href="/windows-hardware/drivers/devtest/driver-verifier-manager--windows-xp-and-later-">Driver Verifier Manager</a>. For more information about adding drivers to the driver verification list, see <a href="/windows-hardware/drivers/devtest/selecting-drivers-to-be-verified">Selecting Drivers to be Verified</a>.

A similar routine, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriververifying">MmIsDriverVerifying</a>, indicates whether a driver identified by a <a href="/windows-hardware/drivers/kernel/introduction-to-driver-objects">driver object</a> is being verified or calls a driver that is being verified.

Another related routine, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriversuspectforverifier">MmIsDriverSuspectForVerifier</a>, indicates whether a driver represented by a driver object is in the list of drivers that are selected to be verified.

For example, if driver A has an import table through which it calls one or more entry points in driver B, and driver B is in the driver verification list, then <code>MmIsDriverVerifyingByAddress(Aobj)</code> returns <b>TRUE</b> and <code>MmIsDriverSuspectForVerifier(Badr)</code> returns <b>TRUE</b>, where <code>Aobj</code> is a pointer to the driver object for A and <code>Badr</code> is an address in driver B. If driver A is not in the driver verification list, <code>MmIsDriverSuspectForVerifier(Aobj)</code> returns <b>FALSE</b>. Even if driver B does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifyingByAddress(Badr)</code> returns <b>TRUE</b> because driver B is in the driver verification list. If a driver C is not in the driver verification list and does not call entry points in any drivers that are in the driver verification list, <code>MmIsDriverVerifyingByAddress(Cadr)</code> and <code>MmIsDriverSuspectForVerifier(Cobj)</code> both return <b>FALSE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriversuspectforverifier">MmIsDriverSuspectForVerifier</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmisdriververifying">MmIsDriverVerifying</a>