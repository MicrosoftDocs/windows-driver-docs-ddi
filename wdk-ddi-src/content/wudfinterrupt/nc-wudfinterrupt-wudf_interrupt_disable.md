---
UID: NC:wudfinterrupt.WUDF_INTERRUPT_DISABLE
title: WUDF_INTERRUPT_DISABLE (wudfinterrupt.h)
description: A driver's OnInterruptDisable event callback function disables a specified hardware interrupt.
old-location: wdf\oninterruptdisable.htm
tech.root: wdf
ms.assetid: 3ADBD4C2-075E-4988-BF13-EB0C3E0C02BF
ms.date: 02/26/2018
keywords: ["WUDF_INTERRUPT_DISABLE callback function"]
ms.keywords: OnInterruptDisable, OnInterruptDisable callback function, WUDF_INTERRUPT_DISABLE, WUDF_INTERRUPT_DISABLE callback, umdf.oninterruptdisable, wdf.oninterruptdisable, wudfinterrupt/OnInterruptDisable
f1_keywords:
 - "wudfinterrupt/OnInterruptDisable"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wudfinterrupt.h
api_name:
- OnInterruptDisable
product:
- Windows
targetos: Windows
req.typenames: 
---

# WUDF_INTERRUPT_DISABLE callback function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <i>OnInterruptDisable</i> event callback function disables a specified hardware interrupt.


## -parameters




### -param Interrupt


### -param AssociatedDevice








#### - pAssociatedDevice [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface that the driver used to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt">CreateInterrupt</a>. 


#### - pInterrupt [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfinterrupt">IWDFInterrupt</a> interface.


## -returns



<i>OnInterruptDisable</i>  must return S_OK if the operation succeeds. Otherwise, the callback should return one of the error codes that are defined in Winerror.h.




## -remarks



To register an <i>OnInterruptDisable</i> callback function, your driver must place the callback function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/ns-wudfinterrupt-_wudf_interrupt_config">WUDF_INTERRUPT_CONFIG</a> structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt">IWDFDevice::CreateInterrupt</a>.


The framework calls the driver's <i>OnInterruptDisable</i> callback function each time the device leaves its working (D0) state. Additionally, a driver can cause the framework to call the <i>OnInterruptDisable</i> callback function by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfinterrupt-disable">IWDFInterrupt::Disable</a>.


Before calling the <i>OnInterruptDisable</i> callback function, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardwareinterrupt-ond0exitpreinterruptsdisabled">OnD0ExitPreInterruptsDisabled</a> event callback function and acquires the user-mode interrupt lock.


For more information about handling interrupts in UMDF drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts">Accessing Hardware and Handling Interrupts</a>.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createinterrupt">IWDFDevice::CreateInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nc-wudfinterrupt-wudf_interrupt_enable">OnInterruptEnable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/ns-wudfinterrupt-_wudf_interrupt_config">WUDF_INTERRUPT_CONFIG</a>
 

 

