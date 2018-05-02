---
UID: NE:wudfinterrupt._WDF_INTERRUPT_POLARITY
title: "_WDF_INTERRUPT_POLARITY"
author: windows-driver-content
description: The WDF_INTERRUPT_POLARITY enumeration type is used to specify an interrupt signal's polarity.
old-location: wdf\wdf_interrupt_polarity_umdf.htm
old-project: wdf
ms.assetid: 30E61DCE-D88C-47B5-B5CD-3C43C6157FBA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_INTERRUPT_POLARITY, PWDF_INTERRUPT_POLARITY, PWDF_INTERRUPT_POLARITY enumeration pointer, WDF_INTERRUPT_POLARITY, WDF_INTERRUPT_POLARITY enumeration, WdfInterruptActiveHigh, WdfInterruptActiveLow, WdfInterruptPolarityUnknown, _WDF_INTERRUPT_POLARITY, umdf.wdf_interrupt_polarity, wdf.wdf_interrupt_polarity_umdf, wudfinterrupt/PWDF_INTERRUPT_POLARITY, wudfinterrupt/WDF_INTERRUPT_POLARITY, wudfinterrupt/WdfInterruptActiveHigh, wudfinterrupt/WdfInterruptActiveLow, wudfinterrupt/WdfInterruptPolarityUnknown"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Windows
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
-	WDF_INTERRUPT_POLARITY
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_POLARITY, *PWDF_INTERRUPT_POLARITY
---

# _WDF_INTERRUPT_POLARITY enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464028">WDF_INTERRUPT_POLARITY</a> enumeration type is used to specify an interrupt signal's polarity.


## -enum-fields




### -field WdfInterruptPolarityUnknown

The interrupt signal's polarity is unknown.


### -field WdfInterruptActiveHigh

The interrupt signal is active when it is high.


### -field WdfInterruptActiveLow

The interrupt signal is active when it is low.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464028">WDF_INTERRUPT_POLARITY</a> enumeration type is used to specify a member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure.



