---
UID: NF:wudfinterrupt.WUDF_INTERRUPT_CONFIG_INIT
title: WUDF_INTERRUPT_CONFIG_INIT function
author: windows-driver-content
description: The WUDF_INTERRUPT_CONFIG_INIT function initializes a WUDF_INTERRUPT_CONFIG structure.
old-location: wdf\wudf_interrupt_config_init.htm
old-project: wdf
ms.assetid: 71011FDF-547E-4FF0-9015-E8E09FDF950E
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WUDF_INTERRUPT_CONFIG_INIT, wdf.wudf_interrupt_config_init, WUDF_INTERRUPT_CONFIG_INIT function, wudfinterrupt/WUDF_INTERRUPT_CONFIG_INIT, umdf.wudf_interrupt_config_init
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfinterrupt.h
apiname:
-	WUDF_INTERRUPT_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WUDF_INTERRUPT_CONFIG_INIT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WUDF_INTERRUPT_CONFIG_INIT</b> function initializes a <a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a> structure.




## -syntax


````
void WUDF_INTERRUPT_CONFIG_INIT(
  _Out_    PWUDF_INTERRUPT_CONFIG      Configuration,
  _In_     PFN_WUDF_INTERRUPT_NOTIFY   OnInterruptIsr,
  _In_opt_ PFN_WUDF_INTERRUPT_WORKITEM OnInterruptWorkItem
);
````


## -parameters




#### - Configuration [out]

A pointer to a <a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a> structure.


#### - OnInterruptIsr [in]

A pointer to the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_isr.md">OnInterruptIsr</a> event callback function.


#### - OnInterruptWorkItem [in, optional]

A pointer to the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_workitem.md">OnInterruptWorkItem</a> event callback function, or NULL.


## -returns


This function does not return a value.



## -remarks


The <b>WUDF_INTERRUPT_CONFIG_INIT</b> function zeros the specified <a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a> structure and sets its <b>Size</b> member to the structure's size. It also stores the specified callback function pointer(s).

<b>WUDF_INTERRUPT_CONFIG_INIT</b> initializes the configuration structure's <b>ShareVector</b> member to <b>WdfUseDefault</b> and the <b>AutomaticSerialization</b> member to FALSE.


