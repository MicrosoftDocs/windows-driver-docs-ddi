---
UID: NF:wudfinterrupt.WDF_INTERRUPT_INFO_INIT
title: WDF_INTERRUPT_INFO_INIT function
author: windows-driver-content
description: The WDF_INTERRUPT_INFO_INIT function initializes a WDF_INTERRUPT_INFO structure.
old-location: wdf\wdf_interrupt_info_init_umdf.htm
old-project: wdf
ms.assetid: CFFE19FB-289C-4002-AB07-AE342D855B20
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_INTERRUPT_INFO_INIT, WDF_INTERRUPT_INFO_INIT function, umdf.wdf_interrupt_info_init, wdf.wdf_interrupt_info_init_umdf, wudfinterrupt/WDF_INTERRUPT_INFO_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfinterrupt.h
api_name:
-	WDF_INTERRUPT_INFO_INIT
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WDF_INTERRUPT_INFO_INIT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464024">WDF_INTERRUPT_INFO_INIT</a> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure.


## -parameters




### -param InterruptInfo

TBD




#### - Info [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure.


## -returns



None




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464024">WDF_INTERRUPT_INFO_INIT</a> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure and sets the structure's <b>Size</b> member.

For more information about handling interrupts in framework-based drivers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Interrupts</a>.


#### Examples

For a code example that uses <a href="https://msdn.microsoft.com/library/windows/hardware/hh464024">WDF_INTERRUPT_INFO_INIT</a>, see <a href="https://msdn.microsoft.com/744D0FFE-6D3C-4AED-8935-63EE9B0AFA0F">IWDFInterrupt::GetInfo</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/744D0FFE-6D3C-4AED-8935-63EE9B0AFA0F">IWDFInterrupt::GetInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a>
 

 

