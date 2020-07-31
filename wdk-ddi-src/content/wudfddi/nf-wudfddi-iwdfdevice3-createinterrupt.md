---
UID: NF:wudfddi.IWDFDevice3.CreateInterrupt
title: IWDFDevice3::CreateInterrupt (wudfddi.h)
description: The CreateInterrupt method creates a framework interrupt object.
old-location: wdf\iwdfdevice3_createinterrupt.htm
tech.root: wdf
ms.assetid: EE68BED8-5FDC-4590-8E95-B228F1DFD32D
ms.date: 02/26/2018
keywords: ["IWDFDevice3::CreateInterrupt"]
ms.keywords: CreateInterrupt, CreateInterrupt method, CreateInterrupt method,IWDFDevice3 interface, IWDFDevice3 interface,CreateInterrupt method, IWDFDevice3.CreateInterrupt, IWDFDevice3::CreateInterrupt, umdf.iwdfdevice3_createinterrupt, wdf.iwdfdevice3_createinterrupt, wudfddi/IWDFDevice3::CreateInterrupt
f1_keywords:
 - "wudfddi/IWDFDevice3.CreateInterrupt"
 - "IWDFDevice3.CreateInterrupt"
req.header: wudfddi.h
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
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFDevice3.CreateInterrupt
targetos: Windows
req.typenames: 
---

# IWDFDevice3::CreateInterrupt


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateInterrupt</b> method creates a framework interrupt object.



## -parameters




### -param Configuration [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/ns-wudfinterrupt-_wudf_interrupt_config">WUDF_INTERRUPT_CONFIG</a> structure that was initialized by a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nf-wudfinterrupt-wudf_interrupt_config_init">WUDF_INTERRUPT_CONFIG_INIT</a> macro.


### -param ppInterrupt [out]

A pointer to a buffer that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfinterrupt">IWDFInterrupt</a>  interface for the new interrupt object.


## -returns



The method returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



Your driver must call <b>CreateInterrupt</b> one time for each interrupt vector that its device requires. If the device supports message-signaled interrupts (MSI), the driver must create an interrupt object for each message that the device can support. 

Drivers typically call the <b>CreateInterrupt</b> method from an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-idriverentry-ondeviceadd">OnDeviceAdd</a> callback function, but can also call this method from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">IPnpCallbackHardware2::OnPrepareHardware</a>.


After the Plug and Play (PnP) manager assigns system resources to the device, the framework stores information about the device's assigned interrupt resources in the interrupt objects that the driver has created. (Drivers that do not support Plug and Play cannot use interrupt objects.)


The system might not assign all the interrupt resources that a device can support. For example, a driver  creates eight interrupt objects for a device that is capable of supporting eight MSI messages. However, the system might assign only one message to the device. In that case, seven of the interrupt objects will be unused.


Typically, your driver should store interrupt-specific information, such as the copied contents of device interrupt registers, in the interrupt object's context space. A driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-assigncontext">IWDFObject::AssignContext</a> to register a context and to request notification when the object becomes invalid.

UMDF supports level-triggered interrupts starting in Windows 8. If a driver running on an operating system earlier than  Windows 8 creates a level-triggered interrupt in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-idriverentry-ondeviceadd">OnDeviceAdd</a>, <b>CreateInterrupt</b> succeeds because the operating system has not yet assigned resources.  However, when the framework attempts to connect the interrupt later, the device fails to start.


For more information about handling interrupts in UMDF drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts">Accessing Hardware and Handling Interrupts</a>.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT  hr;
IWDFInterrupt* pInterrupt;
WUDF_INTERRUPT_CONFIG  interruptConfig;

WUDF_INTERRUPT_CONFIG_INIT(&interruptConfig,
                           MyInterruptIsr,
                           MyInterruptWorkItem);

hr = pDevice->Create(&interruptConfig, 
                     &pInterrupt);
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/ns-wudfinterrupt-_wudf_interrupt_config">WUDF_INTERRUPT_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfinterrupt/nf-wudfinterrupt-wudf_interrupt_config_init">WUDF_INTERRUPT_CONFIG_INIT</a>
 

 

