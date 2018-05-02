---
UID: NC:wudfinterrupt.WUDF_INTERRUPT_DISABLE
title: WUDF_INTERRUPT_DISABLE
author: windows-driver-content
description: A driver's OnInterruptDisable event callback function disables a specified hardware interrupt.
old-location: wdf\oninterruptdisable.htm
old-project: wdf
ms.assetid: 3ADBD4C2-075E-4988-BF13-EB0C3E0C02BF
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OnInterruptDisable, OnInterruptDisable callback function, WUDF_INTERRUPT_DISABLE, WUDF_INTERRUPT_DISABLE callback, umdf.oninterruptdisable, wdf.oninterruptdisable, wudfinterrupt/OnInterruptDisable
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wudfinterrupt.h
api_name:
-	OnInterruptDisable
product:
- Windows
targetos: Windows
req.typenames: 
---

# WUDF_INTERRUPT_DISABLE callback function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <i>OnInterruptDisable</i> event callback function disables a specified hardware interrupt.


## -parameters




### -param Interrupt


### -param AssociatedDevice








#### - pAssociatedDevice [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface that the driver used to call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451208">CreateInterrupt</a>. 


#### - pInterrupt [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451283">IWDFInterrupt</a> interface.


## -returns



<i>OnInterruptDisable</i>  must return S_OK if the operation succeeds. Otherwise, the callback should return one of the error codes that are defined in Winerror.h.




## -remarks



To register an <i>OnInterruptDisable</i> callback function, your driver must place the callback function's address in a <a href="https://msdn.microsoft.com/library/windows/hardware/hh464084">WUDF_INTERRUPT_CONFIG</a> structure before calling <a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice::CreateInterrupt</a>.


The framework calls the driver's <i>OnInterruptDisable</i> callback function each time the device leaves its working (D0) state. Additionally, a driver can cause the framework to call the <i>OnInterruptDisable</i> callback function by calling <a href="https://msdn.microsoft.com/D87C868D-9538-4752-AEBD-2A15E53628CF">IWDFInterrupt::Disable</a>.


Before calling the <i>OnInterruptDisable</i> callback function, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439755">OnD0ExitPreInterruptsDisabled</a> event callback function and acquires the user-mode interrupt lock.


For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.


#### Examples

The function type is declared in <i>Wudfinterrupt.h</i>, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
__drv_functionClass(WUDF_INTERRUPT_DISABLE)
HRESULT
WUDF_INTERRUPT_DISABLE(
    _In_
    IWDFInterrupt* Interrupt,
    _In_
    IWDFDevice* AssociatedDevice
    );

typedef WUDF_INTERRUPT_DISABLE *PFN_WUDF_INTERRUPT_DISABLE;</pre>
</td>
</tr>
</table></span></div>
To define an <i>OnInterruptDisable</i> callback function that is named <i>MyInterruptDisable</i>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WUDF_INTERRUPT_DISABLE  MyInterruptDisable;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT
  MyInterruptDisable (
    IN IWDFInterrupt* pInterrupt,
    IN IWDFDevice*  pAssociatedDevice
    )
  {…}

</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice::CreateInterrupt</a>



<a href="https://msdn.microsoft.com/6C091427-59FF-4101-ACD6-353C959794F6">OnInterruptEnable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464084">WUDF_INTERRUPT_CONFIG</a>
 

 

