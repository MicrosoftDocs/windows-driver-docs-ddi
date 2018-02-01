---
UID: NC:wudfinterrupt.WUDF_INTERRUPT_ISR
title: WUDF_INTERRUPT_ISR
author: windows-driver-content
description: A driver's OnInterruptIsr event callback function services a hardware interrupt.
old-location: wdf\oninterruptisr.htm
old-project: wdf
ms.assetid: D4B8182A-67A5-4D64-A95C-5EB6A1C1E4F0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.oninterruptisr, OnInterruptIsr callback function, OnInterruptIsr, WUDF_INTERRUPT_ISR, WUDF_INTERRUPT_ISR, wudfinterrupt/OnInterruptIsr, umdf.oninterruptisr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wudfinterrupt.h
apiname:
-	OnInterruptIsr
product: Windows
targetos: Windows
req.typenames: WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, *PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
req.product: Windows 10 or later.
---

# WUDF_INTERRUPT_ISR callback


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <i>OnInterruptIsr</i> event callback function services a hardware interrupt.


## -prototype


````
WUDF_INTERRUPT_ISR OnInterruptIsr;

BOOLEAN OnInterruptIsr(
  _In_ IWDFInterrupt *pInterrupt,
  _In_ ULONG         MessageID,
  _In_ ULONG         Reserved
)
{ ... }
````


## -parameters




### -param Interrupt



### -param MessageID [in]

If the device is using message-signaled interrupts (MSIs), this parameter is the message number that identifies the device's hardware interrupt message. Otherwise, this value is 0.


### -param Reserved [in]

Reserved for system use.


#### - pInterrupt [in]

A pointer to <a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a> interface.


## -returns


Returns TRUE if the driver acknowledges ownership of the interrupt, and has stopped and acknowledged the interrupt on its device. Otherwise, returns FALSE.



## -remarks


To register an <i>OnInterruptIsr</i> callback function, your driver must place the callback function's address in a <a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a> structure before calling <a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice3::CreateInterrupt</a>.


The <i>OnInterruptIsr</i> callback function is a UMDF driver's interrupt service routine (ISR), which is called at PASSIVE_LEVEL when a hardware interrupt occurs.

For an edge-triggered interrupt or message-signaled interrupt (MSI), the framework calls <i>OnInterruptIsr</i> outside of the operating system's interrupt dispatch context. This is because UMDF allows only non-shared edge-triggered or MSI interrupts, and the driver does not need to interact with its hardware within this context.

For a level-triggered interrupt, the framework calls <i>OnInterruptIsr</i> in the context of the operating system's interrupt dispatch. As a result, the operating system's interrupt dispatch thread is blocked in kernel-mode waiting for a response from the driver.

Typically, <i>OnInterruptIsr</i> saves any volatile information that might be lost and clears the hardware interrupt. For a level-triggered interrupt, the driver should stop and acknowledge the interrupt on the device and then return TRUE if it owns the interrupt. The driver should do any further processing in an <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_workitem.md">OnInterruptWorkItem</a> callback. To queue a work item, the driver calls the <a href="https://msdn.microsoft.com/5C6DC011-4032-4DB6-AE17-88E510DF9A3A">IWDFInterrupt::QueueWorkItemForIsr</a> method.


For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.



## -see-also

<a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice3::CreateInterrupt</a>

<a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_workitem.md">OnInterruptWorkItem</a>

<a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WUDF_INTERRUPT_ISR callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

