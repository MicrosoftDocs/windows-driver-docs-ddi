---
UID: NE:wudfinterrupt._WDF_INTERRUPT_PRIORITY
title: _WDF_INTERRUPT_PRIORITY
author: windows-driver-content
description: The WDF_INTERRUPT_PRIORITY enumeration type identifies relative priorities for device interrupts.
old-location: wdf\wdf_interrupt_priority_umdf.htm
old-project: wdf
ms.assetid: ECAB84B8-1C39-473C-A6AE-41D1EBDB1FF4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wudfinterrupt/PWDF_INTERRUPT_PRIORITY, wudfinterrupt/WDF_INTERRUPT_PRIORITY, WDF_INTERRUPT_PRIORITY enumeration, wudfinterrupt/WdfIrqPriorityUndefined, wudfinterrupt/WdfIrqPriorityHigh, wudfinterrupt/WdfIrqPriorityLow, umdf.wdf_interrupt_priority, *PWDF_INTERRUPT_PRIORITY, WdfIrqPriorityNormal, PWDF_INTERRUPT_PRIORITY, WDF_INTERRUPT_PRIORITY, _WDF_INTERRUPT_PRIORITY, WdfIrqPriorityUndefined, WdfIrqPriorityLow, wudfinterrupt/WdfIrqPriorityNormal, wdf.wdf_interrupt_priority_umdf, WdfIrqPriorityHigh, PWDF_INTERRUPT_PRIORITY enumeration pointer
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Wudfinterrupt.h
apiname: 
-	WDF_INTERRUPT_PRIORITY
product: Windows
targetos: Windows
req.typenames: *PWDF_INTERRUPT_PRIORITY, WDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# _WDF_INTERRUPT_PRIORITY enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


      The <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_priority.md">WDF_INTERRUPT_PRIORITY</a> enumeration type identifies relative priorities for device interrupts.


## -syntax


````
typedef enum _WDF_INTERRUPT_PRIORITY { 
  WdfIrqPriorityUndefined  = 0,
  WdfIrqPriorityLow        = 1,
  WdfIrqPriorityNormal     = 2,
  WdfIrqPriorityHigh       = 3
} WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY;
````


## -enum-fields




### -field WdfIrqPriorityUndefined

The relative priority of a device's interrupt is undefined.


### -field WdfIrqPriorityLow

The device's interrupt has a relatively low priority, typically because the interrupt does not have to be serviced immediately.


### -field WdfIrqPriorityNormal

The device's interrupt priority is neither relatively low nor relatively high.


### -field WdfIrqPriorityHigh

The device's interrupt has a relatively high priority, typically because the interrupt must be serviced immediately.


## -remarks


The <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_priority.md">WDF_INTERRUPT_PRIORITY</a> enumeration type is used as input to the <a href="https://msdn.microsoft.com/EDBCBB37-41A4-4234-BE8C-4C8739BC287B">IWDFInterrupt::SetPolicy</a> method.



## -see-also

<a href="https://msdn.microsoft.com/EDBCBB37-41A4-4234-BE8C-4C8739BC287B">IWDFInterrupt::SetPolicy</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_PRIORITY enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

